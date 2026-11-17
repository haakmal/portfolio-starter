# Stage 03 — Browser-first onboarding and publishing support

Documentation-only overlay. This increment deliberately does **not** change Hugo templates, CSS, JavaScript, profile settings, project content or GitHub Actions.

## Added
- Concise README focused on first publication and safe editing.
- `docs/SAFE_EDITING.md`: file map, front matter and GitHub editing/recovery.
- `docs/CASE_STUDY_TEMPLATE.md`: adaptable professional case-study scaffold.
- `docs/PUBLISHING_CHECKLIST.md`: content, accessibility and deployment checks.
- `docs/TROUBLESHOOTING.md`: GitHub Actions, Pages, images, YAML and recovery.

The separate draft Interaction Hub tutorial series is distributed in its own archive, not installed into this portfolio repository.

## Verification
1. Confirm all README and documentation links resolve in GitHub.
2. Run `hugo server -D` and `hugo --gc --minify` against the existing Stage 02 site.
3. Check that `git diff` contains documentation files only.
4. Test GitHub's **Use this template** and Pages deployment on a throwaway repository before releasing to students.
