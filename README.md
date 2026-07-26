# luke18.github.io

Personal academic homepage of Tao Sun (孙弢) — Associate Professor (Tenure-Track),
School of Electrical Engineering, Shanghai Jiao Tong University.

Live at **https://luke18.github.io/**

## Design

A deliberately lightweight, dependency-free static site: two hand-written HTML pages
and one CSS file. No build step, no framework, no JavaScript.

- `index.html` — single-page homepage (Biography, Research Interests & Openings, News,
  Selected Publications, Teaching)
- `publications.html` — full publication list grouped by year (currently not linked
  from the homepage)
- `assets/css/style.css` — all styling
- `assets/img/`, `assets/pdf/` — photo, paper PDFs, CV
- `data/papers.bib` — BibTeX source of record for publications (not served)

## Local preview

Open `index.html` directly in a browser, or serve the folder:

```sh
uv run python -m http.server 8000
```

## Deployment

Pushing to `main` triggers `.github/workflows/deploy.yml`, which copies the site files
to the `gh-pages` branch (the GitHub Pages source for this repo).

See `CLAUDE.md` for maintenance conventions.
