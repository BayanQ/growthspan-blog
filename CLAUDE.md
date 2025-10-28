# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is the Growthspan Blog, a complete Hexo static site using the Clean Blog theme. It's deployed on Netlify and configured for automatic builds on push.

## Commands

### Development
```bash
npm install          # Install dependencies
npm run server       # Start local development server (http://localhost:4000)
npm start            # Alias for npm run server
```

### Building
```bash
npm run clean        # Clean generated files and cache
npm run build        # Generate static files (output to public/)
```

### Content Management
```bash
hexo new post "My New Post"           # Create a new blog post
hexo new page "page-name"             # Create a new page
hexo new draft "Draft Post"           # Create a draft post
hexo publish draft "Draft Post"       # Publish a draft
```

### Deployment
Deployment is automatic via Netlify when pushing to the master branch. Netlify runs `npm install && npm run build` and publishes the `public/` directory.

## Architecture

### Directory Structure

```
.
├── _config.yml                 # Main Hexo configuration
├── package.json                # Node.js dependencies
├── netlify.toml                # Netlify deployment config
├── source/                     # Content source files
│   ├── _posts/                 # Blog posts (Markdown)
│   ├── tags/                   # Tags page
│   ├── categories/             # Categories page
│   └── about/                  # About page
├── themes/                     # Theme directory
│   └── clean-blog/             # Clean Blog theme
│       ├── _config.yml         # Theme configuration
│       ├── layout/             # EJS templates
│       ├── languages/          # i18n translations
│       └── source/             # Theme static assets (CSS, images)
└── public/                     # Generated static files (git-ignored)
```

### Configuration Files

**Main Config (`_config.yml`):**
- Site metadata (title, description, author)
- URL structure and permalinks
- Theme selection (set to `clean-blog`)
- Content generation settings
- Pagination and date formats

**Theme Config (`themes/clean-blog/_config.yml`):**
- Menu structure and navigation
- Cover images (home page and post defaults)
- Comment system settings (Disqus or Facebook)
- Social media links (footer)
- Google Analytics and Addthis integration

### Content Management

**Blog Posts (`source/_posts/`):**
Write posts in Markdown with front matter:
```yaml
---
title: Post Title
subtitle: A catchy subtitle (optional, shows in listings)
date: 2025-10-28 10:00:00
author: Author Name
tags:
  - tag1
  - tag2
categories:
  - Category Name
cover: /img/custom-cover.jpg  # Optional custom header image
share_cover: /img/share.jpg   # Optional social sharing image
comment: false                 # Optional: disable comments
---
```

**Pages:**
- Static pages live in `source/[page-name]/index.md`
- Use `layout: page` in front matter
- Examples: about, contact, custom pages

### Theme System

The Clean Blog theme uses EJS templating:

**Main Layout (`themes/clean-blog/layout/layout.ejs`):**
- Base template: head → menu → content → footer → scripts
- All pages inherit from this layout

**Key Templates:**
- `index.ejs` - Home page with post listings
- `post.ejs` - Individual blog post view
- `page.ejs` - Static pages
- `archive.ejs` - Archive listings

**Partials (`themes/clean-blog/layout/_partial/`):**
- `article-full.ejs` - Full post rendering with metadata, content, tags, categories
- `article-index.ejs` - Post previews for listings
- `head.ejs` - Meta tags, Open Graph, Twitter Cards, CSS includes
- `menu.ejs` - Navigation menu
- `footer.ejs` - Footer with social links
- `comments.ejs` - Disqus or Facebook comments integration

### Build Process

1. Hexo reads `_config.yml` and content from `source/`
2. Markdown files are converted to HTML
3. EJS templates from `themes/clean-blog/layout/` are rendered
4. Static assets are copied from `themes/clean-blog/source/`
5. Final output is generated to `public/` directory
6. Netlify serves the `public/` directory

### Key Features

- **Responsive Design**: Bootstrap 3.3.6 grid system
- **SEO Optimized**: Open Graph and Twitter Card meta tags
- **Syntax Highlighting**: Code blocks with syntax highlighting
- **Image Galleries**: FeatherLight.js for lightbox galleries
- **Comments**: Disqus or Facebook comments support
- **Analytics**: Google Analytics integration
- **Social Sharing**: Addthis integration for sharing
- **Multi-language**: Support for 10+ languages
