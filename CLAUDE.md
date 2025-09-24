# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a static portfolio website for Charbel Tannous (Software Engineer) exported from Webflow. The site showcases projects, work experience, and contact information with a modern, responsive design.

## Architecture

- **Static HTML Site**: Pure HTML/CSS/JS without build tools or frameworks
- **Main Pages**:
  - `index.html` - Homepage with hero section and project highlights
  - `work.html` - Complete portfolio showcase
  - `about.html` - Professional background and skills
  - `contact.html` - Contact form and information
- **Experience Pages**: Individual project pages in `/experience/` directory
- **Assets**: Organized in `/css/`, `/js/`, `/images/` directories
- **Deployment**: Configured for Vercel hosting with clean URLs

## Common Development Commands

### Formatting Code
```bash
python scripts/format_files.py
```
Formats all HTML, CSS, JS, JSON, and MD files using Prettier.

### Generate Sitemap
```bash
python scripts/generate_sitemap.py
```
Generates XML sitemap for SEO, automatically discovers all HTML pages.

### Local Development
Since this is a static site, serve locally with any HTTP server:
```bash
python -m http.server 8000
# or
npx serve .
```

## Key Configuration

### Vercel Deployment (`vercel.json`)
- Clean URLs enabled (removes .html extensions)
- Image optimization with WebP conversion
- Security headers configured
- Redirects from .html URLs to clean URLs
- Caching strategy for static assets

### Directory Structure
```
/
├── index.html, work.html, about.html, contact.html  # Main pages
├── experience/                                      # Individual project pages
├── css/                                            # Stylesheets (Webflow + custom)
├── js/                                             # JavaScript (jQuery, animations)
├── images/                                         # All visual assets
├── scripts/                                        # Python utilities
└── vercel.json                                     # Deployment configuration
```

## Important Notes

- **Webflow Export**: This is exported from Webflow, so maintain the existing CSS class structure
- **Responsive Design**: Mobile-first approach with specific mobile styles
- **Dependencies**: Uses jQuery and includes BlockRain.js for animations
- **No Build Process**: Direct HTML/CSS/JS editing - changes are immediately live
- **Security**: Comprehensive security headers configured in vercel.json