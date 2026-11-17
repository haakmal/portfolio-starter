# Publishing and editing troubleshooting

GitHub Pages does not publish a Hugo source repository directly. The supplied **Publish portfolio** GitHub Actions workflow builds the site and sends the result to GitHub Pages.

## Start here: where did it fail?

1. Open your repository's **Actions** tab.
2. Select the latest **Publish portfolio** run.
3. If it is red, open the failed job and expand the first failed step. Read the first meaningful error, including any file path and line number.
4. If the build is green but the website is wrong, open **Settings → Pages** and confirm the live URL and deployment source.
5. Check the latest commit on `main` matches the changes you expect.

## Common problems

| Symptom | Likely cause | What to do |
| --- | --- | --- |
| No Actions run after editing | Changes committed to a different branch, or Actions disabled | Check branch selector and repository Actions settings. The supplied workflow runs on pushes to `main`; use **Run workflow** for a manual run. |
| Pages is unavailable or 404 | Pages source not configured or deployment not complete | Set **Settings → Pages → Build and deployment → GitHub Actions**. Check for a successful **Deploy** job and wait a few minutes. |
| Build job is red | Invalid YAML, broken Markdown front matter or Hugo template edit | Expand **Build site** and read the first error. Correct the named file and commit again. |
| Deploy job is red but Build succeeded | Pages permissions, Pages settings or organisation policy | Confirm Pages uses GitHub Actions and the workflow has permissions. If managed by an organisation, ask its administrator about policy restrictions. |
| Site loads without CSS | Wrong deployment URL, failed asset path or edited template | Use the Pages URL shown in settings. Avoid editing `hugo.toml` or hardcoding URLs; the workflow sets the base URL. |
| Project missing from Work | Draft, wrong folder, or not committed | Use `content/work/project-name/index.md`, set `draft: false`, commit to `main`, and wait for a green build. |
| Image missing | File not uploaded or filename mismatch | Confirm the image is beside `index.md`, then match `cover: "cover.jpg"` exactly (including case). |
| New content not visible | Build still running, wrong branch, or cached page | Check the latest successful run and its commit, then refresh or use a private window. |
| Font looks different | Google Fonts blocked or offline, or wrong setting | Check `font_pair` spelling; the site uses fallbacks. Use `font_pair: system` to avoid external font requests. |
| Button text unreadable | Accent and text colours have poor contrast | Change `accent_text` to a readable dark or light value; test on mobile too. |
| GitHub asks about a conflict | Another change happened before yours | Review both versions; avoid blindly overwriting someone else's edits or force-pushing. |

## YAML errors

Front matter must start and end with `---`. Values containing a colon should be quoted. Lists need consistent indentation. Compare your file with a working example project. A YAML parse error may identify the line after the actual mistake.

```yaml
---
title: "My Project: An Experiment"
draft: false
cover: "cover.jpg"
---
```

## Recover a previous version

For one file, open its **History**, inspect the last working version and copy the correct content into the current file, then commit. For a larger change, inspect the relevant commits or ask for help before reverting. Avoid deleting the repository or force-pushing as a first response.

If you work locally, `git status`, `git log --oneline -5` and `git diff` can help identify uncommitted or recent changes. Do not use destructive Git commands without understanding which work they will discard.

## What to include when asking for help

Share the page URL (if public), the **first meaningful error** from the Actions build log, the affected file path, and what you changed. **Never share passwords, access tokens or private research data.**

## Homepage hero graphic is missing or unwanted

In `data/design.yaml`, check the `hero_graphic` block. To remove the graphic, set `enabled: false` (not `"false"`). The introduction should expand without leaving an empty frame.

To replace the graphic, upload the image to `static/images/` and use a path such as `image: "images/your-artwork.jpg"`. Do not include `static/` or a leading slash, and match the filename's capitalisation. If the image is missing, Hugo falls back to the original graphic and logs a warning in GitHub Actions. Add a short `alt` description for meaningful artwork.
