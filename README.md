# TheCore Studio

Website for **TheCore Studio**, a Pilates studio in Santa Maria delle Mole (Castelli Romani). Small classes, seriously trained instructors, complete equipment beyond the Reformer. *Il centro da cui parte il movimento.*

Built with [Hugo](https://gohugo.io/) and a custom in-repo theme. Content and copy are in Italian and follow the studio's voice: warm, plain, unhurried, informal *tu*.

## Stack

- **Static site generator:** Hugo ≥ 0.146 (standard build, no extended features required)
- **Theme:** custom theme `thecore` living in [`themes/thecore/`](themes/thecore/)
- **Design system:** documented in [`DESIGN.md`](DESIGN.md) (Google Stitch format, DESIGN.md-aware AI harnesses can read it)
- **Fonts:** self-hosted woff2 (Cormorant Garamond, Hanken Grotesk) in [`static/fonts/`](static/fonts/)
- **i18n:** single language (Italian), strings in [`i18n/it.yaml`](i18n/it.yaml)

## Project structure

```
.
├── archetypes/          # default content archetype (draft = true)
├── assets/              # project-level assets (unused; theme has its own)
├── content/             # site content (Italian markdown)
├── data/                # data files (unused)
├── i18n/                # translations (it.yaml)
├── layouts/             # project-level layouts (empty; theme provides them)
├── static/              # fonts, favicon
├── themes/thecore/      # the active custom theme
│   ├── assets/css/      # design system + component styles (main.css)
│   ├── assets/js/       # main.js
│   ├── layouts/         # baseof, index, single, list, partials
│   └── hugo.toml        # theme config (min Hugo version)
├── hugo.toml            # site config: title, menus, params
├── DESIGN.md            # brand, voice, colors, typography, tokens
└── .gitignore           # ignores public/ build output
```

## Getting started

**Prerequisites:** [Hugo](https://gohugo.io/installation/) ≥ 0.146.

```bash
# 1. Clone the repository
git clone git@github.com:thecorestudio/website.git
cd website

# 2. Run the dev server
hugo server -D
# → http://localhost:1313

# 3. Build the static site
hugo
# → output in public/ (gitignored)
```

## Adding content

New pages are created from the archetype (draft by default):

```bash
hugo new classi/pilates-matwork.md
```

Content is plain markdown with front matter; the theme renders it through `single.html` (with a section label) and `list.html` (card grid for sections).

### Navigation

Main menu items are defined in [`hugo.toml`](hugo.toml) under `[menu]`:

```toml
[[menu.main]]
  name = 'Classi'
  pageRef = '/classi'
  weight = 2
```

### Copy & translations

All user-facing strings live in [`i18n/it.yaml`](i18n/it.yaml) and are referenced in templates via `{{ T "key" }}`. Keep the voice consistent — see the *Voice & Tone* section in `DESIGN.md` for do/don't examples.

## Design system

Colors, typography, spacing, and logo rules are all specified in [`DESIGN.md`](DESIGN.md). Key rules:

- **Terracotta** (`#C06B47`) is an accent for the single action you want the person to take — never a background carpet.
- Max one or two background colors per surface (clay/cream).
- Titles in Cormorant Garamond, functional text in Hanken Grotesk, labels in uppercase Spline Sans Mono.
- Radius stays soft, never sharp.

CSS custom properties implementing the tokens are at the top of `themes/thecore/assets/css/main.css`.

## Deployment

The site is configured for `https://thecore.studio/` (`baseURL` in `hugo.toml`). Build with `hugo`, then serve the contents of `public/` — the output directory is gitignored by design.

## Notes

- Contact details (email, phone, address) in the footer and homepage are **placeholder values** — replace them with real studio details before launch.
- Theme-level config (Hugo version requirement) lives in `themes/thecore/hugo.toml`.
