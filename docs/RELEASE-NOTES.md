# Stage 01 — Foundation

- Browser-first Hugo portfolio starter with Home, Work, About and two example case studies.
- Project content lives in Hugo leaf bundles (`content/work/<slug>/index.md` plus images).
- Profile settings live in `data/profile.yaml`; no separate CMS.
- GitHub Actions builds and publishes to Pages, with `baseURL` set from the Pages environment.
- Responsive monochrome editorial CSS, keyboard skip link, reduced-motion support and image alt-text conventions.
- Beginner README with clear safe-edit / do-not-edit boundaries, GitHub editing, publishing, troubleshooting and recovery instructions.

## Test before distribution

1. Run `hugo server -D` and `hugo --gc --minify` with Hugo Extended.
2. Use the GitHub template-repository setting on the upstream repository.
3. Create a test copy through **Use this template** and enable GitHub Actions deployment in Settings → Pages.
4. Change `data/profile.yaml`, create a project, upload images, verify live URLs and check mobile layout.
5. Confirm that a deliberate malformed YAML edit fails visibly in Actions, then restore it through file history.

## Scope boundary

This is the portfolio starter's foundation. The full Interaction Hub tutorial series is a separate content deliverable to be authored against the working starter. No plugin, CMS, npm build or Hugo module is required.
