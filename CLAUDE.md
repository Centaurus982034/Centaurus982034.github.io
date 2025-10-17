# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is a Jekyll-based academic website using the **al-folio** theme. It's designed to create a professional academic portfolio with publications, projects, blog posts, and CV functionality. The site is hosted on GitHub Pages.

## Development Commands

### Building and Serving
- **Build the site**: `bundle exec jekyll build`
- **Serve locally**: `bundle exec jekyll serve` (standard Jekyll development)
- **Production build**: `bin/cibuild` (same as build command)
- **Deploy to GitHub Pages**: `bin/deploy` (handles branch switching and deployment)

### Code Quality and Formatting
- **Format code**: `npx prettier --write .` (formats Liquid templates and other files)
- **Purge unused CSS**: `purgecss -c purgecss.config.js` (used during deployment)

### Installation
- **Install Ruby dependencies**: `bundle install`
- **Install Node.js dependencies**: `npm install`

## Architecture and Structure

### Core Configuration
- **Main config**: `_config.yml` - Contains all site settings, Jekyll configuration, plugins, and theme customization
- **Ruby dependencies**: `Gemfile` - Jekyll plugins including jekyll-scholar, jekyll-feed, jekyll-imagemagick
- **Node dependencies**: `package.json` - Prettier for code formatting

### Content Organization
- **Pages**: `_pages/` - Static pages (about, CV, publications, projects, etc.)
- **Blog posts**: `_posts/` - Blog entries in markdown
- **Projects**: `_projects/` - Project descriptions and portfolios
- **News**: `_news/` - News/announcements displayed on homepage
- **Bibliography**: `_bibliography/papers.bib` - Academic publications in BibTeX format
- **Data files**: `_data/` - YAML data files (CV, repositories, etc.)

### Layout and Styling
- **Layouts**: `_layouts/` - Jekyll layout templates
- **Includes**: `_includes/` - Reusable template components
- **Sass styles**: `_sass/` - Theme stylesheets and customizations
- **Assets**: `assets/` - Images, PDFs, JSON files, and other static content

### Functionality Scripts
- **Analytics setup**: `_scripts/` - Client-side JavaScript for Google Analytics, Giscus comments, etc.
- **Build scripts**: `bin/` - Deployment and build automation scripts
- **Jekyll plugins**: `_plugins/` - Custom Jekyll plugins for extended functionality

### Key Features
- **Academic publications**: Automatically generated from BibTeX with jekyll-scholar
- **Dark/light mode**: Built-in theme switching
- **Responsive design**: Mobile-friendly Bootstrap-based layout
- **Math support**: MathJax integration for LaTeX equations
- **Code highlighting**: Syntax highlighting for code blocks
- **Image optimization**: ImageMagick integration for responsive images
- **Search functionality**: Client-side search across content
- **RSS feed**: Automatic feed generation
- **CV generation**: Both JSON Resume and YAML formats supported

### Development Notes
- Uses Jekyll 4.x with extensive plugin ecosystem
- Bootstrap-based responsive design
- Liquid templating with custom filters and tags
- PurgeCSS integration for CSS optimization
- Pre-commit hooks available for code quality
- Docker support available for consistent environments

### Deployment
The `bin/deploy` script handles full GitHub Pages deployment:
1. Switches to deploy branch
2. Builds site with `JEKYLL_ENV=production`
3. Purges unused CSS
4. Commits and pushes to `gh-pages` branch
5. Returns to source branch