# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Build Commands

```bash
# Compile PDF (recommended — handles bibliography and re-runs automatically)
latexmk -pdf main.tex

# Quick single-pass compile
pdflatex main.tex

# Clean build artifacts (keeps PDF)
latexmk -c

# Full clean including PDF
latexmk -C
```

## Project Structure

This is a LaTeX thesis: **UrbanPulse — Streaming Platform for Live City Activity and Anomaly Detection** by Chau Thinh (ITCSIU22240), International University, Ho Chi Minh City.

- `main.tex` — preamble, title page, abstract, and chapter includes. All document-wide settings (geometry, packages, custom commands) live here.
- `chapters/` — one `.tex` file per chapter, included via `\input{}` in `main.tex`. Chapter order: Introduction → Related Work → Methodology → Prototyping → Implementation → Result → Discussion → Conclusion → Appendix (Listings).
- `images/` — all figures; referenced with bare filename (no path prefix) because `\graphicspath{{images/}}` is set in `main.tex`.
- `bibliography.bib` — BibTeX references, style `ieeetr`.

## Key LaTeX Conventions

- Custom commands defined in `main.tex`: `\cmark` (✓) and `\xmark` (✗) from `pifont`.
- JavaScript listings use a custom `lstdefinelanguage{JavaScript}` block in `main.tex`; Python uses the built-in `listings` support.
- Appendix chapter labeling uses a custom `\appendix` override so chapters appear as "Appendix A", "Appendix B", etc.
- Page numbering: Roman numerals for front matter, Arabic from Chapter 1 (`\pagenumbering{arabic}` + `\setcounter{page}{1}` inside `main.tex` at the Introduction chapter).
- Bibliography label: renamed from "Bibliography" to "References" via `\renewcommand{\bibname}{References}`.
