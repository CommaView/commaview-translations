# Translating CommaView

CommaView's words are in Android string resources: each screen's area has its own file, `strings_<area>.xml`, in English
(`values/`) and in each language (`values-<qualifier>/`, for example `values-de/`, `values-pt-rBR/`, `values-zh-rTW/`).
The app's own words are under `app/`; a few shared drawing components' words are under `shared-ui/`. English is the
source: a change is to a translation, `values-<qualifier>/`, never to `values/`.

## The rules every string keeps

- **Placeholders stay as they are.** `%1$s`, `%2$d` and the like are filled by the app (a name, a number, "this
  phone"); keep every one the English has, with its number, and move it wherever the sentence needs it. Text in braces,
  such as `{date time}` and `{car}` in the YouTube defaults, is syntax: keep it exactly as English writes it.
- **Counts** (`<plurals>`) need the forms your language has; `other` always.
- **Escaping**, as Android reads the files: `'` as `\'`, `&` as `&amp;`, `<` as `&lt;`. Keep typographic apostrophes (’) and ellipses (…) as the English has them.
  A line break is `\n`.
- **Names are never translated**: CommaView, comma (the device, lower case), comma 3X, comma four, openpilot and the
  forks, Live View, YouTube and the others each glossary lists under "Kept as they are".
- **Use your language's glossary** (`glossary/glossary-<qualifier>.md`): the words every string uses for CommaView's
  terms, so screens translated apart say the same thing. A better word for a term is a change to its glossary too.
- Short, common words first: every screen is checked at twice the usual text size on a small phone.
- The comments above a string (`<!-- … -->`) say where it shows and what its placeholders are. They're for you; leave
  them as they are.

## This phone or this device

The app names the device it runs on "this phone" on a phone and "this device" on a tablet or a car's screen, by what
the device is (`HostDevice`, in `shared`; the design system's Content rules). That's a choice of words, so each
language words it, once, and every sentence takes it as a placeholder:

- `strings_common.xml` holds the two nouns, mid-sentence and at a sentence's start: `common_this_phone` /
  `common_this_device` ("this phone" / "this device") and `common_this_phone_start` / `common_this_device_start`
  ("This phone" / "This device"). A language without capitals gives the same words to both pairs.
- A sentence that names the device says it as a placeholder: `Saved on %1$s`, `%1$s's battery is low`,
  `%2$s saves the last known position`. A sentence that starts with it and names it again has two (one for each form).
- Write the translation so it reads with either noun. Chinese, Japanese and Korean don't change a noun by case, and
  the two nouns are chosen to take the same particles: Traditional Chinese 這支手機 / 這部裝置, Japanese
  このスマートフォン / この端末, Korean 이 휴대전화 / 이 기기 (both end in a vowel, so `%1$s가`, `%1$s를`, `%1$s는`,
  `%1$s와`, `%1$s로` fit either). A language whose nouns take case or gender (German's dieses Telefon, diesem Gerät)
  picks nouns that decline alike, or words the sentence around the placeholder so that it needn't change.
- "your phone" / "your device" works the same way: `common_your_phone` / `common_your_device` and their `_start`
  forms, passed as `yourPhoneWord` / `YourPhoneWord` (`yourPhone` / `YourPhone` in English that isn't shown).
- Every sentence that names the device takes the slot; none writes "phone" for it. Where English said "the phone",
  `main` says "this phone" / "this device", so those sentences take `thisPhoneWord` too: there is no third form. A
  label that reads differently on each kind of device ("Same as the phone" / "Same as this device", Map theme) is two
  strings, chosen by `HostDevice.kind` where it's read.
- Each language's scheme, which its glossary spells out:
  - German: the slot holds the noun alone (Handy / Gerät, both neuter); the sentence writes "dieses %1$s",
    "auf diesem %1$s", "Ihr %1$s", "Ihrem %1$s". The `_start` forms are whole ("Dieses Handy", "Ihr Gerät") and
    open their sentence as its subject. No genitive ("von diesem %1$s").
  - Spanish and French: whole phrases ("este teléfono", "tu teléfono"; "ce téléphone", "votre appareil"), all
    masculine, so articles and adjectives agree either way.
  - Portuguese (Brazil): whole phrases ("este celular", "seu celular"); a preposition that contracts with "este" is
    written as its first letter before the slot: `n%1$s` (neste), `d%1$s` (deste). "seu" doesn't contract
    ("no %1$s").
  - Turkish: whole phrases ("bu telefon", "telefonunuz"); only the suffixes both nouns take alike follow the slot
    (-a, -da, -dan, -daki, -la), never the accusative or genitive, and a lower-case slot never opens a sentence.
  - Ukrainian: whole phrases ("цей телефон", "ваш телефон"), both masculine; the slot only in the nominative or
    accusative, never after a preposition or in the genitive.
  - Thai, Chinese and Japanese: whole phrases, no spaces around the slot. Korean: both nouns end in a vowel, so one
    particle fits either.

## Translating

Write the `zh-TW` strings with [the glossary](glossary/glossary-zh-TW.md), and each other language's with its own glossary
(`glossary-<qualifier>.md`). `python3 tools/i18n/check-locale.py <qualifier>` checks a language's files against the
English (keys, placeholders, plurals) without Gradle. Keep the English's placeholders (the check fails a
mismatch), names, units and numbers. Prefer a short natural phrase to a literal one; a button stays a verb.

## A word too long for its line

When a copy fails with "word broken", first ask whether the word's column is unreasonably narrow: a heading squeezed
beside a button, words beside an action that could go under them. That is a layout fix (the screen chooses its
arrangement from the words measured at the person's text size; see the responsive contract), never a shorter word.
Otherwise the word is simply too long for a label at 2× text, and the translation changes: **a shorter natural word, or
the same idea in two or more words** (German `Standort des Autos`, not `Fahrzeugstandort`; `Kontrast bei Tageslicht`,
not `Tageslicht-Kontrast`; Spanish `Reintento automático`, not `Reintentando automáticamente`). Words in Android's own
strings keep their spelling.

Don't count on a hyphen or a soft hyphen (U+00AD, `&#173;`) to break a compound. Under the app's Barlow text styles,
which leave Compose's `hyphens` unset (no hyphenation), Android neither breaks after a plain hyphen
(`Tempolimit-D / iagnose`) nor at a soft hyphen (`Fahrzeug­stan / dort`): it splits the word where the line runs out.
Only with `Hyphens.Auto` does it break at either, drawing a hyphen at a soft one (`Fahrzeug- / standort`), and that
would also hyphenate every other word by its dictionary, so the app doesn't set it. A compound kept whole must fit its
line whole, hyphens and all.

## The website's words

The words of [commaview.com](https://commaview.com), its guides, blog posts, Supported forks and What's new, are in
`website/`, translated file by file. [website/README.md](website/README.md) says what each file is and what stays
as English has it (a guide's steps, screens and links, a post's date). The rules above hold there too, and a word the
app shows, in **bold** in a guide, is the app's own translation from `app/values-<qualifier>/`.
