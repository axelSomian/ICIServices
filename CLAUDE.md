# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static marketing website for **ICI Services**, an industrial solutions company based in Abidjan, Ivory Coast. No build tools, no package manager, no backend — pure HTML/CSS/JS deployed as-is.

## Development

**Local development:** Open in VS Code and start Live Server (pre-configured on port 5501 in `.vscode/settings.json`). No install or build step needed.

**Deployment:** Copy files directly to any static web host. No compilation required.

## Architecture

### Page Structure

- `index.html` — Landing page with hero, about, services grid, certifications, stats, footer
- `Pages/*.html` — Six service detail pages (diesel, incendie, metrologie, robinetterie, achat, actualite) plus `contact.html`
- `styles.css` — Single shared stylesheet for all pages
- `Assets/imgs/` — All image assets (~40 files: logos, backgrounds, service photos)

### Conventions

All pages share the same header/footer HTML structure — when updating navigation or footer content, **edit every page** (no templating engine is in use).

Bootstrap 5.3.3 and Bootstrap Icons 1.3.0 are loaded from CDN (jsDelivr). No local copies.

### Contact Form

The contact form in `Pages/contact.html` uses vanilla JS to build a `mailto:` link — it opens the user's default email client rather than submitting to a server. Relevant addresses: `infos@iciservices.ci`, `jeremy.cravo@iciservices.ci`, `agnes.tape@iciservices.ci`.

### Language Toggle

The FR/EN toggle in the navbar is UI-only and not yet functional.

## Key CSS Details

- Color scheme: Bootstrap `danger` red (`#dc3545`) as primary accent, dark footer, light content sections
- Service cards: fixed 250px height with hover scale + shadow animation
- Page banners: 350px height with dark overlay and animated text entry
- Mobile breakpoint: 768px (Bootstrap's `md`)
- Custom scrollbar styled in gold/yellow
