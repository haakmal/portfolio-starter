# Make the portfolio your own

This starter is a starting point, not a design system you must keep. You own the repository and may change **any** part of the site. The options below help you begin without editing code.

## Start with `data/design.yaml`

In GitHub, open `data/design.yaml`, select the pencil icon, edit the values, then select **Commit changes**. GitHub Actions will rebuild your site. Check the **Actions** tab for a green check before refreshing the public site.

```yaml
accent: "#465FE8"
accent_text: "#FFFFFF"
font_pair: grotesk
work_layout: grid
hero_graphic:
  enabled: true
  image: ""
  alt: ""
```

### Accent colour

- `accent` accepts any **six-digit HEX colour**, such as `"#465FE8"`, `"#D5F45A"`, or `"#F27A61"`.
- `accent_text` controls the colour of text **on** accent-coloured buttons. Choose `"#FFFFFF"` (white) or `"#151515"` (dark) according to contrast.
- Keep the `#`, quotation marks, colons and indentation. A malformed HEX colour safely falls back to cobalt, but malformed YAML may prevent Hugo from building.
- Check text contrast, keyboard focus and links after changing colours. A pale accent usually needs dark text.

### Optional homepage graphic

The default geometric illustration is not compulsory. You can keep it, replace it with your own artwork, or remove it without touching HTML or CSS.

In `data/design.yaml`:

```yaml
hero_graphic:
  enabled: true
  image: ""
  alt: ""
```

- **Keep the original:** leave `enabled: true` and `image: ""`. The built-in SVG automatically uses your accent colour.
- **Use your own artwork:** upload a JPG, PNG, WebP or SVG into `static/images/` in GitHub, then set `image: "images/my-artwork.jpg"`. Match the filename exactly, including uppercase/lowercase. The image fits within the existing hero frame without cropping.
- **Remove the graphic:** change `enabled: false` (without quotation marks). The frame disappears and the introduction expands to use the available space. You can leave the image path in place for later.
- **Accessibility:** if the image conveys information, write a short description in `alt`. If it is purely decorative, keep `alt: ""`.

**Paths are relative to `static/`.** For example, `static/images/hero.webp` is written as `images/hero.webp`. Do not include `static/` or a leading slash. This ensures links work when GitHub Pages hosts the site under a repository subpath.

If the image is missing or the path is invalid, the site falls back to the original motif and Hugo writes a warning during the build. Use an image you have permission to publish and compress large files before uploading.

Students who want to alter the frame, dimensions or layout can use `assets/css/custom.css`, or change `layouts/index.html` directly.

### Typeface pairing

Change `font_pair` to one of these values (without quotes):

| Value | Headings | Body | Character |
| --- | --- | --- | --- |
| `grotesk` | Space Grotesk | DM Sans | Contemporary, precise (default) |
| `studio` | Archivo | DM Sans | Direct, confident |
| `humanist` | Manrope | Source Sans 3 | Friendly, highly readable |
| `contrast` | Fraunces | DM Sans | Expressive editorial contrast |
| `system` | Your device's system sans | Your device's system sans | Fast, no external font requests |

The first four choices load open-source typefaces from **Google Fonts** when online; system fonts provide fallbacks if the request fails. No font files are bundled with the starter. Use `system` if you prefer not to load third-party fonts. Open `docs/typeface-preview.html` in a browser to compare the five options.

### Project layout

- `work_layout: grid` — a two-column project grid on larger screens, one column on phones.
- `work_layout: list` — a vertical editorial index with images beside descriptions on larger screens.

Both layouts preserve the same case studies, order and mobile behaviour. There is no introduction alignment setting; the default is intentionally left-aligned.

## Want to go beyond the options?

You are free to change the design, even if that means ignoring the preset system completely. There are two supported routes:

1. **Override the design:** edit `assets/css/custom.css`. It loads after the main stylesheet and after the colour variables generated from `design.yaml`.
2. **Redesign the site:** edit `assets/css/main.css` and the HTML templates in `layouts/`. This is optional and requires some HTML/CSS knowledge.

Example `assets/css/custom.css`:

```css
/* Custom colours and content width */
:root {
  --accent: #D5F45A;
  --accent-ink: #151515;
  --page-width: 1500px;
}

/* Override the chosen font pairing (higher specificity than the preset). */
body[class] {
  --font-head: Georgia, serif;
  --font-body: Arial, sans-serif;
}

/* Make the cards less rigid */
.project-image { border-width: 1px; }
```

The starter does not prevent you from adding new page layouts, scripts, custom fonts, animations or other CSS. Advanced edits should be committed on a branch first, so you can compare them with the working site.

## What not to edit initially

The browser-first publishing workflow needs these files to remain intact:

| File or folder | Beginner guidance |
| --- | --- |
| `.github/workflows/deploy.yml` | Do not edit. Publishes your site. |
| `hugo.toml` | Do not change `baseURL` for ordinary GitHub Pages use; Actions supplies it. |
| `layouts/` | Optional advanced editing; changing Hugo templates can break builds. |
| `assets/css/main.css` | Optional advanced editing; start with `data/design.yaml` instead. |
| `.gitignore` | Leave intact so generated output is not committed. |
| `public/`, `resources/` | Generated files; do not edit or commit. |

You **can** edit these files if you understand what they do. The table is a safeguard for beginners, not a restriction on ownership.

## Troubleshooting

| Problem | What to check |
| --- | --- |
| Changes not visible | Confirm the latest GitHub Actions run is green; refresh the public site. |
| Red X on Actions | Open the failed run → **Build site** → first error. Check YAML indentation, quotes and the file named in the error. |
| Accent looks unchanged | Confirm you edited `data/design.yaml` on `main`, used a six-digit HEX value and committed. Check for overrides in `assets/css/custom.css`. |
| Buttons are difficult to read | Set `accent_text` to dark for a light accent, or white for a dark accent. Check contrast manually. |
| Hero image is missing | Check that `enabled: true`, the file is in `static/images/`, and `image:` uses its exact path without `static/`. Review the GitHub Actions build warnings. |
| Hero frame remains after disabling | Check that `enabled: false` is indented under `hero_graphic:` and is not in quotation marks. |
| Typeface looks unchanged | Check the spelling of `font_pair`, internet access and any browser font-blocking settings. The site uses local fallback fonts offline. |
| List/grid setting has no effect | Confirm `work_layout` is `grid` or `list`. Check for a conflicting custom CSS rule. |
| CSS changes appear to break the site | Temporarily empty `assets/css/custom.css`, commit and test again. Restore a previous file version using GitHub History if needed. |
| Site fails after editing a template | Use GitHub file History to restore the last working version; don't delete the repository. |

See the repository README for general GitHub Pages and publishing troubleshooting. The longer Interaction Hub tutorial series will explain these concepts step by step.
