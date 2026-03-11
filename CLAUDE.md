# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Jekyll static site for Mohammadreza Shahsahebi's personal academic website, hosted at [shahsahebi.com](https://shahsahebi.com). It uses the [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/) Jekyll theme (v4.24.0) with the "contrast" skin.

## Common Commands

**Local development (Jekyll):**
```bash
bundle exec jekyll serve
# or using Rakefile:
bundle exec rake preview
```

**Build for production:**
```bash
bundle exec jekyll build
```

**Rebuild minified JS** (after editing `assets/js/_main.js` or plugins):
```bash
npm run build:js
```

**Watch JS for changes:**
```bash
npm run watch:js
```

## Architecture

### Content Structure

All main content lives in top-level Markdown files:
- [index.md](index.md) — Home/About page (main content: bio, working papers, conference presentations, awards, experience)
- [teachings.md](teachings.md) — Teaching details
- [contact.md](contact.md) — Contact form (powered by FormKeep external service)
- [about.md](about.md) — Redirects to index

Navigation is configured in [_data/navigation.yml](_data/navigation.yml).

### Customization vs Theme

- Theme files (`_layouts/`, `_includes/`, `_sass/minimal-mistakes/`) are the upstream Minimal Mistakes theme — avoid editing unless necessary
- Custom styling goes in [assets/css/custom.css](assets/css/custom.css) (currently just link underline styles)
- Site-specific config is in [_config.yml](_config.yml)
- The generated site outputs to `_site/` (git-ignored)

### JavaScript Pipeline

`assets/js/main.min.js` is the concatenated+minified bundle. Do not edit it directly — edit `assets/js/_main.js` or plugin files, then run `npm run build:js`.

### Deployment

GitHub Pages deploys from the `main` branch. The `CNAME` file sets the custom domain `shahsahebi.com`.
