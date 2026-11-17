# Case-study template

A case study is not a fixed formula. It is a way to show what you investigated, what you made, how you made decisions and what you learned. Adapt or remove the suggested headings to suit applied, critical, speculative, material-led or research-led work.

## Create a project

In GitHub, create `content/work/your-project/index.md` and paste the example below. Replace the placeholders and commit. Upload the cover image into the same folder; the `cover` value must match the filename.

```markdown
---
title: "Your Project Title"
description: "One sentence about the project."
date: 2026-11-17
draft: true
weight: 3
featured: false
cover: "cover.jpg"
cover_alt: "A prototype on a table showing its physical controls"
role: "Research, design and prototyping"
year: "2026"
---

Introduce the project in your own voice. What is the proposition?

## Context

What prompted this work? What problem, possibility or question did you explore?

## Process

What did you investigate, test, sketch, prototype or reconsider? Show evidence.

![A descriptive explanation of this process photograph](process-01.jpg)

## Outcome

What resulted? Describe what it does, what it means, or what it proposes.

## Reflection

What changed in your thinking? What remains unresolved?
```

## Practical conventions

- `draft: true` keeps unfinished projects off the published website. Change it to `false` when ready.
- `featured: true` makes the project eligible for the homepage's selected work.
- `weight` controls the order (smaller numbers first). Avoid using the same weight for every project.
- `cover` refers to a file beside `index.md`. If you have no cover yet, remove the `cover:` property or leave it empty; the card uses a placeholder.
- `cover_alt` describes the cover's meaningful content. For decorative images, use suitable empty alternative text where appropriate.
- `role` and `year` are optional project details.
- Markdown images use a filename relative to the page bundle, for example `![Prototype interface](interface.jpg)`.

## Professional practice

Credit collaborators, describe your role accurately, and distinguish group outcomes from your individual contribution. Do not publish client secrets, confidential data or images of participants without appropriate permission. If a project cannot be shown publicly, describe your process at an appropriate level or keep it private.

A useful case study is not necessarily long. Clear images, decisions and reflection are often more valuable than exhaustive documentation.
