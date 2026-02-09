# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Personal portfolio and CV site for a DevOps Engineer, hosted on GitHub Pages at www.hamzarazzaq.com. The site serves a PDF resume via an embedded iframe.

## Architecture

- **`index.html`** — GitHub Pages entry point; embeds the PDF resume in a full-page iframe
- **`develop.tex`** — Working/draft LaTeX CV using the `moderncv` package (banking style). Edit this file for CV changes.
- **`production.tex`** — Finalized LaTeX CV. Sync from `develop.tex` when changes are ready.
- **`Hamza_Razzaq_DevOps.pdf`** — Compiled PDF served by the site
- **`CNAME`** — Custom domain config (`www.hamzarazzaq.com`)

## LaTeX Build

No build tooling is configured in the repo. Compile the CV with:

```
pdflatex develop.tex
```

Key packages used: `moderncv`, `tikz`, `graphicx`, `multicol`, `enumitem`, `fontawesome` (via moderncv).

## Deployment

Push to `main` branch — GitHub Pages serves automatically. After compiling a new PDF, replace `Hamza_Razzaq_DevOps.pdf` and push.

## CV Conventions

- The `\customcventry` command handles experience entries (title, date, company, location, description)
- Profile photo is included as a square image (`photo.jpg`) via `\includegraphics` — no circular clipping
- Contact info uses FontAwesome icons (`\faMobile`, `\faEnvelope`, `\faLinkedin`, `\faHome`, `\faCalendar`)
- The CV targets European relocation — summary emphasizes career progression narrative over raw metrics
