# Contributing & Getting Started

This guide is for anyone who wants to understand how this documentation site works, add new content, or maintain existing pages. Read this first before editing any files.

---

## How the Site Works

This is a [Docsify](https://docsify.js.org/) documentation site. Docsify renders Markdown files directly in the browser — there is no build step. The site is hosted on GitHub Pages from the `docs/` folder of this repository.

- **Live site:** https://robertvejvoda.github.io/fairspot-architecture/
- **Source files:** `docs/` folder in this repository
- **Entry point:** `docs/index.html` (Docsify config) + `docs/Home.md` (home page content) + `docs/README.md` (applied template version)
- **Sidebar:** `docs/_sidebar.md` — defines all navigation links

Changes committed to the `main` branch are automatically published to GitHub Pages within a few minutes.

---

## Folder Structure

```
docs/
├── index.html                      # Docsify configuration (rarely edited)
├── README.md                       # Applied template version
├── Home.md                         # Home page shown by Docsify
├── _sidebar.md                     # Navigation sidebar (all links live here)
├── contributing.md                 # This file
└── architecture/
    ├── README.md                   # Architecture Repository index
    ├── artifact-register.md
    ├── architecture-vision.md
    ├── togaf-adm-map.md
    ├── decisions.md
    ├── principles.md
    ├── requirements.md
    ├── stakeholders-and-concerns.md
    ├── architecture-states/
    │   ├── README.md
    │   ├── architecture-version-register.md
    │   ├── baseline-architecture.md
    │   ├── target-architecture.md
    │   ├── transition-architectures.md
    │   └── gap-analysis.md
    ├── business/
    ├── information-systems/
    ├── technology/
    ├── security/
    ├── implementation-migration/
    ├── governance/
    └── views/
```

---

## Critical Rule: How Links Work in Docsify

> **This is the most common source of broken links. Read carefully.**

Docsify resolves all Markdown links relative to the **docs root**, not relative to the file that contains the link.

### ✅ Correct — absolute from docs root

```markdown
[Business Architecture](/architecture/business/README)
[Artifact Register](/architecture/artifact-register)
```

### ❌ Wrong — relative to the file (will 404)

```markdown
[Business Architecture](business/README)          <!-- missing architecture/ prefix -->
[Artifact Register](../artifact-register)         <!-- ../  breaks in Docsify -->
```

### Rule for sidebar links (`_sidebar.md`)

Never use `./` prefix in sidebar links. Write paths directly from the docs root:

```markdown
* [Architecture Repository](/architecture/README)   ✅
* [Architecture Repository](./architecture/README) ❌
```

---

## How to Add a New Page

1. Create a new `.md` file in the appropriate `docs/architecture/` subfolder.
2. Write the content in Markdown.
3. Add a link to `docs/_sidebar.md` using the absolute path from the docs root.
4. If the page links to other pages, use absolute paths from the docs root (see rule above).
5. Commit to `master`. The change appears on the live site within a few minutes.

**Example:** Adding a new "Integration Patterns" page under Information Systems:

1. Create `docs/architecture/information-systems/integration-patterns.md`
2. Add to `_sidebar.md`:
   ```markdown
   * [Integration Patterns](/architecture/information-systems/integration-patterns)
   ```
3. Link from other pages using:
   ```markdown
   [Integration Patterns](/architecture/information-systems/integration-patterns)
   ```

---

## How to Edit Files on GitHub

The easiest way to edit content is directly in the GitHub web editor:

1. Navigate to the file in the repository (e.g., `docs/architecture/business/README.md`)
2. Click the **pencil icon** (Edit this file) in the top-right of the file view
3. Make your changes
4. Click **"Commit changes..."** (top right)
5. Add a short commit message describing what you changed
6. Click **"Commit changes"** in the dialog

> **Tip:** You can also press `e` on any file page to open it in the editor.

---

## How to Preview Locally

If you want to preview the site before pushing to GitHub:

```bash
# Install Docsify CLI (one-time)
npm install -g docsify-cli

# Serve the docs folder
npx docsify-cli serve docs

# Open in browser
# http://localhost:3000
```

---

## Troubleshooting

| Problem | Likely cause | Fix |
|---|---|---|
| Link gives 404 | Path is relative to file, not docs root | Prefix the path with `architecture/` (or the correct root-relative path) |
| Sidebar link 404 | `./` prefix in `_sidebar.md` | Remove the `./` prefix |
| Changes not visible | GitHub Pages CDN cache | Wait 2–5 minutes and hard-refresh (`Cmd+Shift+R` / `Ctrl+Shift+R`) |
| New page not in nav | Missing entry in `_sidebar.md` | Add the link to `_sidebar.md` |
| Page shows blank | File not committed or wrong filename casing | Check commit history and exact filename |

---

## Key Files Reference

| File | Purpose |
|---|---|
| `docs/index.html` | Docsify configuration (theme, plugins, settings) |
| `docs/README.md` | Home page — shown when visiting the site root |
| `docs/_sidebar.md` | Navigation sidebar — all section and page links |
| `docs/contributing.md` | This guide — how to contribute and maintain the site |
| `docs/architecture/README.md` | Architecture repository index and version history |
| `docs/architecture/artifact-register.md` | Complete list of all architecture artifacts and their status |
