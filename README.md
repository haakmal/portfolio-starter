# Design Portfolio Starter

A responsive Hugo portfolio for designers. It uses an editorial visual system with strong borders, generous spacing and an adjustable accent. **You can create, edit and publish your portfolio entirely through GitHub's website.** You do not need to install Hugo, Git or a code editor to begin.

This is **your portfolio**, not a course submission system. You own the repository, its content and its design. You can keep the starter appearance, change the settings or rebuild it yourself.

## Get your site online

1. Sign in to [GitHub](https://github.com/) and open the original portfolio starter repository.
2. Select **Use this template → Create a new repository** (not **Fork**). Name it `YOUR-USERNAME.github.io` for a personal site, or choose another name for a project site. Use a **Public** repository for the simplest GitHub Pages setup. **Never publish confidential information.**
3. In your new repository, open **Settings → Pages**. Under **Build and deployment**, choose **GitHub Actions** as the source.
4. Open **Actions** and look for **Publish portfolio**. If there is no run yet, open the workflow and select **Run workflow**. GitHub may first ask you to enable Actions.
5. Wait for the green check. In **Settings → Pages**, open your website address. The first deployment may take a few minutes.
6. Open `data/profile.yaml`, select **Edit** (pencil), replace the example details and **Commit changes** to `main`. A new build should begin automatically.

If the site does not appear, follow [Publishing and troubleshooting](docs/TROUBLESHOOTING.md). **Do not edit the GitHub Actions workflow to fix a missing site until you've checked the settings and build log.**

## What you can safely edit

| Task | File or folder |
| --- | --- |
| Your name, introduction, email and links | [`data/profile.yaml`](data/profile.yaml) |
| Accent colour, fonts, work layout, optional homepage graphic | [`data/design.yaml`](data/design.yaml) |
| Your About page | [`content/about.md`](content/about.md) |
| Project titles, descriptions and case studies | `content/work/PROJECT-NAME/index.md` |
| Project covers and process images | The same project folder as its `index.md` |
| Additional CSS (optional) | [`assets/css/custom.css`](assets/css/custom.css) |

**Start with the first five rows.** The site will build itself after you commit changes. For more detail, read [Safe editing and file map](docs/SAFE_EDITING.md) and [Case-study template](docs/CASE_STUDY_TEMPLATE.md).

## Add a project through GitHub

1. Open `content/work/` and look at one of the example project folders.
2. Choose **Add file → Create new file** in `content/work/` (or create a file from the repository root). Enter `content/work/my-project/index.md` as the filename. GitHub creates the folder when the file is committed.
3. Copy the starter front matter from [the case-study template](docs/CASE_STUDY_TEMPLATE.md). Change its title and description, set `draft: false` when ready, and write your case study below the closing `---` line.
4. Commit the file to `main`. Navigate into `content/work/my-project/`, choose **Add file → Upload files**, and upload `cover.jpg` or other images. The `cover:` filename must match the uploaded file exactly, including capitalisation.
5. Wait for the **Publish portfolio** Action to finish, then check the Work page and your project.

**Markdown** is plain text with simple formatting: `## Heading`, `**bold**`, `[link](https://example.com)` and `![descriptive image text](process-01.jpg)`. Case-study headings are suggestions, not mandatory categories.

## Adjust the design without coding

Edit [`data/design.yaml`](data/design.yaml):

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

Choose `grotesk`, `studio`, `humanist`, `contrast` or `system` for typography. Use `grid` or `list` for the Work page. The homepage graphic is optional: set `hero_graphic.enabled: false` to remove it, or upload your own image to `static/images/` and set `hero_graphic.image: "images/your-artwork.jpg"`. Keep the accent and accent text colours readable together. See [Customisation](docs/CUSTOMISATION.md) for all choices and optional CSS overrides.

## What not to edit yet

| Location | Why |
| --- | --- |
| `.github/workflows/deploy.yml` | Publishes the site automatically; changing it can stop deployment. |
| `hugo.toml` | Hugo configuration; the workflow already sets the correct public URL. |
| `layouts/` | Hugo page templates; beginners do not need to edit HTML. |
| `assets/css/main.css` | Core design rules; use `design.yaml` first. |
| `.gitignore` | Keeps generated files out of the repository. |
| `public/` and `resources/` | Hugo-generated output, not source files. |

These are **safeguards, not restrictions**. Students who want to learn HTML, CSS, JavaScript or Hugo can modify the entire site. Work on a branch first when changing templates or deployment files.

## Before sharing your portfolio

Check the [Publishing checklist](docs/PUBLISHING_CHECKLIST.md): replace example projects, confirm that your contact details are intentional, test mobile and keyboard navigation, describe meaningful images, check colour contrast, and confirm that your latest GitHub Actions deployment succeeded.

For errors, see [Troubleshooting](docs/TROUBLESHOOTING.md), including missing images, failed Actions, YAML mistakes and recovering previous file versions.

## Optional local development

Install Git, Hugo Extended and an editor, then:

```sh
git clone https://github.com/YOUR-USERNAME/YOUR-REPOSITORY.git
cd YOUR-REPOSITORY
hugo server -D
```

Open `http://localhost:1313/`. Run `hugo --gc --minify` to check a production build. Local development is optional; GitHub's browser editor remains a valid authoring workflow.

## Learning documentation

A separate draft tutorial series, **Building Your Design Portfolio with Hugo and GitHub**, is being prepared for the Interaction Hub. It covers GitHub, case studies, media, publishing, maintenance, optional local development and troubleshooting. This README is intentionally the short starting point.

## Ownership and licence

The starter code is MIT-licensed (see `LICENSE`). Your own writing, photographs, designs and case studies remain yours. Check permission and attribution before publishing other people's material.
