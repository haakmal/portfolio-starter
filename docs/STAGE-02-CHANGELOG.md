# Stage 02 — Editorial Signal

Incremental overlay for the Stage 01 Portfolio Starter. The repository root remains the Hugo site. **No files are deleted** and no `.git` metadata is included.

## Changes

- Adopted the selected Editorial Signal design: spacious editorial typography, strong but restrained borders, cobalt accents, padded navigation and action controls.
- Added an original geometric homepage composition whose accent inherits the selected colour.
- Improved project cards, Work index, About page, and case-study reading layout while preserving existing Markdown content and page URLs.
- Added `data/design.yaml` with accent, accent text, five typeface pairings and grid/list work layout. The introduction remains left-aligned; there is no alignment setting.
- Added `assets/css/custom.css`, loaded after the starter stylesheet and configuration colours. Students may also edit HTML and CSS directly; there is no enforced preset system.
- Added a standalone font comparison HTML page, customisation guide, and updated beginner README with GitHub Actions troubleshooting.
- No JavaScript dependency, npm build, CMS, or additional publishing service required.

## Installation and checks

From a clean Stage 01 Git repository, create a branch, extract the archive at the repository root, review `git diff`, then run `hugo server -D` and `hugo --gc --minify`.

Inspect Home, Work, About, and both case studies at desktop and mobile widths. Change `font_pair` to each option, then try `work_layout: list`, change the accent, and check keyboard focus and contrast. Return to the desired defaults before committing.

## Design choices

- Default: `accent: "#465FE8"`, `accent_text: "#FFFFFF"`, `font_pair: grotesk`, `work_layout: grid`.
- Font provider: Google Fonts for curated pairings, system fallback if offline; `system` disables external font requests.
- Advanced students may override anything via `assets/css/custom.css` or edit `assets/css/main.css` and `layouts/`.
- No change to `.github/workflows/deploy.yml` or Hugo configuration.
