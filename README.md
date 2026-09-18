# Fountain Editor

A free, single-file screenplay editor that runs entirely in your web browser. No install, no sign-up, no internet connection required. You write in plain text, and it formats your work into a proper screenplay as you type.

Built on [Fountain](https://fountain.io), the open plain-text screenplay format.

## Quick start

1. Download `fountain-editor-v4.html` (open the file above, then use the download button).
2. Double-click it to open in your browser. Chrome or Edge are recommended (see **Saving** below).
3. Start writing in the left pane. The formatted screenplay appears live on the right.

That is the whole setup. The file is self-contained, so you can keep it anywhere, work offline, and even email it to a collaborator.

## Which browser?

**Use Chrome or Edge for real writing.** They let the editor save directly back to your file: the Save button (and Cmd+S / Ctrl+S) updates your `.fountain` file in place, and the editor always knows your filename.

**Firefox and Safari work, with one limitation.** Those browsers do not allow web pages to write back to a file, so every Save downloads a fresh copy instead (usually to your Downloads folder), and you manage the copies yourself. Everything else, including writing, live preview, themes, save history, and PDF export, works the same. There is no browser where the editor is broken; Chrome and Edge simply give the full experience.

## The idea: write freely, format automatically

Screenwriting software usually makes you stop and fuss with margins, tabs, and menus. Fountain flips that around. You write your screenplay as ordinary text and let a few simple "indicators" tell the editor how each line should look. You stay in the flow of writing, and the editor handles the industry formatting behind the scenes.

Think of it this way: you are not formatting a document, you are writing plain text with a handful of light conventions. A line typed in capital letters becomes a character cue. A line that starts with INT. or EXT. becomes a scene heading. You never leave the keyboard.

## The indicators (how to write it)

| To create this | Type this | Example |
|---|---|---|
| Scene heading | A line starting with `INT.` or `EXT.` | `INT. COFFEE SHOP - DAY` |
| Action | Just write normally | `She opens the door and steps inside.` |
| Character | A line in ALL CAPS | `JORDAN` |
| Parenthetical | A line in parentheses under a character | `(quietly)` |
| Dialogue | The line(s) directly under a character | `We need to talk.` |
| Transition | ALL CAPS ending in `TO:` | `CUT TO:` |
| Centered text | Wrap it in angle brackets | `>THE END<` |
| Emphasis | Asterisks and underscores | `*italic*`, `**bold**`, `_underline_` |
| Page break | Three or more equals signs | `===` |

### Title page

At the very top of the document, before anything else, add a block like this followed by a blank line:

```
Title: The Great Escape
Credit: Written by
Author: Your Name
Draft date: 2026
```

### A tiny complete example

```
Title: Coffee

FADE IN:

INT. CORNER CAFE - DAY

Warm light. A BARISTA looks up.

BARISTA
The usual?

JORDAN
(smiling)
Surprise me.

> DISSOLVE TO:
```

## How it is processed and formatted

As you type, the editor reads your text line by line and identifies each element by its indicator. It sees the capital letters and knows JORDAN is a character. It sees INT. and knows a scene is starting. It sees the parentheses and indents that line as a parenthetical. It then renders the right-hand preview in proper screenplay layout: correct margins, Courier font, and character cues and dialogue placed where the industry expects them.

Nothing about your text file changes. The formatting lives in how the file is displayed and exported, not in the text itself. Your writing stays clean, portable plain text.

## Features

- **Live preview**: the formatted screenplay updates as you type
- **Typewriter scrolling**: your active line is held at a steady eyeline while you type, never pinned to the bottom edge
- **Linked panes**: the preview follows your cursor as you write; scroll the preview to any moment and the writing view mirrors you there
- **Scene navigator**: jump to any scene from the sidebar (both panes move together)
- **Resizable panes**: drag the divider to size the writing and preview areas
- **Focus mode**: hide the preview to write in a full-width window
- **Themes**: writing-window colors (dark, sepia, paper, and more) plus preview paper shades, including a Night mode for late hours
- **Save history**: the editor keeps your last 20 saves in the browser, restorable anytime
- **Open and save** real `.fountain` files
- **Export a clean PDF** to share

## Saving and sharing

Your work is saved as a `.fountain` file. Because Fountain is an open plain-text standard, that file is yours forever. It opens in this editor, in any plain-text editor, and in other screenwriting apps that support Fountain (such as Highland, Slugline, and WriterDuet).

- **Chrome and Edge**: the Save button writes straight back to your file (Cmd+S or Ctrl+S).
- **Firefox and Safari**: the Save button downloads a copy of your file.
- On the first save of a new script, the editor suggests a filename taken from your `Title:` line, so a script titled "Crystal Syndicate" saves as `crystal-syndicate.fountain` rather than `untitled.fountain`.
- The editor also **autosaves** your work in the browser between sessions.

### Exporting a PDF

Click **Export PDF**. A clean, script-only page opens and the browser's print dialog appears. Choose "Save as PDF." For the cleanest result, open "More settings" and turn off "Headers and footers" so the browser does not add the page title and date to the margins.

Note: PDF page breaks use the browser's automatic breaks. This is great for short pieces. Precise, studio-grade pagination is planned for a later version.

## What's new in v4

Writing comfort and safety upgrades:

- **Typewriter scrolling.** While you type, your active line stays at a comfortable eyeline with breathing room below it, instead of scraping the bottom of the window.
- **Linked panes.** The preview follows your cursor as you write. Scroll the preview by hand to find a moment and the writing view mirrors you there; start typing and both panes snap back to your cursor. Scene navigator clicks move both panes.
- **Preview paper themes.** White, Cream, Dim, and Night, for writing late without the bright page. Printing and PDF export always stay black on white regardless of the screen theme.
- **Save history.** The editor keeps your last 20 saves in this browser. The History button lists them and can restore any one; a restore is always reversible and never touches your file until you save again.
- **Smarter first save.** A new script is named from its `Title:` line, so "Crystal Syndicate" saves as `crystal-syndicate.fountain` instead of `untitled.fountain`.
- **Sturdier saving.** Rapid back-to-back saves queue up instead of colliding, and if your cloud sync briefly locks the file, the save retries on its own.

(v3 was an internal release; its changes ship here.)

## What's new in v2

The formatting engine was audited line by line against the Fountain spec and hardened:

- Character extensions can be lowercase: `JORDAN (cont'd)` now formats as a character cue.
- Emphasis follows the spec's spacing rules, so stray asterisks or underscores in a sentence no longer italicize text by accident, and `\*` or `\_` print literally.
- Lyrics (`~`), notes (`[[...]]`), and indented forced-action lines all parse correctly, and an unclosed note can never hide part of your script.
- Title pages now render `Authors:`, `Source:`, and `Date:`, and files saved with a UTF-8 byte-order mark are read correctly.

(`fountain-editor-v1.html` remains available as the previous version.)

## Credits

Built by Rooftop Pictures.

The Fountain format was created by John August, Nima Yousefi, Stu Maschwitz, and Martin Vilcans. Learn more at [fountain.io](https://fountain.io).

## License

Released under the MIT License. See [LICENSE](LICENSE).
