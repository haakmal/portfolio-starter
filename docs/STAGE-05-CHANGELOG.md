# Stage 05 — Optional homepage graphic

A focused incremental update to the Stage 04 Editorial Signal portfolio.

- Added `hero_graphic.enabled`, `hero_graphic.image`, and `hero_graphic.alt` to `data/design.yaml`.
- Retained the original accent-aware SVG as the default (no visual change with default settings).
- Allowed a custom JPG, PNG, WebP or SVG uploaded to `static/images/` to replace the default.
- Hiding the graphic removes the frame and lets the introduction use the available width on desktop and mobile.
- Updated README, safe-editing, customisation and troubleshooting guidance.
- Did not modify typefaces, arrows, projects, other page layouts or GitHub Actions.

## Test

1. Run `hugo server -D` with the default settings and verify the original motif.
2. Set `hero_graphic.enabled: false` and check desktop/mobile layouts.
3. Set it back to true, upload an image to `static/images/`, and set `image:` to its relative path.
4. Confirm the image is not cropped and that a missing path warns and falls back.
5. Run `hugo --gc --minify`, review the diff, and commit.

This is an overlay patch preserving Git history; no files are deleted.
