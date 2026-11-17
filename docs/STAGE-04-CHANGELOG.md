# Stage 04 — Arrow typography consistency

An overlay patch for the Stage 03 Portfolio Starter (Editorial Signal).
No files are removed. All arrow characters and layout treatments are retained.

## Files replaced

- `assets/css/main.css`
- `layouts/index.html`
- `layouts/_default/baseof.html`
- `layouts/_default/single.html`
- `layouts/work/single.html`
- `layouts/partials/project-card.html`

## Files added

- `docs/STAGE-04-CHANGELOG.md`
- `PATCH-MANIFEST.txt`

## Behaviour

- Decorative arrows in buttons, navigation, project cards, links and footer use `.ui-arrow`.
- The glyphs retain their current characters (↗, ←, ↑) but render with `system-ui`.
- `font_pair` in `data/design.yaml` still controls all other typography.
- Existing project arrow borders, accent backgrounds, hover states and spacing remain unchanged.
- Advanced students can override `.ui-arrow` in `assets/css/custom.css`.

## Apply from repository root on a clean branch

```sh
tar -xzf ~/Downloads/portfolio-starter-stage-04-arrows.tar.gz -C .
git diff --check
hugo server -D
hugo --gc --minify
```

## Browser checks

Check homepage CTA, View all work, project cards, Contact, About email/social links,
Back to Work, and Back to top. Change `font_pair` between `grotesk` and `contrast`
and verify that the arrow glyphs remain visually consistent.

## Commit

```sh
git add assets/css/main.css layouts/ docs/STAGE-04-CHANGELOG.md PATCH-MANIFEST.txt
git commit -m "stage-04: standardise interface arrow typography"
```

This is a non-destructive overlay patch; Git history is retained.
