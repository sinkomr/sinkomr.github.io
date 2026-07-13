# Handoff: michaelsinko.phd

Context document for the next collaborator (written 2026-07-13 by the Claude session that built V2). Everything below is current as of branch `claude/personal-website-review-l84l25`.

## What this is

Personal website for **Michael R Sinko PhD** at **https://michaelsinko.phd/** (repo: `sinkomr/sinkomr.github.io`). Static site built with **Hugo** (extended) and the **PaperMod** theme (git submodule at `themes/PaperMod`, do not edit the theme directly).

## Repo and branch state

- **`main`**: only a LICENSE. All real work lives on the working branch below and merges into main via PR.
- **`claude/personal-website-review-l84l25`**: the working branch, full V2 site source. Open **draft PR #1** targets main. Nothing ships until that PR merges; the owner has explicitly said he is not ready to ship yet.
- **`gh-pages`**: the live V1 site, deprecated. It gets completely overwritten by the deploy workflow on first merge to main. Never edit it by hand.
- **`claude/check-jekyll-usage-Q8hdg`**: historical branch from a previous session where V2 originally lived (stranded, already extracted). Ignore it.

## Deployment (do not change this without asking)

- `.github/workflows/deploy.yml`: on push to main, builds with Hugo extended 0.147.7 (`hugo --gc --minify`) and pushes `public/` to the `gh-pages` branch via `peaceiris/actions-gh-pages@v4`.
- GitHub Pages serves from the `gh-pages` branch with custom domain `michaelsinko.phd` (DNS verified pointing at GitHub Pages). This setup was chosen deliberately so **no Pages settings changes are needed** to ship. `static/CNAME` keeps the domain in place across deploys; do not delete it.
- `baseURL` in `hugo.toml` is `https://michaelsinko.phd/`.
- PaperMod requires Hugo >= 0.146; the workflow pin satisfies it. Keep any version bumps above that.

## Local development

- `hugo server -D` (drafts on) after `git submodule update --init --recursive`.
- If no Hugo binary is available (e.g. sandboxed environments where GitHub release downloads are blocked): `pip install hugo` provides `python3 -m hugo` (hugo-python-distributions). It runs a newer Hugo than the workflow pin; expect a few harmless deprecation warnings that the CI build won't show.
- Verification habits used so far, worth keeping: build clean, crawl built HTML for broken internal links, confirm canonical URLs point at michaelsinko.phd, and grep the output for em-dashes (see style rules).

## Hard style rules from the owner

1. **No em-dashes. Ever.** He calls them "the stupid emdash." Use commas, colons, semicolons, or parentheses. This has been enforced across all content and checked at build time (`grep -c '—' public/...` should be 0).
2. **Relaxed, casual, first-person voice.** Reference point: his friend Wentao's page at outside5sigma.com/about, but he explicitly corrected an early draft for copying that style too closely. Draw inspiration (short chronological paragraphs, humor woven into sentences, hobbies as a closer), do not imitate (no "Hi there, this is...", no "here's the longer version" pivot).
3. **Never invent biography.** Personal details on the site come only from facts he has stated. When seeding content, leave cells/sections blank rather than guessing, or mark the file `draft: true` with a review note.
4. He prefers short over long; he trimmed an early two-paragraph bio request down and later expanded it himself on his own terms. Follow his lead on length.

## Owner facts (the interview database)

Everything below came from him directly and is safe to use:

- Grew up in **western Pennsylvania**; outdoors kid, constant reader, **Eagle Scout**.
- **Miami University**: physics **BS/MS**. First year set up a **PCB prototyping line**; then characterized **magnetic materials (nanoparticles, thin films)**; first exposure to **cryogenic liquids and high magnetic fields**. Played intramural **broomball** and learned **ice hockey**.
- **Carnegie Mellon PhD** in physics: **2D materials and superconducting circuits**; heavy **cleanroom/nanofab** time; department cookout **grill master**; two cats, **Pico and Nano**; learned to **ski in the Appalachians**.
- Headed west **before** the postdoc (Sandia is in **Livermore, CA**, a common mix-up he corrected once).
- **Sandia National Laboratories postdoc**: set up a **nanoimprint lithography** system; **UHV** work he describes as "a fancy but frustrating UHV setup" (nickelate superconductors, though he cut that detail from the bio).
- **Bleximo**: quantum device fabrication; the company **ceased operations** (his preferred phrasing on the site).
- Now: **Fisica ATI**, working on **high energy density physics and pulsed power systems**.
- **SQUID Consultants LLC**: his quantum computing hardware consulting company. Never describe it as "on the side."
- Lives in the **Bay Area**. Hobbies: **woodworking, 3D printing, gardening**.

