# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Jekyll-based personal blog using the "Catbook" theme, a category-centric theme designed for bloggers. The site supports both dark and light modes and is deployed on Netlify at `ruifengz99.github.io`.

## Development Commands

### Local Development
```bash
# Install dependencies
bundle install

# Serve locally with auto-reload
jekyll serve
# The site will be available at http://localhost:4000
```

### Build and Deploy
```bash
# Build for production
bundle exec jekyll build
# Output will be in the _site directory

# The site deploys automatically via Netlify when pushed to main branch
```

## Architecture and Structure

### Core Jekyll Structure
- `_config.yml` - Main site configuration, user profile, and Jekyll settings
- `_posts/` - Blog posts in Markdown format with YAML front matter
- `_portfolio/` - Portfolio items (collection defined in _config.yml)
- `_layouts/` - HTML templates for different page types
- `_includes/` - Reusable HTML components
- `_sass/` - Sass stylesheets
- `_site/` - Generated static site (ignored in git)

### Category System
The theme is built around a category-centric approach:
- `categories/` - Individual category pages (e.g., `coding.html`, `dev.html`)
- Each category page includes `{% include archive.html %}` to display posts
- Categories are defined in post front matter and automatically generate navigation

### Key Files
- `index.html` - Homepage
- `portfolio.html` - Portfolio page
- `aboutme.html` - About page (controlled by `user.aboutme` in _config.yml)
- `netlify.toml` - Netlify build configuration

### Post Format
Posts follow Jekyll conventions:
```yaml
---
title: Post Title
categories: [category1, category2]
comments: true  # Enable comments via Disqus/Cusdis
---

Post content in Markdown...
```

### Portfolio Format
Portfolio items are in the `_portfolio/` collection:
```yaml
---
title: Project Title
categories: [coding]
comments: true
---

Project description and content...
```

## Theme Features

### Dark/Light Mode
The theme includes a toggle switch for dark/light mode, implemented via JavaScript in `_includes/js.html`.

### Comments
Supports both Disqus and Cusdis comment systems, configured in `_config.yml`.

### Customization
- User profile and site info configured in `_config.yml`
- Custom styling via Sass files in `_sass/`
- Category pages must be manually created in `categories/` folder

## Ruby Environment
- Ruby version: 2.7.8 (specified in `.ruby-version`)
- Jekyll version: ~4.3.2
- Dependencies managed via Bundler (see `Gemfile`)

## Deployment
- Site deploys automatically to Netlify when changes are pushed to main branch
- Build command configured in `netlify.toml`
- Custom domain: `ruifengz99.github.io`