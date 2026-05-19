# Yuan-Hao Jiang Academic Homepage

This repository contains the source code and content for [yuanhao-cs.github.io](https://yuanhao-cs.github.io/), a Jekyll-based personal academic homepage.

## Local preview

Install dependencies and start the local server:

```bash
bundle install
bundle exec jekyll serve
```

Then open `http://127.0.0.1:4000`.

To generate the static site without starting the server:

```bash
bundle exec jekyll build
```

The generated site will be written to `_site/`.

## Repository structure

- `_data/profile.yml`: profile, portrait, affiliation, awards, service, footer
- `_publications/`: publication entries shown on the homepage and publications page
- `_news/`: homepage news items
- `assets/PDF/`: local paper PDFs
- `assets/images/covers/`: publication cover images
- `assets/images/photos/`: profile photos
- `assets/results/gs_data_shieldsio.json`: Google Scholar citation badge data
- `google_scholar_crawler/`: helper script for refreshing Google Scholar cache files

## How to update content

### Update the homepage portrait

1. Put the new image under `assets/images/photos/`
2. Update `portrait_url` in `_data/profile.yml`

### Add or update a publication

1. Create or edit a Markdown file under `_publications/<year>/`
2. Fill in the front matter fields used by the site:
   - `title`
   - `date`
   - `selected`
   - `abbr`
   - `label`
   - `pub_pre`
   - `pub`
   - `pub_date`
   - `abstract`
   - `cover`
   - `authors`
   - `PDF`
   - `HTML`
   - `CODE_OR_DATASET`
   - `BIB`
3. Put the PDF in `assets/PDF/`
4. Put the cover image in `assets/images/covers/`

### Add or update a news item

1. Create or edit a Markdown file under `_news/`
2. Use a short homepage-friendly sentence
3. Add a precise `date` so homepage ordering is correct

### Update Google Scholar citations

If only the badge number needs to change, edit:

`assets/results/gs_data_shieldsio.json`

If you want to refresh the cached Scholar data programmatically, use the script in `google_scholar_crawler/`.

## Conventions used in this repo

- Version tags use `vYYYYMMDD`
- Date-based naming uses 8 digits
- `CORE-` labels should stay uppercase
- Homepage-selected papers use `selected: true`

## Suggested publication asset naming

Use stable, sortable filenames such as:

- `assets/PDF/2026-1_jia_slam.pdf`
- `assets/images/covers/2026-1_jia_slam.png`
- `_publications/2026/2026-1_jia_slam.md`
