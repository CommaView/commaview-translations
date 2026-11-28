# commaview.com's words

The website's text, [commaview.com](https://commaview.com), in English and each language the site offers. Like the
app's, the translations are **machine translated**; this is where anyone who speaks a language can make them better.
The files are exported from the site's repository with `scripts/translations-export.mjs`; only what's published is
here (no drafts).

| Language | Folder name here | The app's words in that language |
|---|---|---|
| German | `de` | `app/values-de` |
| Spanish | `es` | `app/values-es` |
| French | `fr` | `app/values-fr` |
| Japanese | `ja` | `app/values-ja` |
| Korean | `ko` | `app/values-ko` |
| Portuguese (Brazil) | `pt-br` | `app/values-pt-rBR` |
| Thai | `th` | `app/values-th` |
| Turkish | `tr` | `app/values-tr` |
| Ukrainian | `uk` | `app/values-uk` |
| Chinese (Simplified) | `zh-cn` | `app/values-zh-rCN` |
| Chinese (Traditional) | `zh-tw` | `app/values-zh-rTW` |

English is the source: `en.json` and the `en/` folders. A change is to a translation, never to English.

## What each file is

- `words/<lang>.json`: the words the site's own pages draw: the header and footer, the home page, the guides'
  and the blog's chrome, Supported forks, What's new, the team page and Browser View's car pages. Each key's value is
  the text; `{name}` in braces is filled by the site (a title, a version, a count) and stays exactly as English writes
  it. Translate only the values: keys stay as they are, and a key English hasn't can't be added.
- `guides/<lang>/<slug>.md`: a guide (commaview.com/guides/<slug>). Its front matter, between the `---` lines, holds
  the guide's words (title, description, lede, each step's title, body, pins' text, notes and warnings, tabs' labels,
  the checks and fixes) and its structure, which stays as English has it (below). The description is at most 200
  characters.
- `blog/<lang>/<slug>.md`: a blog post (commaview.com/blog/<slug>): its title, description (at most 180
  characters), hero label and text.
- `forks/<lang>/<id>.md`: a fork's section on Supported forks (commaview.com/forks): its heading, the note the
  table adds to the fork's name, and what CommaView draws for it.
- `whats-new/<lang>/<date>.yaml`: an update on What's new (commaview.com/whats-new): its title and each list's
  items (a title and a sentence or two). Its date and versions are English's.

## What stays as English has it

The site reads these, so a translation that changes them can't be taken back (the site's import refuses the file
and says why):

- in a guide's front matter: `topic`, `order`, `kind`, `appVersion`, `parked`, `updated`, `related` and
  `blogPost`; every step, in English's order, with its `id`; each step's and tab's `screen` and `clip` (the
  app's screen and clip it shows) and each pin's `target` (where on that screen it points), so translate a pin's
  `text` only;
- in a post's front matter: `slug`, `date`, `updatedDate` and `draft` (its `tags` are keywords for search
  engines, yours to translate);
- in a fork's section: its fields (a `tableNote` where English has one, none where it hasn't);
- in an update: `date`, `app` and `runtimeVersion` (leave them out or keep English's) and every list with as many
  items as English's;
- links: where each one goes. Write a link's words in your language and keep its target; a link to another page
  of the site may point to that page in your language (`/guides/setup` as `/de/guides/setup`), and that's all
  that may change in it. A link within the page (`#…`) goes to one of its headings, whose anchor is made from the
  heading's words, so in a translation it's made from your heading (`## Kein Internet im Auto` is
  `#kein-internet-im-auto`), or it's one of a guide's own sections (`#fixes`, `#steps`, `#step-<id>`),
  or an anchor you keep with `<a id="…"></a>` before your heading. A link to a heading on another page
  (`/guides/car-screens#tested-hardware`) takes that page's anchor in your language;
- HTML: no tag or attribute English hasn't got (but for an anchor, `<a id="…"></a>`). Markdown's own markup
  (**bold**, lists, headings) is yours to use as the language needs;
- the YAML has to stay valid: when a value has a colon followed by a space, or starts with a quote or `*`, keep it in
  quotes as English does.

## The app's words

Where a guide or a post names what the app shows (a button, a screen, a setting), the word is in **bold** and is
the app's own: in a translation it must be exactly the app's translation of that word, from
`app/values-<qualifier>/strings_<area>.xml` in this repository (the table above gives each language's folder:
`pt-br` is `values-pt-rBR`, `zh-cn` `values-zh-rCN`, `zh-tw` `values-zh-rTW`). Search the English
`app/values/` for the word to find its key, then use that key's text in your language's folder. If the app's word is
wrong, change it there too (a pull request may change both), so the guide and the app stay the same. Names are
never translated (CommaView, comma, comma 3X, comma four, openpilot and the forks, Live View, YouTube and the others
each glossary lists), and the glossaries in `glossary/` hold the words for CommaView's terms.

## Suggest a change

As for the app's words ([README.md](../README.md), [CONTRIBUTING.md](../CONTRIBUTING.md)): edit the translation and
open a pull request, or open an issue saying which file and line, what it says now and what it should say. A merged
change reaches commaview.com in its next deploy: the site's repository takes translations back with
`scripts/translations-import.mjs`, which copies only translations of files English still has and refuses one that
breaks the rules above. The licence is the repository's ([LICENSE](../LICENSE)): the website's text is CommaView's,
and contributions are CC0-1.0 ([CONTRIBUTIONS-CC0-1.0.txt](../CONTRIBUTIONS-CC0-1.0.txt)).
