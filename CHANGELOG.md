# Changelog

All notable user-visible changes to MD Viewer are listed here. The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## [1.0.0] - 2026-11-04

MD Viewer 1.0.0 is the first sandboxed release. The direct download (Developer ID, notarized by Apple) and the Mac App Store version are the same app.

### Added

- **App Sandbox.** MD Viewer now runs in the macOS App Sandbox: it can read and write only what you open or allow. Documents, folders and the Quick Look preview work as before; when a document needs more than the file you opened, MD Viewer asks for it.
- **Folder access band.** When a document needs its folder, a small band at the bottom of the window says why and offers **Grant Access…**, **Not Now** and **Don't Ask for This Folder**. It appears when the images next to a document can't be shown, when `[[links]]` and embeds can't be resolved, and when comments should be saved next to the document. **Grant Access…** opens the standard macOS folder panel, already pointed at the most likely folder. If the document is inside a folder you opened with **Open Folder…**, the band can upgrade that permission without showing the panel.
- **Settings ▸ Folder Access.** Lists the folders you have allowed, with their path, what each one is used for and when it was last used. **Remove** takes one folder away, **Remove All** takes all of them away (nothing on your Mac is deleted), **Add Folder…** allows a folder in advance, **Choose Again…** re-selects a folder that was moved or renamed, and **Ask Again** brings back the band for folders you told MD Viewer not to ask about.
- **Permissions are remembered.** A folder you allow stays allowed until you remove it. Documents inside it show their images, links and comments without asking again.
- **Comments without folder access.** Until you allow the document's folder, comments are kept inside the app, and the band offers to save them next to the document. When you allow the folder, they move into `<name>.md.review.md` beside the document, so an AI agent can read them.
- **About window** (*MD Viewer ▸ About MD Viewer*): the version and build, a button that copies the version and macOS line for support requests, links to the website, contact, source and downloads, issue reports and the privacy policy, and a **Licenses and Notices** page that shows the license texts of the bundled open-source libraries without a network connection.
- **Help menu** links: MD Viewer Website, Report an Issue… and Privacy Policy.
- **Mac App Store.** MD Viewer arrives on the Mac App Store as **MD Viewer for Markdown Docs**, next to the direct download.

### Changed

- Images next to a document, `[[links]]` and embeds, and the comment file next to a document now need your permission for the folder. Documents that need nothing beyond the file itself open exactly as before.
- Folders you open with **Open Folder…** are remembered too (listed as "Folder browsing only"), so recent and favorite folders reopen without asking.
- **Updating from 0.2.x:** your settings are carried over automatically the first time 1.0.0 starts. MD Viewer starts with the welcome window once; the open tabs and the recent documents list of 0.2.x are not carried over. Recent and favorite folders stay in the list, but macOS may ask you to allow a folder again: a folder marked "Grant access to open it again" needs one click and a confirmation in the folder panel.
- **Both versions on one Mac:** if you install the direct download and the Mac App Store version on the same Mac, macOS asks once, the first time you open each of them after the other, to confirm that the app differs from the version you opened before. Choose **Open Anyway**; after that both open without asking.

### Fixed

- **⌘Z** (Edit ▸ Undo) now undoes a task checkbox click. Before, Undo could stay disabled after ticking a task.

### Security

- MD Viewer can only reach the files and folders you open or allow. A document cannot open the folder panel by itself: it appears only after you click.
- For safety, MD Viewer refuses to take access to your whole home folder, a whole disk, system folders, Library or hidden folders, and tells you to choose the document's own folder or a folder above it that is not one of those.
- Only your own clicks on links in a document are acted on. Clicks that a document's content generates by script are ignored.

## [0.2.2] - 2026-11-04

### Changed

- Printing (⌘P, File ▸ Print… and the toolbar button) now pages the document for the paper selected in the print panel: A4 when no printer is chosen or in most regions, Letter in the US. The text reflows onto that paper with a 20 mm margin, and the page is centered and fills the whole sheet.
- Printing uses the light theme by default (white paper, black text), so documents read in the dark theme print legibly and save ink. Settings ▸ Printing and PDF ▸ *Theme when printing* switches to the selected theme. Exporting a PDF (⇧⌘E) still uses the selected theme.
- Printed PDFs no longer contain hidden markers or the app's internal links.

