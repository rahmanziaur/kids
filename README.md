# MakeCode Tutorials

A collection of tutorials, example projects, and embeddable demos built with [Microsoft MakeCode Arcade](https://arcade.makecode.com/) — a free, block-based (with optional JavaScript/TypeScript) game-making platform for kids and beginner programmers.

This repo/site is meant to help readers **see the code, see the editor, and see the game run** — all without leaving the page — by embedding live MakeCode projects directly into Markdown or HTML documentation.

---

## 🔗 Project Link

Scan the QR code or click the link below to open the example project directly in the MakeCode Arcade editor:

**Project:** [https://arcade.makecode.com/S21431-99886-00500-09210](https://arcade.makecode.com/S21431-99886-00500-09210)

<img src="https://raw.githubusercontent.com/rahmanziaur/kids/main/download.gif" alt="QR code linking to the MakeCode Arcade project" width="200" />

---

## 🖼️ Editor Preview

A quick look at the MakeCode Arcade editor — blocks workspace on one side, simulator on the other:

<img src="https://raw.githubusercontent.com/rahmanziaur/kids/master/makecode1.jpg" alt="MakeCode Arcade editor showing the blocks workspace and simulator" width="600" />

---

## 📖 About MakeCode Arcade

MakeCode Arcade lets you build retro-style games using drag-and-drop blocks (which can be converted to JavaScript). Every project you create and share gets a permanent **share ID** that looks like:

```
S21431-99886-00500-09210
```

That ID is the key to everything below — it's what you swap into the embed URLs to show *your* project instead of the example one.

### Getting your own share ID
1. Open your project in the [MakeCode Arcade editor](https://arcade.makecode.com/).
2. Click **Share**.
3. Copy the generated URL — it will look like `https://arcade.makecode.com/S21431-99886-00500-09210`.
4. The part after the last `/` (e.g. `S21431-99886-00500-09210`) is your share ID. Use it in place of `pub:S21431-99886-00500-09210` in any embed below.

---

## 🧩 Embedding a MakeCode Project

There are three different ways to embed a project, depending on how much interactivity you want to show. Each uses a responsive, aspect-ratio-locked `<iframe>` wrapper so it scales cleanly on any screen size.

### 1. Code Embed — blocks/code viewer (compact)

Shows just the blocks/code in a small, fixed-height viewer. Best for inline "here's the code" snippets inside a tutorial step.

```html
<div style="position:relative;height:calc(300px + 5em);width:100%;overflow:hidden;">
  <iframe
    style="position:absolute;top:0;left:0;width:100%;height:100%;"
    src="https://arcade.makecode.com/---codeembed#pub:S21431-99886-00500-09210"
    allowfullscreen="allowfullscreen"
    frameborder="0"
    sandbox="allow-scripts allow-same-origin">
  </iframe>
</div>
```

**When to use it:** mid-tutorial, right after explaining a block of logic, so the reader can see exactly what those blocks look like without the full editor chrome.

---

### 2. Full Editor Embed — blocks + simulator side-by-side

Loads the entire MakeCode editor (blocks workspace, toolbox, and simulator) inside the page. Readers can scroll through the code *and* play the game live.

```html
<div style="position:relative;height:0;padding-bottom:70%;overflow:hidden;">
  <iframe
    style="position:absolute;top:0;left:0;width:100%;height:100%;"
    src="https://arcade.makecode.com/#pub:S21431-99886-00500-09210"
    frameborder="0"
    sandbox="allow-popups allow-forms allow-scripts allow-same-origin">
  </iframe>
</div>
```

**When to use it:** at the start or end of a tutorial, as the "full project" reference so readers can explore everything at once.

---

### 3. Run Embed — simulator only

Loads **only the game simulator** (no blocks, no editor) — just a playable screen. Great for a clean demo at the top of a tutorial before any code is explained.

```html
<div style="position:relative;height:0;padding-bottom:117.6%;overflow:hidden;">
  <iframe
    style="position:absolute;top:0;left:0;width:100%;height:100%;"
    src="https://arcade.makecode.com/---run?id=S21431-99886-00500-09210"
    allowfullscreen="allowfullscreen"
    sandbox="allow-popups allow-forms allow-scripts allow-same-origin"
    frameborder="0">
  </iframe>
</div>
```

**When to use it:** as a "play it first" hook before diving into the how-to-build-it steps.

---

### Quick comparison

| Embed type | URL pattern | Shows | Best for |
|---|---|---|---|
| Code embed | `/---codeembed#pub:<id>` | Blocks/code only, compact | Inline code snippets |
| Full editor | `/#pub:<id>` | Blocks + simulator + toolbox | Full project reference |
| Run only | `/---run?id=<id>` | Simulator only | Playable demo hook |

---

## 📐 Why the responsive wrapper?

Each embed uses a different sizing technique on purpose, matched to its content's natural shape:

- **Code embed** — `height: calc(300px + 5em)` gives a fixed minimum height tall enough to show several blocks without wasting space on small screens.
- **Full editor** — `padding-bottom: 70%` creates a wide aspect ratio (the editor is landscape-oriented: toolbox + blocks + simulator side by side).
- **Run embed** — `padding-bottom: 117.6%` creates a tall, narrow aspect ratio matching the MakeCode Arcade screen (160×120 game canvas plus on-screen controls), so the simulator isn't cropped or letterboxed.

The `position: absolute` iframe inside a `position: relative`, `overflow: hidden` container is the classic "responsive iframe" pattern — it lets the embed scale fluidly with the width of its parent while keeping a fixed aspect ratio.

> 💡 Tip: if your embed looks cropped or has awkward whitespace, adjust the `padding-bottom` percentage to better match the content's natural aspect ratio.

---

## ✍️ Writing a New Tutorial

Suggested structure for each tutorial file (e.g. `tutorials/dodge-game.md`):

1. **Title & summary** — one or two sentences on what the reader will build.
2. **Play it first** — a *Run Embed* so readers see the finished game.
3. **Step-by-step instructions** — prose + screenshots, with a *Code Embed* after each major step to show the relevant blocks.
4. **Full project** — a *Full Editor Embed* at the end so readers can explore, remix, and open the project directly in MakeCode.
5. **Challenges** — optional "try it yourself" extensions.

---

## 🗂 Suggested Repo Structure

```
makecode-tutorials/
├── README.md
├── tutorials/
│   ├── 01-getting-started.md
│   ├── 02-dodge-game.md
│   └── 03-platformer-basics.md
└── assets/
    └── screenshots/
```
---

## 🤝 Contributing

1. Fork this repo.
2. Add your tutorial under `tutorials/`, following the structure above.
3. Make sure every embedded project has a valid, publicly shared MakeCode ID (test the link in a private browser window before submitting).
4. Open a pull request.

---

## 📚 Resources

- [MakeCode Arcade Editor](https://arcade.makecode.com/)
- [MakeCode Arcade Documentation](https://arcade.makecode.com/docs)
- [MakeCode Arcade GitHub](https://github.com/microsoft/pxt-arcade)

## 📄 License

Tutorial text and original example projects in this repo are released under the MIT License unless otherwise noted. MakeCode Arcade itself is © Microsoft.
 


> Open this page at [https://rahmanziaur.github.io/makecode/](https://rahmanziaur.github.io/makecode/)

## Use as Extension

This repository can be added as an **extension** in MakeCode.

* open [https://arcade.makecode.com/](https://arcade.makecode.com/)
* click on **New Project**
* click on **Extensions** under the gearwheel menu
* search for **https://github.com/rahmanziaur/makecode** and import

## Edit this project

To edit this repository in MakeCode.

* open [https://arcade.makecode.com/](https://arcade.makecode.com/)
* click on **Import** then click on **Import URL**
* paste **https://github.com/rahmanziaur/makecode** and click import

#### Metadata (used for search, rendering)

* for PXT/arcade
<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>
