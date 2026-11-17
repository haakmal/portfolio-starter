# Design Portfolio Starter

A minimal, professional Hugo portfolio for design students. **You can publish your first site using GitHub in a browser.** You do not need to know HTML, CSS or JavaScript. The starter is yours to change, extend or completely redesign.

This is a starter repository, not a content-management service. GitHub holds your files, keeps a record of changes and publishes the site through GitHub Actions and Pages.

## Start here — publish without installing software

1. Create a free GitHub account and sign in.
2. On the starter repository, select **Use this template → Create a new repository** (not *Fork*). Name it `yourusername.github.io` for a personal site or any name for a project site. Make the repository **Public** if you are using GitHub Pages on a plan that requires it. Don't put private information into a public repository.
3. Open **Settings → Pages** in your new repository. Under **Build and deployment**, choose **GitHub Actions** as the source.
4. Open the **Actions** tab. The `Publish portfolio` workflow runs when changes are pushed to `main`. If no run appears, choose the workflow and **Run workflow**. Allow Actions if GitHub asks.
5. Wait until the workflow shows a green check. Return to **Settings → Pages** to find your public site URL. The first build can take a few minutes.
6. In the repository, open `data/profile.yaml`, select the pencil icon, edit your name and introduction, and **Commit changes** to `main`. A new deployment should start automatically.

**If you cannot see “Use this template”:** the original repository owner must enable *Template repository* in its settings. If Pages cannot be configured, check repository visibility and permissions before proceeding.

## Edit your portfolio

| You want to… | Edit this file or folder | How |
| --- | --- | --- |
| Change your name, introduction, email or links | `data/profile.yaml` | Edit quoted text; keep the YAML keys and indentation. |
| Edit your About page | `content/about.md` | Edit Markdown below the second `---` line. |
| Add a project | `content/work/` | Copy an example project folder; rename it; edit `index.md`. |
| Add project images | Your project's folder | Upload an image beside `index.md`; reference it using Markdown. |
| Change project ordering | Project `index.md` | Change `weight: 1`, `weight: 2`, etc. Lower numbers appear first. |
| Hide unfinished work | Project `index.md` | Set `draft: true` until it is ready. |
| Change fonts, colours or spacing | `assets/css/main.css` | Optional; start with the variables under `:root`. |

### Example project structure

```text
content/work/my-project/
  index.md
  cover.jpg
  process-01.jpg
```

Edit the `index.md` front matter:

```yaml
---
title: "My Project"
description: "One sentence about the work."
date: 2026-11-17
draft: false
weight: 1
featured: true
cover: "cover.jpg"
role: "Research and prototyping"
year: "2026"
---
```

Below the closing `---`, write in Markdown. For example, `## Context`, `## Approach`, `## Outcome`, and `## Reflection`. These are suggestions, not mandatory headings. To include an image stored beside the project file, write `![A description of the image](process-01.jpg)`.

**Images:** Use short lowercase filenames without spaces. Keep files reasonably sized (for example, compress large photographs before uploading). Write meaningful alternative text for informative images. Do not publish other people's work without permission or attribution.

### Editing in GitHub

Select a file → pencil icon → edit → **Commit changes**. GitHub stores a version history. For a new project, use **Add file → Create new file** to create `content/work/my-project/index.md`; use **Add file → Upload files** to add images in that same folder. GitHub's browser interface does not create empty folders, so folders appear when you create files inside them.

## What NOT to edit (at first)

| Location | Why it exists | Guidance |
| --- | --- | --- |
| `.github/workflows/deploy.yml` | Builds and publishes the site | **Do not edit** unless you understand GitHub Actions. |
| `layouts/` | HTML page structure | Leave alone for the beginner pathway. |
| `hugo.toml` | Hugo site configuration | Do not change `baseURL` for normal GitHub Pages deployment; Actions sets it automatically. |
| `.gitignore` | Excludes generated files | Leave as supplied. |
| `public/`, `resources/` | Generated Hugo output | Do not edit or commit; these are rebuilt. |
| `assets/css/main.css` | Visual styling | Optional; changing it is not required to publish. |

**Safe editing rule:** Start with `data/profile.yaml`, `content/about.md`, and `content/work/`. Keep the YAML `---` delimiters, colons, quotes and indentation intact. Never publish passwords, student records, private client data or confidential research.

## Troubleshooting publishing

| What you see | Likely cause | What to do |
| --- | --- | --- |
| No public site / 404 immediately after setup | Pages not enabled, workflow hasn't run, or deployment pending | Set **Settings → Pages → Source: GitHub Actions**; check the Actions tab and wait for deployment. |
| Workflow did not start | Commit not on `main`, Actions disabled, or branch name differs | Check branch and Actions permissions; use **Run workflow** to test. |
| Red X on Actions build | YAML or Markdown front matter error, missing file, or Hugo build error | Open the failed workflow → **Build site** step; read the first error and locate the file/line. |
| Site loads without styling | Incorrect Pages URL or base path | Confirm Pages is using the supplied Actions workflow; don't hardcode root-relative asset paths. |
| A project does not appear | `draft: true`, wrong folder, or incorrect filename | Set `draft: false`; use `content/work/project-name/index.md`. |
| Project cover missing | Filename doesn't match `cover` | Check spelling, extension and letter case, e.g. `cover.jpg` vs `Cover.JPG`. |
| Text looks broken after editing YAML | Missing quote, colon or closing `---` | Compare with the example project; restore the last working version from **History**. |
| Changes not visible | Workflow still running, browser cache, or wrong branch | Wait for a green deployment, refresh the page and check `main`. |
| GitHub refuses a commit | Permissions or conflicting edits | Check that you own the repository and are editing the intended branch; review GitHub's conflict message before overwriting anything. |

**Recover a mistake:** Open the file → **History** → inspect a previous version. Copy its content back into the file and commit the correction. Do not delete the repository to fix a broken page. For larger changes, create a branch first so you can review changes before merging.

## Optional: work locally

Install Git, Hugo Extended and a code editor. Then:

```sh
git clone https://github.com/YOUR-USERNAME/YOUR-REPOSITORY.git
cd YOUR-REPOSITORY
hugo server -D
```

Open `http://localhost:1313/`. When ready, commit and push your changes. Use `hugo --gc --minify` to check a production build. Local development is optional, not a requirement for publishing.

## More guidance

A separate **Building Your Design Portfolio with Hugo and GitHub** tutorial series is planned for the Interaction Hub. It will explain GitHub, Markdown, case studies, publishing, recovery and optional CSS/HTML customisation step by step. This repository README remains the immediate starting point.

## License and ownership

The starter code is offered under the MIT License (see `LICENSE`). Your own writing, images, designs and case studies remain yours; the starter license does not grant rights to other people's content.
