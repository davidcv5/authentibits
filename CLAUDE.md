# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Build Commands

```bash
npm run dev      # Start dev server at localhost:4321
npm run build    # Build production site to ./dist/
npm run preview  # Preview production build locally
```

## Architecture

Authentibits is a static blog built with Astro 5, styled with Tailwind CSS 4, and deployed to Firebase Hosting via GitHub Actions.

### Content Flow
- Blog posts are Markdown/MDX files in `src/content/blog/`
- Content collections defined in `src/content.config.ts` enforce frontmatter schema
- Posts require: `title`, `description`, `pubDate`, optional `heroImage` and `updatedDate`
- Hero images must use relative paths from content files: `../../assets/image.jpg`

### Key Configuration Files
- `src/consts.ts` - Site title and description constants used across components
- `astro.config.mjs` - Site URL, integrations (MDX, sitemap), Tailwind via Vite plugin
- `firebase.json` - Hosting config with caching headers for static assets

### CI/CD
- Push to `main` → deploys to production (authentibits.web.app)
- Pull requests → deploys to preview channel with comment on PR
- Workflows in `.github/workflows/` use `FIREBASE_SERVICE_ACCOUNT_AUTHENTIBITS` secret

## Blog Post Frontmatter Schema

```yaml
---
title: 'Post Title'
description: 'SEO description'
pubDate: 'Dec 21 2024'
heroImage: '../../assets/blog-placeholder-1.jpg'  # optional
updatedDate: 'Dec 22 2024'  # optional
---
```

## Documentation Guidelines

When generating documentation, include mermaid diagrams where appropriate for architecture, design, and flow visualization.

## Blog Writing Guidelines

- Use the PAS (Problem-Agitation-Solution) framework to structure blog posts, but never include explicit labels like "The Problem:", "The Agitation:", or "The Solution:" in headings
- Let the structure guide the narrative naturally without telegraphing the framework to readers
- See `docs/brand-guidelines.md` for comprehensive voice, tone, and structural patterns
