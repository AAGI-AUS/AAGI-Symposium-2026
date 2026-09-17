# AAGI Symposium 2026

Official website for the **2026 Australian Analytics for the Australian Grains Industry (AAGI) Symposium**, held **10–12 November 2026** at the QT Hotel Perth, Western Australia.

The site is the central hub for the symposium: the program schedule, workshops, poster showcase, HDR networking session, participant information, and other resources.

## About the Symposium

The annual AAGI Symposium brings together researchers, students and industry collaborators from across Australia to share research, develop new collaborations, and explore the latest advances in data analytics for the grains industry. The 2026 program also includes the inaugural AAGI Awards, recognising outstanding contributions from AAGI members.

## Site Structure

The site is built with [Quarto](https://quarto.org/) as a static website.

- `index.qmd` – homepage
- `program.qmd` – symposium schedule
- `workshops.qmd`, `workshop-*.qmd` – workshop overview and individual workshop pages
- `posters.qmd`, `posters-theme-*.qmd` – poster showcase, split by theme
- `hdr.qmd` – HDR networking session
- `participants.qmd` – participant information
- `resources.qmd` – additional symposium materials and links
- `contact.qmd` – contact details
- `_quarto.yml` – site configuration (navigation, theme, output)
- `styles.css` – custom site styling
- `images/` – site images and logos
- `data/` – supporting data files (e.g. schedule spreadsheet)
- `submitted-posters/` – submitted poster PDFs, organised by theme folder
- `scripts/generate_poster_pages.py` – generates the poster theme pages from PDFs in `submitted-posters/`
- `generate-posters.sh` – convenience script to regenerate poster pages and render the site
- `docs/` – rendered site output (published via GitHub Pages)
- `.github/automation/` – Google Form → GitHub upload automation for poster submissions

## Building the Site Locally

Requires [Quarto](https://quarto.org/docs/get-started/) and Python 3 with `pdftoppm` (from `poppler`) available on the `PATH`.

```bash
# Regenerate poster pages from submitted PDFs and render the full site
./generate-posters.sh
```

Or run the steps individually:

```bash
python3 scripts/generate_poster_pages.py   # regenerate poster theme pages
quarto render                              # render the site into docs/
quarto preview                             # preview the site locally
```


## Deployment

The site is published via GitHub Pages from the `docs/` directory.
