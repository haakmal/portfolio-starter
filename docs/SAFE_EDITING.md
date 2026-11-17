# Safe editing: understanding your portfolio files

The repository is a folder of source files that Hugo turns into a website. **GitHub is the editor and version history; GitHub Actions builds the site; GitHub Pages publishes it.**

## Green light: edit these first

| Location | What it changes | Common mistake |
| --- | --- | --- |
| `data/profile.yaml` | Name, role, introduction, email and links | Deleting quotation marks or breaking indentation |
| `data/design.yaml` | Accent, text contrast, fonts and Work layout | Invalid HEX colour or unknown font option |
| `content/about.md` | Your About page | Accidentally removing the opening/closing `---` |
| `content/work/` | Project case studies | Creating `my-project.md` instead of `my-project/index.md` |
| Project image files | Covers and documentation | Filename doesn't match `cover:` or image link |
| `assets/css/custom.css` | Optional CSS experiments | An override that hides text or reduces contrast |

**Avoid changing these at first:** `.github/workflows/deploy.yml`, `hugo.toml`, `layouts/`, `assets/css/main.css` and `.gitignore`. Do not edit or commit generated `public/` or `resources/` directories. These files aren't forbidden; they are advanced parts of the system.

## How a page works

A Markdown file usually begins with **front matter** between two `---` lines. These are properties Hugo reads:

```yaml
---
title: "A Project About Interaction"
description: "One sentence describing the work."
date: 2026-01-01
draft: true
weight: 1
featured: true
cover: "cover.jpg"
role: "Research and prototyping"
year: "2026"
---
```

Everything after the second `---` is the page body. The YAML property names and indentation are structural. Change the values, not the names. A colon inside ordinary text should be quoted, for example `description: "Research: early findings"`.

`draft: true` hides the project from normal production builds. Set `draft: false` when ready. `featured: true` includes the project among homepage selections; if no projects are featured, the homepage uses the first projects by weight. Lower `weight` numbers appear first.

## Creating a project folder in GitHub

GitHub's browser interface cannot create empty folders. In `content/work/`, use **Add file → Create new file**, enter `my-project/index.md`, paste the case-study template and commit. The new folder appears with its file. Upload images into that same folder using **Add file → Upload files**.

If GitHub's interface places the file in the wrong folder, check its breadcrumb before committing. Never overwrite another project's `index.md`.

## Commit, check, correct

1. Select **Edit** on a file, make a small change, then choose **Commit changes**.
2. Confirm the commit is on `main` if you want it published immediately.
3. In **Actions**, check that **Publish portfolio** completes successfully.
4. Visit the public site. If the change isn't there yet, check the workflow before editing again.
5. To correct a mistake, open the file's **History**, inspect an earlier version, copy the correct content into the current file and commit. Avoid force-pushing or deleting the repository.

For larger changes, use a separate branch and compare before merging. Never place passwords, private client material, identifiable research participants or unpublished confidential work in a public repository.
