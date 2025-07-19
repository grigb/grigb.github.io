# grigbilham.com

Legacy site for Grig Bilham — technologist, electronic musician, and nonprofit strategist.

## Overview

This is a simple, static GitHub Pages site that serves as a professional legacy page for Grig Bilham. It emphasizes his 25+ year mission of building creator-first technology and open systems.

## Features

- Clean, responsive design
- Comprehensive SEO metadata (Open Graph, Twitter Cards, Schema.org)
- Security headers configured via Cloudflare
- Weekly uptime monitoring via GitHub Actions
- Custom domain support (grigbilham.com)

## Local Development

To run locally:

```bash
# Using Python's built-in server
python3 -m http.server 8000

# Or using Node.js
npx http-server -p 8000
```

Then visit http://localhost:8000

## Deployment

This site is deployed automatically via GitHub Pages. Any push to the `main` branch will trigger a deployment.

## Domain Configuration

The site uses a custom domain (grigbilham.com) configured through:
1. CNAME file in the repository
2. DNS records pointing to GitHub Pages
3. Cloudflare proxy for security headers and HTTPS enforcement

## Maintenance

- Profile image: Update `/assets/placeholder.svg` with actual photo
- Content updates: Edit `index.html` directly
- Uptime monitoring: Check GitHub Actions tab for weekly status