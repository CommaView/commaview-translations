# CommaView translations

The words of [CommaView](https://commaview.com), the Android app for comma devices, in every language it offers. The
translations are **machine translated**, and the app says so; this repository is where anyone who speaks a language
can make them better.

| Language | In English | Folder | Glossary |
|---|---|---|---|
| Deutsch | German | `values-de` | [glossary](glossary/glossary-de.md) |
| Español | Spanish | `values-es` | [glossary](glossary/glossary-es.md) |
| Français | French | `values-fr` | [glossary](glossary/glossary-fr.md) |
| 日本語 | Japanese | `values-ja` | [glossary](glossary/glossary-ja.md) |
| 한국어 | Korean | `values-ko` | [glossary](glossary/glossary-ko.md) |
| Português (Brasil) | Portuguese (Brazil) | `values-pt-rBR` | [glossary](glossary/glossary-pt-rBR.md) |
| ไทย | Thai | `values-th` | [glossary](glossary/glossary-th.md) |
| Türkçe | Turkish | `values-tr` | [glossary](glossary/glossary-tr.md) |
| Українська | Ukrainian | `values-uk` | [glossary](glossary/glossary-uk.md) |
| 简体中文 | Chinese (Simplified) | `values-zh-rCN` | [glossary](glossary/glossary-zh-rCN.md) |
| 繁體中文 | Chinese (Traditional) | `values-zh-rTW` | [glossary](glossary/glossary-zh-TW.md) |

English (`values/`) is the source. The files here are exported from the app's repository with
`tools/i18n/translations-export.py`; strings of features that aren't out for everyone yet are left out until they are.

## Suggest a change

1. Read [CONTRIBUTING.md](CONTRIBUTING.md) (placeholders, escaping, names kept as they are) and your language's
   glossary in `glossary/`.
2. Edit the string in `app/values-<qualifier>/strings_<area>.xml` (or `shared-ui/…`): open a pull request, or, if you'd
   rather not edit files, an issue saying which string (its `name`), what it says now and what it should say.
3. Change only translations. English (`values/`) is written in the app's repository and comes here with each export;
   a pull request that changes English, adds a string or removes one can't be taken.

## How review works

- A maintainer reads each pull request. A word that the glossary decides is changed in the glossary too, so every
  screen keeps saying the same thing; where another speaker of the language is around, they're asked to look as well.
- The app's repository takes the translations back with `tools/i18n/translations-import.py`, which copies only
  translations of strings English still has and refuses a file whose placeholders, plurals or escaping don't match
  the English. Every language is then checked on screen at the largest text size before a release ships it.
- A merged change reaches people in the next CommaView release.

## Licence

CommaView's strings and their translations are © RhynoTech, all rights reserved ([LICENSE](LICENSE)). They're
published here so they can be reviewed and improved, not for use elsewhere.

What you contribute is yours to give: by opening a pull request or an issue with a translation, you dedicate it to
the public domain under **CC0-1.0** ([CONTRIBUTIONS-CC0-1.0.txt](CONTRIBUTIONS-CC0-1.0.txt)), so CommaView can ship it
without conditions.