### Fixed

- In the dark theme the print preview shrank the page into a corner of the sheet and left white strips along the top and right edge. The page now fills the sheet.
- Changing the paper in the print panel after it opened now re-centers and rescales the page on the new paper, and the chosen paper is used for the next print.
- ⌘P, File ▸ Print… and the toolbar button (in both Pages and Flow) now go through the same code path, so they behave the same.

## [0.2.1] - 2026-11-04

### Added

- Tooltips: every icon-only button shows a one-sentence description and its keyboard shortcut after about 0.4 seconds of hovering, in English and Turkish.
- A pointing-hand cursor over the custom glass buttons.

### Changed

- Settings window: the window buttons sit inside the glass surface, long content scrolls, and a hint at the bottom edge shows when there is more below.

## [0.2.0] - 2026-11-04

### Added

- **Obsidian support**, on by default: `[[wikilinks]]` (`[[Note|label]]`, `[[Note#Heading]]`, `[[Note#^block]]`), embeds (`![[…]]` for notes, headings, blocks, images, PDFs), callouts (all 13 types, titles, foldable, nested, custom colors from `.obsidian/snippets`), a Properties card (including Turkish keys and JSON-style properties, tag and alias chips), `#tags`, `==highlights==`, `%%hidden comments%%`, `^block-ids`, custom task states (`- [/]`, `- [-]`, `- [?]`) and Obsidian line breaks.
- **Links** sidebar (⌥⌘6): backlinks and outgoing links with context.
- **Tags** mode in the Files sidebar, with nested tags.
- **Quick Switcher** (⌘K): fuzzy search over note names and aliases, with open tabs and recent documents when the field is empty.
- **Search in Vault** (⇧⌘F): search across all notes with `"phrases"`, `-exclusions`, `tag:`, `path:` and `file:` filters, case and accent insensitive (including Turkish `ı/İ`).
- **Find** in the document (⌘F, ⌘G, ⇧⌘G) in Flow, Pages and Canvas.
- **Canvas**: Obsidian `.canvas` files open read-only, with pan, zoom and fit.
- **Hover preview**: hovering a `[[link]]` in Flow shows the target section in a small card.
- One-time **vault index prompt**: opening a note that belongs to an Obsidian vault offers to index the folder. The index lives in memory only. It can be turned off in Settings.
- Settings ▸ **Markdown dialect**: switch between Obsidian and GitHub syntax. Documents re-render immediately.

### Changed

- The Quick Look preview understands the Obsidian syntax too (callouts, highlights, Properties). Links to other notes are not resolved there.

## [0.1.1] - 2026-11-03

### Fixed

- Stability and reliability fixes.

## [0.1.0] - 2026-11-03

First release.

### Added

- Native macOS Markdown viewer with a Liquid Glass interface, English and Turkish.
- **Pages** (A4 pages, like Preview) and **Flow** (reflowing text) views, thumbnails and a Contents sidebar, light, dark and system themes, zoom with fit-width and fit-page.
- GitHub Flavored Markdown (tables, task lists, strikethrough, autolinks), footnotes, alerts (`> [!NOTE]`), a front matter card, heading anchors, emoji shortcodes, relative images and code highlighting.
- Offline **Mermaid** diagrams and **KaTeX** math, loaded only when a document needs them.
- **ASCII and Unicode box diagrams** drawn as crisp vector graphics, with a Diagram | Text switch.
- **Live follow** and automatic refresh when an AI agent or editor changes the file, with the reading position kept.
- **Changes** view that shows what changed during the session.
- **Comments** with **Send to Agent**: comments are stored in a `<name>.md.review.md` side file and can be copied as a ready-made prompt.
- Clicking a task checkbox updates the `.md` file.
- Folder browsing in a **Files** sidebar, glass tabs and **Split View** with scroll syncing.
- PDF export and printing.
- **Quick Look** preview for Markdown files in Finder.
- Make MD Viewer the default Markdown viewer from the app, and Open Recent.
