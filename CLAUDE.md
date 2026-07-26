# CLAUDE.md

Guidance for Claude Code when working in this repository.

## What this is

The personal academic homepage of Tao Sun (孙弢), Associate Professor (Tenure-Track),
School of Electrical Engineering, Shanghai Jiao Tong University. Published at
https://luke18.github.io/ via GitHub Pages.

It is a **deliberately lightweight static site**: two hand-written HTML pages and one
CSS file. No framework, no build step, no JavaScript, no external dependencies
(fonts and icons are system/inline). Keep it that way — do not introduce Jekyll,
npm packages, CDNs, or build tooling.

## Commands

- **Local preview**: open `index.html` directly in a browser (all paths are relative,
  so `file://` works), or serve with `uv run python -m http.server 8000`.
- **Python**: always use `uv` (`uv run`, `uv add`) — never bare `pip`/`python`.
- **Deploy**: push to `main`; `.github/workflows/deploy.yml` copies the site to the
  `gh-pages` branch, which is the GitHub Pages source. Do not commit or push unless asked.

## Folder structure

```
.
├── .claude/
│   └── settings.json        # Claude Code project permissions
├── .github/
│   └── workflows/
│       └── deploy.yml       # copies static files to gh-pages on push to main
├── assets/
│   ├── css/style.css        # all site styling (single stylesheet)
│   ├── img/                 # photos (job_photo.png is the homepage portrait) + favicon.ico
│   └── pdf/                 # paper PDFs + CV (clean kebab-case names, e.g. sun2025-...)
├── data/
│   └── papers.bib           # BibTeX source of record for publications (not served)
├── index.html               # homepage: Biography · Research & Openings · News ·
│                            #   Selected Publications · Teaching
├── publications.html        # full publication list by year (kept, but NOT linked
│                            #   from the homepage — owner prefers Google Scholar)
├── .nojekyll                # tells GitHub Pages not to run Jekyll
├── robots.txt
├── CLAUDE.md
└── README.md
```

## Conventions

- **Content edits** happen directly in `index.html` / `publications.html`; styling in
  `assets/css/style.css`. Keep all asset paths **relative** so `file://` viewing works.
- **News**: add new items to the top of the News list in `index.html` with a
  `<span class="date">Mon YYYY</span>` prefix.
- **Publications**: `data/papers.bib` is the source of record. When adding a paper,
  update the bib file, add the entry to `publications.html` (under its year), and — if
  it is a highlight — to Selected Publications in `index.html`. Write authors with
  full names; bold the site owner's with `<span class="me">Tao Sun</span>`. Name PDFs
  `firstauthorYYYY-venue-shortslug.pdf`.
- **Style**: single accent color (`--accent`, SJTU red) defined in `:root`; serif
  headings, sans-serif body. Preserve the clean, minimal look.
- **Maintain this file**: update CLAUDE.md when the project structure or conventions
  change (new pages, moved folders, new tooling). Do not log routine content edits
  (news items, publications) here.
