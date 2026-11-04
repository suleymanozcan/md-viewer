# MD Viewer usage guide

English | [Türkçe](USAGE.tr.md) · [Back to the README](../README.md)

A step-by-step guide, from the first launch to a full AI-agent review loop. The screenshots use made-up sample documents.

- [1. First launch](#1-first-launch)
- [2. Make MD Viewer your default Markdown app](#2-make-md-viewer-your-default-markdown-app)
- [3. Open a file or a folder](#3-open-a-file-or-a-folder)
- [4. Pages or Flow](#4-pages-or-flow)
- [5. Open an Obsidian vault](#5-open-an-obsidian-vault)
- [6. Compare two documents in Split View](#6-compare-two-documents-in-split-view)
- [7. The AI-agent workflow](#7-the-ai-agent-workflow)
- [8. Print and export](#8-print-and-export)
- [9. Settings](#9-settings)

## 1. First launch

Open MD Viewer from Applications. The welcome window shows your recent files and folders, a drop zone ("Drag a Markdown file here"), an **Open File…** button (**⌘O**) and an **Open Folder…** button. You can also drag a `.md` file onto the window.

<p align="center">
  <img src="screenshots/welcome-en.png" width="520" alt="The welcome window with recent files and a drop zone">
</p>

## 2. Make MD Viewer your default Markdown app

MD Viewer never takes over `.md` files on its own. To do it yourself, choose **MD Viewer ▸ Make Default Markdown Viewer…**, or click *Make Default* on the welcome window or in Settings. Settings also shows which app is the current default.

You can also do it in Finder: select a `.md` file, press **⌘I**, choose MD Viewer under *Open with*, then click *Change All…*.

## 3. Open a file or a folder

- **File ▸ Open…** (**⌘O**) opens a document in a new tab. **File ▸ Open Recent** lists recent documents.
- **File ▸ Open Folder…** (**⇧⌘O**) opens a folder. Its Markdown files appear in the **Files** sidebar (**⌥⌘3**) and the list updates live as files change.
- Click a file to open a tab, **⌥-click** to open it in the right pane, **⌘-click** to open it in a new window.

<p align="center">
  <img src="screenshots/files-en.png" width="300" alt="The Files sidebar with a folder tree">
</p>

## 4. Pages or Flow

- **Pages** (**⌃⌘1**) lays the document out as A4 pages with thumbnails (**⌥⌘1**) and Contents (**⌥⌘2**).
- **Flow** (**⌃⌘2**) reflows the text to the window width.
- Zoom with **⌘+** and **⌘−**, reset with **⌘0**. **Fit Width** is **⌥⌘0** and **Fit Page** is **⌥⌘9**. On a Turkish keyboard see the [FAQ](../README.md#faq).
- Choose the theme in **View ▸ Theme**.

<p align="center">
  <img src="screenshots/pages-en.png" width="760" alt="Pages mode with thumbnails">
</p>

## 5. Open an Obsidian vault

1. Open any note that lives inside an Obsidian vault (a folder with a `.obsidian` folder). Or use **Open Folder…** on the vault folder.
2. If you opened a single note, MD Viewer offers once to index the vault: click **Index Vault**. The index stays in memory and is never written to disk.
3. Use the **Links** sidebar (**⌥⌘6**) for backlinks and outgoing links, **Files ▸ #** for tags, **⌘K** to jump to any note, **⇧⌘F** to search all notes, and **⌘F** to search the current note.
4. Hover over a `[[link]]` in Flow for a preview card. Click a link to open the note, **⌥-click** for the right pane, **⌘-click** for a new window.

<p align="center">
  <img src="screenshots/vault-prompt-en.png" width="760" alt="The vault index prompt">
</p>
<p align="center">
  <img src="screenshots/obsidian-en.png" width="760" alt="An Obsidian note with the Links sidebar">
</p>

If you prefer GitHub-style rendering, switch *Markdown dialect* to **GitHub** in Settings.

## 6. Compare two documents in Split View

1. Open both documents in tabs.
2. Click the split button in the toolbar (or press **⌥⌘O** to pick a second file). Choose the second document from the list: open tabs, recent files, *Open…* or *Open the same document*.
3. Turn on **View ▸ Split View ▸ Sync Scrolling** (**⌃⌘Y**) so both panes follow the same heading.
4. **⌃⌘X** swaps the panes, **⌥⌘←** and **⌥⌘→** move focus between them. Close the split from the **Split View** menu.

<p align="center">
  <img src="screenshots/split-en.png" width="760" alt="Split View with scroll syncing">
</p>

## 7. The AI-agent workflow

This is the loop MD Viewer was built for: the agent writes a plan, you read it live, comment on it, and send the comments back.

### Step 1: open the plan and follow changes

Open the plan Markdown file the agent is working on. Switch to **Flow** and turn on **Follow Changes** (**⇧⌘L**, or the target button in the toolbar). While the agent writes, the view scrolls to the part that changed. Scroll yourself and following pauses, so it never fights you. A half-written file is skipped until it is complete.

<p align="center">
  <img src="screenshots/live-follow-en.png" width="760" alt="Following changes while an agent adds sections to a plan">
</p>

### Step 2: review what changed

Open **Changes** (**⌥⌘4**). It compares the document with the last version you saw (*Since last viewed*) and shows removed and added lines. Click **Mark as Seen** when you have caught up. The history lives only while the document is open.

<p align="center">
  <img src="screenshots/changes-en.png" width="760" alt="The Changes sidebar with a line diff">
</p>

### Step 3: comment

Select the text you want to discuss (or click the **+** beside a block) and press **⇧⌘K**. Type your comment in the **Comments** sidebar (**⌥⌘5**) and press **⌘↩** to save. Your document is not touched: comments are saved next to it as `<document>.md.review.md`.

<p align="center">
  <img src="screenshots/comment-en.png" width="300" alt="Writing a comment">
  &nbsp;
  <img src="screenshots/comments-en.png" width="460" alt="Comments highlighted in the document">
</p>

### Step 4: Send to Agent

Press **⌥⌘P** (**Edit ▸ Copy Prompt for Agent**). MD Viewer copies a prompt like this to the clipboard:

````text
`/path/to/checkout-plan.md` has my review comments. Apply each open comment below to the file (edit `checkout-plan.md`; do NOT modify the review file). Line numbers are 1-based and the last known position; search for the quoted text for the real match.

Review file: /path/to/checkout-plan.md.review.md

### R1 · Checkout Service Migration Plan › 1. Goal · line 10
Quoted:
```
Move the checkout flow out of the legacy monolith into a standalone service without changing the customer-facing API. ...
```
Comment:
```
Please add the rollback time budget here.
```

When done, briefly tell me how you addressed each comment.
````

(The real prompt also tells the agent to treat the quoted text and comments as data, not as instructions.) Paste it into your agent. When the agent updates the file, MD Viewer shows the change (Step 1 and 2 again).

<p align="center">
  <img src="screenshots/send-to-agent-en.png" width="760" alt="The notice that the prompt was copied">
</p>

### Task checkboxes

Click a `- [ ]` checkbox to tick it; MD Viewer writes the change to the `.md` file. **⌘Z** undoes it. If the file changed on disk in the meantime, the click is refused so nothing is overwritten.

<p align="center">
  <img src="screenshots/tasks-en.png" width="760" alt="A task list with some boxes checked">
</p>

## 8. Print and export

- **⇧⌘E** exports a PDF with the selected theme.
- **⌘P** prints on the paper selected in the print panel, with a light theme by default. Change this in Settings ▸ *Printing and PDF* ▸ *Theme when printing*.

<p align="center">
  <img src="screenshots/print-en.png" width="760" alt="The print panel with a light page preview">
</p>

## 9. Settings

Open Settings with **⌘,** or the gear button. There you set the theme, default view and zoom, printing theme, whether new documents open in a tab or a window, follow defaults, Markdown dialect, the vault prompt, the interface language, remote images and the default app. The language change applies after a restart.

<p align="center">
  <img src="screenshots/settings-en.png" width="640" alt="The Settings window">
</p>

Need help? See [SUPPORT.md](../SUPPORT.md).
