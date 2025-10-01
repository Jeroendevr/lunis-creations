# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Pelican-based static site generator for "Luni's Creations", a Dutch portfolio website showcasing custom
printing and craft work. The site uses a custom theme and generates static HTML from Markdown content.

## Development Commands

### Building the Site

```bash
# Generate static site
make html
# OR
invoke build

# Clean and rebuild
make clean && make html
# OR  
invoke rebuild

# Development server with auto-reload
make devserver
# OR
invoke livereload    # Recommended - includes browser auto-refresh
```

### Development Server

```bash
# Serve site locally at http://localhost:8000
make serve
# OR
invoke serve

# Combined build and serve
invoke reserve
```

### Production

```bash
# Build for production
make publish
# OR
invoke publish
```

## Project Architecture

### Content Management

- **Content directory**: `content/` - Contains all markdown files
- **Pages**: `content/pages/` - Static pages like portfolio
- **Posts**: `content/*.md` - Blog posts/articles with categories
- **Images**: `content/images/` - Static assets referenced in content
- **Language**: Dutch (nl) - Primary content language

### Theme Structure

- **Custom theme**: `themes/nicole-portfolio/`
- **Templates**: `themes/nicole-portfolio/templates/` - Jinja2 HTML templates
- **Static assets**: `themes/nicole-portfolio/static/` - CSS, fonts, JS
- **Generated output**: `output/` - Final static site (do not edit manually)

### Configuration

- **Development config**: `pelicanconf.py` - Local development settings
- **Production config**: `publishconf.py` - Production deployment settings
- **Task automation**: `tasks.py` - Invoke tasks, `Makefile` - Make targets

### Content Format

Markdown files use standard Pelican metadata:

```markdown
Title: Article Title
Date: YYYY-MM-DD
Category: Category Name

Content goes here...
```

## Dependency Management

- **Python**: Requires Python >=3.13
- **Package manager**: uv (configured in `pyproject.toml`)
- **Main dependency**: `pelican[markdown]>=4.11.0`

## Site Details

- **Site name**: "Luni's Creations"
- **Author**: Nicole
- **Production URL**: https://lunis-creations.nl
- **Timezone**: Europe/Amsterdam
- **Categories**: Bedrukking (printing), misc