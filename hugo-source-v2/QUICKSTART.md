# Quick Start Guide - Website V2

## What's New in V2

Your website has been completely rebuilt with proper Hugo source files. Here's what changed:

### Before (V1)
- Only built HTML files (no way to edit or add content)
- Broken navigation links
- Missing favicon files
- Typo in main content ("research,fun" → "research, fun")
- No proper git workflow

### After (V2)
- Full Hugo source structure with markdown files
- Projects page ready for content
- Order of Magnitude page ready for content
- About page template
- Clean, professional PaperMod theme
- Automated GitHub Actions deployment
- Proper documentation

## Directory Overview

```
hugo-source-v2/
├── content/              ← Your content lives here (markdown files)
│   ├── _index.md        ← Home page
│   ├── about.md         ← About page
│   ├── projects/        ← Project posts go here
│   └── oom/             ← Order of Magnitude entries
├── static/images/       ← Put images here
├── hugo.toml            ← Site configuration
└── themes/PaperMod/     ← Theme (don't modify directly)
```

## First Steps

### 1. Install Hugo (if not already installed)

**macOS:**
```bash
brew install hugo
```

**Linux:**
```bash
sudo snap install hugo
```

**Windows:**
Download from https://gohugo.io/installation/windows/

Verify installation:
```bash
hugo version
```

### 2. Run Locally

```bash
cd hugo-source-v2
hugo server -D
```

Visit http://localhost:1313 to see your site.

### 3. Add Your First Project

Create a new project file:

```bash
cd hugo-source-v2
hugo new content/projects/my-first-project.md
```

Edit the file and set `draft: false` when ready to publish.

### 4. Add Order of Magnitude Entries

Example for nanometer scale:

```bash
hugo new content/oom/10e-9-nanometers.md
```

Edit to add:
- Scale reference (what exists at this scale)
- Projects/measurements you've done at this scale
- Images showing work at this scale

## Content Structure

### Projects

Each project should include:
- Title and date
- Description
- Technical details
- Images
- Results/outcomes

See `content/projects/example-project.md` for template.

### Order of Magnitude

Each OoM entry should include:
- Scale (e.g., "10^-9 meters")
- Context (what exists at this scale)
- Your work/measurements at this scale
- Images and visualizations

See `content/oom/example-scale.md` for template.

## Customization

### Update Site Information

Edit `hugo.toml`:

```toml
title = "Your Name"
[params]
  description = "Your description"
  author = "Your Name"
```

### Add Social Links

In `hugo.toml`, modify the `socialIcons` section:

```toml
[[params.socialIcons]]
  name = "github"
  url = "https://github.com/yourusername"

[[params.socialIcons]]
  name = "linkedin"
  url = "https://linkedin.com/in/yourprofile"
```

### Update About Page

Edit `content/about.md` with your information.

## Deployment

### Option 1: GitHub Actions (Recommended)

1. Push to your repository
2. GitHub Actions automatically builds and deploys
3. Site appears at michaelsinko.phd

### Option 2: Manual Build

```bash
cd hugo-source-v2
hugo --minify
```

Copy contents of `public/` to your web host.

## Adding Images

1. Place images in `static/images/projects/` or `static/images/oom/`
2. Reference in markdown: `![Description](/images/projects/myimage.jpg)`
3. Or use front matter cover image:

```yaml
cover:
  image: "/images/projects/myimage.jpg"
  alt: "Description"
  caption: "Optional caption"
```

## Next Steps

1. **Update About page** with your bio and contact info
2. **Add real projects** - remove example-project.md, add your own
3. **Add OoM entries** - start with scales relevant to your work
4. **Add images** - create folders in static/images/ and add visuals
5. **Customize theme** - adjust colors/fonts in hugo.toml if desired

## Theme Documentation

PaperMod theme docs: https://github.com/adityatelange/hugo-PaperMod/wiki

## Getting Help

- Hugo docs: https://gohugo.io/documentation/
- PaperMod GitHub: https://github.com/adityatelange/hugo-PaperMod
- Hugo forums: https://discourse.gohugo.io/

## Site Goals

This site is designed to be:
- **Clean and professional** - minimal design, focus on content
- **Easy to maintain** - markdown files, simple structure
- **Fast to build** - Hugo is extremely fast
- **Easy to deploy** - automated via GitHub Actions

The style emphasizes **clarity and information presentation** over decoration. The PaperMod theme provides a sharp, clean aesthetic perfect for technical and academic content.
