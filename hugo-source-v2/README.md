# Michael R Sinko PhD - Website V2

This is the Hugo source code for michaelsinko.phd, rebuilt from scratch with proper source structure.

## Quick Start

### Prerequisites

- [Hugo Extended](https://gohugo.io/installation/) (v0.120.0 or later)
- Git

### Local Development

1. Clone with submodules:
```bash
git clone --recurse-submodules <repository-url>
cd hugo-source-v2
```

2. If already cloned, initialize submodules:
```bash
git submodule update --init --recursive
```

3. Run local server:
```bash
hugo server -D
```

Visit http://localhost:1313 to preview the site.

### Building for Production

```bash
hugo --minify
```

The built site will be in the `public/` directory.

## Site Structure

```
hugo-source-v2/
├── content/
│   ├── _index.md           # Home page
│   ├── about.md            # About page
│   ├── projects/           # Projects section
│   │   ├── _index.md       # Projects landing page
│   │   └── *.md            # Individual project posts
│   └── oom/                # Order of Magnitude section
│       ├── _index.md       # OoM landing page
│       └── *.md            # Individual scale entries
├── static/
│   └── images/             # Images for projects and OoM
│       ├── projects/
│       └── oom/
├── themes/
│   └── PaperMod/           # Theme (git submodule)
└── hugo.toml               # Site configuration
```

## Adding Content

### Adding a New Project

1. Create a new markdown file in `content/projects/`:

```bash
hugo new content/projects/my-project.md
```

2. Edit the file with your project details:

```markdown
---
title: "My Project Name"
date: 2025-01-23
draft: false
description: "Brief project description"
tags: ["tag1", "tag2"]
cover:
  image: "/images/projects/my-project.jpg"
  alt: "Project image description"
  caption: "Optional caption"
---

## Overview

Project description here.

## Technical Details

- Technology stack
- Key features
- Implementation notes

## Images

![Additional image](/images/projects/my-project-detail.jpg)

## Results

Outcomes and learnings.
```

3. Add images to `static/images/projects/`

### Adding an Order of Magnitude Entry

1. Create a new markdown file in `content/oom/`:

```bash
hugo new content/oom/scale-name.md
```

2. Edit with scale information:

```markdown
---
title: "10^X meters (Unit Name)"
date: 2025-01-23
draft: false
description: "Things at this scale"
weight: 1000  # Lower numbers appear first
params:
  scale: "10^X m"
  unit: "unit name"
---

## Scale Reference

Context for this order of magnitude.

## Projects at This Scale

### Project Name

Description and details.

![Visualization](/images/oom/scale-image.jpg)
```

3. Add images to `static/images/oom/`

## Configuration

Edit `hugo.toml` to customize:

- Site title and description
- Menu items
- Social links
- Theme settings

## Deployment

### Manual Deployment

1. Build the site:
```bash
hugo --minify
```

2. Copy contents of `public/` to your web server or GitHub Pages branch.

### Automated Deployment (Recommended)

A GitHub Actions workflow is included in `.github/workflows/` that automatically builds and deploys the site when you push to the main branch.

## Theme

This site uses [PaperMod](https://github.com/adityatelange/hugo-PaperMod), a clean and minimal Hugo theme designed for readability and professional presentation.

## License

Content is © 2025 Michael R Sinko PhD. Theme is licensed under MIT by its respective authors.