## Content state, page by page

### About (`content/about.md`): DONE, owner-approved v1
He wrote the final text himself; I copy-edited it (his words are canon). Do not restructure it without his say-so.

### Order of Magnitude (`content/oom/`): BUILT, awaiting his review of values
His signature section. Structure he specified: the section index lists **units**; each unit page is a **table walking the powers of ten** across the physically reasonable range.

- **29 published pages**, weights 10 through 290, in the order he listed the units: length, area, volume, velocity, acceleration, force, pressure, mass, charge, voltage, current, power, energy, capacitance, inductance, resistance, radiation dose, radiation dose rate, luminosity, temperature, spectral frequency, time, neutron yield, plasma density, magnetic field, electric field, angular velocity, sound level, air quality.
- Table format: `| Scale | Reference point | My encounters |`. Magnetic field adds a `DC or pulsed` column (his request). Sound level counts in dB rather than powers of ten; air quality is framed around ISO cleanroom classes (ISO N = 10^N particles/m³, running to concrete grinding).
- The **My encounters** column is deliberately sparse: seeded only from the facts above, blank cells are invitations for his war stories.
- **Exponents use Unicode superscripts (10⁻⁹), not `<sup>` HTML**, because Goldmark's raw-HTML rendering is off (default). If a redesign needs inline HTML in markdown, set `markup.goldmark.renderer.unsafe = true` in hugo.toml, knowingly.
- Four units were my additions he hasn't explicitly reviewed: inductance, electric field, angular velocity, sound level. "rads/rads-sec" was interpreted as radiation dose/dose rate (HEDP context), flagged to him, not yet confirmed.
- `elements-and-isotopes.md` is **`draft: true`** with a review note: a seeded inventory of elements/isotopes he has worked with. Needs his pass before publishing; some entries are inferences.
- Unbuilt candidates he was offered: bytes, gas flow (sccm), torque, radioactivity (Ci/Bq), data rate, dollars.
- `[pagination] pagerSize = 50` in hugo.toml exists specifically so the OoM index shows all units on one page. Don't lower it.

### Home page: OPEN ITEM
Still shows the original blurb from `hugo.toml` `[params.homeInfoParams]` ("This site chronicles my publicly available research, projects, and interesting measurements."), which predates the About rewrite. Options raised with him but undecided: refresh the blurb in his newer voice, or switch PaperMod to profile mode (centered name/photo/buttons). A design pass is the natural place to settle this.

### Projects (`content/projects/`): EMPTY
Landing page intro only; `example-project.md` is a `draft: true` template. No real projects gathered yet. He has obvious candidates (PCB line, nanoimprint system, woodworking/3D printing builds) but has not been interviewed for these.

### Images: NONE YET
`static/images/` doesn't exist yet. No photos anywhere on the site. PaperMod supports cover images per page (`cover:` front matter). Wentao's page leans on captioned era photos; the owner may want the same eventually.

## Design-relevant technical notes

- Theme customization goes in root-level overrides, not the submodule: `assets/css/extended/*.css` (PaperMod concatenates these into its stylesheet) and `layouts/` for template overrides.
- Favicons: a generated "MS" monogram set in `static/` (rounded square, PaperMod dark palette: bg `#2e2e33`, fg `#dadadb`), plus `safari-pinned-tab.svg` (currently just a rounded square, no monogram). Generated by a throwaway PIL script; a designed replacement would be welcome. Sizes: favicon.ico (16/32/48), favicon-16x16.png, favicon-32x32.png, apple-touch-icon.png (180).
- `hugo.toml` params of note: `defaultTheme = "auto"` (light/dark both live), ShowReadingTime/ShareButtons/WordCount off, breadcrumbs on, `env = "production"`.
- Menu: Home / Projects / Order of Magnitude / About.
- The site currently has zero custom CSS or layout overrides; it is stock PaperMod.

## Process expectations

- Owner collaborates iteratively: he asks to be interviewed, reacts to drafts, and sometimes rewrites wholesale (his rewrite wins). Show him the text, list what you changed, offer targeted follow-ups.
- Commit to `claude/personal-website-review-l84l25` and push; PR #1 already tracks it. Keep it a draft PR until he says ship.
- Shipping = merging PR #1 to main. First merge overwrites the deprecated V1 on gh-pages automatically. He knows this.
- Verify builds locally before pushing (see verification habits above).
