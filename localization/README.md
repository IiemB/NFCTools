# Help translate NFCTools

This folder holds every piece of text the NFCTools app shows. Each language is one folder with one file:

```
localization/
├── en.lproj/Localizable.strings   English, the source text
└── id.lproj/Localizable.strings   Bahasa Indonesia
```

The app is built from these files, so a translation merged here ships in the next release. You don't need
a Mac, Xcode, or any programming experience: a text editor and a GitHub account are enough.

Two ways to help:

- **Improve an existing language.** Fix a typo, an awkward sentence, or a wrong term.
- **Add a new language.** Translate `en.lproj/Localizable.strings` into your language.

## Add a new language

1. [Fork this repository](https://github.com/IiemB/NFCTools/fork).
2. In `localization/`, create a folder named `<language code>.lproj`, for example `fr.lproj` (French),
   `de.lproj` (German), `ja.lproj` (Japanese), `pt-BR.lproj` (Brazilian Portuguese), or `zh-Hans.lproj`
   (Simplified Chinese).
3. Copy `en.lproj/Localizable.strings` into it and translate the text on the right-hand side of each line
   (see the rules below). Save the file as UTF-8.
4. Open a pull request. Say which language it is and whether you are a native speaker.

A new language shows up in the app's language picker once the maintainer has added it to the picker,
normally in the release after your pull request is merged.

## Improve an existing language

Edit the file for that language, then open a pull request that says what you changed and why. For a small
fix you can use the pencil button on GitHub and never leave the browser.

Not comfortable with pull requests? [Open an issue](https://github.com/IiemB/NFCTools/issues) with the key
(the left-hand side of the line) and your suggested text.

## The file format

Each line is `"key" = "text";`.

```
/* Alerts */
"alert.tagDisabled.title" = "Tag Disabled";
"alert.tagDisabled.message" = "'%@' is currently disabled and cannot be emulated. Enable it in tag details first.";
```

| Part | What to do |
| --- | --- |
| `"alert.tagDisabled.title"` (the key, left of `=`) | Never change it. The app looks text up by this name. |
| `"Tag Disabled"` (the text, right of `=`) | Translate this. |
| `/* Alerts */` (a comment) | Leave it; it only groups the lines. |
| The quotes, the `=` and the `;` at the end | Keep them exactly. One missing `;` breaks the whole file. |

## Rules

1. **Keep every placeholder.** `%@`, `%d`, `%1$d`, `%2$d` and similar are replaced by the app with a
   name or a number. The translation must contain the same placeholders as the English line, the same
   number of times. You may move them to fit your grammar; numbered ones (`%1$d`, `%2$d`) keep their
   numbers when they move. A translation whose placeholders differ from English is rejected by the build,
   because it would crash the app.
2. **Keep escape sequences.** Write a quotation mark inside the text as `\"` and a line break as `\n`,
   just like the English line does.
3. **Keep the keys and the number of lines.** Don't add, remove, rename, or reorder lines.
4. **Don't translate names and technical terms:** NFC, NFCTools, NFC Tools, NFCTools Plus, TrollStore,
   Dopamine, RootHide, GitHub, Ko-fi, UID, PUPI, NDEF, ATQA, SAK, APDU, MIFARE, FeliCa, ISO 14443,
   ISO 15693, Gen3, Gen4, URL, CLI, `.nftag`, and the language names under `language.*` (each language is
   shown in its own name, for example "Bahasa Indonesia").
5. **Use Apple's wording for system features** in your language: Control Center, Lock Screen, Home Screen,
   Settings, widget. Check how your iPhone names them.
6. **Keep it short.** Button labels and titles have little room. If the English is two words, aim for
   about that length. Keep the English capitalization style only if your language uses it.
7. **Write the way a person would say it.** Plain, friendly, and consistent: pick one word for "tag",
   "emulate", "reader" and "saved" and use it everywhere. Use the form of address apps normally use in
   your language.

If a line is unclear, leave the English text in place and mention it in your pull request. An untranslated
line is better than a wrong one.

## Translating with AI

An AI assistant can produce a good first draft. Paste the prompt below, replace `[LANGUAGE]`, and paste the
whole content of `en.lproj/Localizable.strings` where shown. The file has about 430 lines; if the answer is
cut off, ask the assistant to "continue from the last complete line".

````text
You are a professional app localizer and a native speaker of [LANGUAGE]. Translate the iOS
Localizable.strings file at the end of this message from English into [LANGUAGE].

About the app: NFCTools is an iPhone app for technical users. It reads NFC tags and contactless
cards, saves them to a library of "tags", emulates a saved tag so the phone acts as that card,
writes a UID or NDEF record to a writable ("magic") tag, and has widgets, Control Center tiles, a
diagnostics screen and a "send report" feature. "NFCTools Plus" is its jailbreak companion tweak.

Format rules. They are strict, because the app crashes or shows broken text otherwise:
1. Every line is "key" = "text"; — translate only the text on the right of the equals sign. Never
   change a key, the quotes, the equals sign or the final semicolon.
2. Output every line of the input, in the same order, including blank lines and /* comments */.
   Do not add, remove, merge or reorder lines. Do not translate comments.
3. Keep every format placeholder (%@, %d, %1$d, %2$d, %ld, %.1f ...) exactly as written and the
   same number of times as in the English text. You may move a placeholder to fit the grammar.
   Numbered placeholders such as %1$d and %2$d keep their numbers when moved.
4. Keep escape sequences: \" for a quotation mark inside the text and \n for a line break. Do not
   introduce an unescaped " inside a text.
5. Keep the characters … · › and emoji where the English text has them.

Language rules:
6. Do not translate product names and technical terms: NFC, NFCTools, NFC Tools, NFCTools Plus,
   TrollStore, Dopamine, RootHide, GitHub, Ko-fi, UID, PUPI, NDEF, ATQA, SAK, APDU, MIFARE, FeliCa,
   ISO 14443, ISO 15693, Gen3, Gen4, URL, CLI, .nftag.
7. Keys that start with "language." are language names shown in their own language (for example
   "Bahasa Indonesia"). Leave those texts unchanged, except "language.system", which you translate.
8. For iOS features (Control Center, Lock Screen, Home Screen, Settings, widget, Face ID), use the
   exact terms Apple uses in the [LANGUAGE] version of iOS.
9. Write natural, concise interface text the way well-made [LANGUAGE] apps do, not a word-for-word
   translation. Buttons and titles must stay about as short as the English. Use the form of address
   that is standard for apps in [LANGUAGE].
10. Be consistent: choose one translation for each recurring term (tag, emulate, reader, saved tag,
    writable tag, report, diagnostics) and use it in every line. The key name tells you where a
    text appears (for example "settings.", "home.", "clone.", "diag.") — use it as context.
11. If a text is ambiguous, pick the meaning that fits an NFC app and keep going. Do not ask
    questions and do not leave notes inside the file.

Output: only the complete translated file inside one code block, nothing before or after it.

Here is the file:

[PASTE THE CONTENT OF en.lproj/Localizable.strings HERE]
````

**Review the result before you send it.** AI drafts are usually close but not finished:

- Read it as a user of the app would. Fix anything that sounds translated, too long, or inconsistent.
- Check that no line is missing: the file must have the same number of lines as the English one.
- Search for `%` and compare a few lines with English to confirm the placeholders survived.
- Say in your pull request that the draft was made with AI and that you reviewed it. A translation nobody
  who speaks the language has read will not be merged.

## What happens after you open a pull request

The maintainer reviews it and builds the app with your file. The build checks that the file is valid, that
placeholders match English, and lists any lines that are missing. If something needs a change you'll get a
comment on the pull request. Once merged, your translation ships with the next release.

This folder covers the app's interface text only.

Thank you for helping make NFCTools usable for more people.
