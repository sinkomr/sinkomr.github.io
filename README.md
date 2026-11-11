# Michael R Sinko PhD — michaelsinko.phd

Hugo source for [michaelsinko.phd](https://michaelsinko.phd/), built with the [PaperMod](https://github.com/adityatelange/hugo-PaperMod) theme.

## How deployment works

- **`main`** holds the Hugo source (this branch — the one you edit).
- On every push to `main`, the GitHub Actions workflow (`.github/workflows/deploy.yml`) builds the site and pushes the output to **`gh-pages`**, which GitHub Pages serves at michaelsinko.phd.
- Never edit `gh-pages` by hand — it is overwritten on every deploy.

## Local development

Prerequisites: [Hugo Extended](https://gohugo.io/installation/) v0.128 or later, and Git.

```bash
git clone --recurse-submodules https://github.com/sinkomr/sinkomr.github.io.git
cd sinkomr.github.io
hugo server -D        # -D includes draft content
```

Visit http://localhost:1313 to preview. If you cloned without `--recurse-submodules`, run `git submodule update --init --recursive` to fetch the theme.

## Site structure

```
├── content/
│   ├── _index.md           # Home page intro
│   ├── about.md            # About page
│   ├── projects/           # Projects section
│   └── oom/                # Order of Magnitude section
├── static/                 # Copied verbatim into the site root
│   ├── CNAME               # Custom domain (do not delete)
│   ├── favicon* / apple-touch-icon.png
│   └── images/             # Put images here
├── themes/PaperMod/        # Theme (git submodule — don't edit)
├── hugo.toml               # Site configuration
└── .github/workflows/deploy.yml
```

## Adding content

### A new project

```bash
hugo new content/projects/my-project.md
```

```markdown
---
title: "My Project Name"
date: 2026-07-11
draft: false
description: "Brief project description"
tags: ["tag1", "tag2"]
cover:
  image: "/images/projects/my-project.jpg"
  alt: "Project image description"
---

## Overview
...
```

Put images in `static/images/projects/` and reference them as `/images/projects/name.jpg`. Set `draft: false` when ready to publish — drafts are visible locally with `hugo server -D` but never deployed.

### An Order of Magnitude entry

```bash
hugo new content/oom/10e-9-nanometers.md
```

```markdown
---
title: "10^-9 meters (Nanometers)"
date: 2026-07-11
draft: false
description: "Things at this scale"
weight: 1000   # lower numbers appear first
params:
  scale: "10^-9 m"
  unit: "nanometers (nm)"
---
```

Images go in `static/images/oom/`.

Template examples live at `content/projects/example-project.md` and `content/oom/example-scale.md` (both `draft: true`, so they never publish).

## Configuration

Edit `hugo.toml` for the site title, description, menu, social icons, and theme settings. PaperMod docs: https://github.com/adityatelange/hugo-PaperMod/wiki

## License

Content © Michael R Sinko PhD. Theme licensed under MIT by its authors.
