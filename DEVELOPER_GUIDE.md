# Developer Guide - grigbilham.com

This guide explains how to maintain and update the grigbilham.com legacy site.

## Quick Start

### Local Development

```bash
# Clone the repository
git clone git@github.com:grigb/grigb.github.io.git
cd grigb.github.io

# Run a local server (choose one)
python3 -m http.server 8000
# OR
npx http-server -p 8000

# Visit http://localhost:8000
```

### Making Changes

1. Edit files locally
2. Test changes in browser
3. Commit and push:
```bash
git add .
git commit -m "Describe your changes"
git push
```

Changes will be live at https://grigbilham.com within 1-2 minutes.

## Site Structure

```
/
├── index.html          # Main (only) page
├── assets/            
│   └── grig-bilham-profile.png  # Profile photo
├── CNAME              # Custom domain config (don't modify)
├── .github/workflows/
│   └── uptime.yml     # Weekly monitoring
└── README.md          # Basic site info
```

## Common Updates

### Update Bio Text

Edit the paragraphs in `index.html` between lines ~175-190:

```html
<section class="bio">
  <p>
    <strong>Grig Bilham is a technologist...</strong>
  </p>
  <!-- More paragraphs -->
</section>
```

### Add/Update Links

Find the "Projects & Links" section around line ~195:

```html
<div class="links">
  <a href="https://example.com" class="link-card">
    <h3>Project Name</h3>
    <p>Brief description</p>
  </a>
  <!-- Add more link cards here -->
</div>
```

### Update Profile Photo

1. Replace `/assets/grig-bilham-profile.png` with new image
2. Keep filename the same OR update references in `index.html`
3. Recommended: 600x600px square image

### Update SEO/Social Media Tags

The `<head>` section (lines ~5-50) contains:
- Open Graph tags (Facebook/LinkedIn previews)
- Twitter Card tags
- Schema.org structured data

Update these when bio significantly changes.

## Deployment

The site uses GitHub Pages with a custom domain:

- **Hosting**: GitHub Pages (automatic from main branch)
- **Domain**: grigbilham.com (via CNAME file)
- **SSL**: Provided by GitHub Pages
- **DNS**: Managed externally (Cloudflare)

### How It Works

1. Push to `main` branch → GitHub Pages builds automatically
2. `CNAME` file tells GitHub to serve at grigbilham.com
3. DNS records point grigbilham.com → GitHub's servers
4. GitHub handles SSL certificates

## Monitoring

- **Uptime Check**: Runs weekly (Mondays 8 AM UTC)
- **View Status**: Check Actions tab in GitHub
- **Manual Run**: Go to Actions → Weekly Uptime → Run workflow

## Important Notes

### DO NOT

- Delete or modify the CNAME file
- Change repository name (must stay as `grigb.github.io`)
- Use Jekyll or other static site generators (plain HTML only)
- Add complex JavaScript (keep it simple and fast)

### DO

- Keep the site lightweight and fast
- Maintain accessibility (alt tags, semantic HTML)
- Test locally before pushing
- Update timestamps in commits for clarity

## Technical Details

### Why This Setup?

1. **GitHub Pages**: Free, reliable, no maintenance
2. **Plain HTML**: No build process, instant updates
3. **Custom Domain**: Professional appearance
4. **Simple Design**: Focuses on content, loads instantly

### Performance

The site is optimized for speed:
- Single HTML file
- Inline CSS (no external requests)
- Minimal images
- No JavaScript frameworks

### Security

- HTTPS enforced via GitHub Pages
- No user input or dynamic content
- No cookies or tracking
- Security headers via Cloudflare (if configured)

## Troubleshooting

### Site Not Updating

1. Check GitHub Actions for errors
2. Hard refresh browser (Ctrl+Shift+R)
3. Wait 5 minutes (CDN cache)

### Domain Not Working

1. Verify CNAME file exists with `grigbilham.com`
2. Check DNS settings point to `grigb.github.io`
3. Confirm repository name is exactly `grigb.github.io`

### Local Development Issues

- Use full `http://localhost:8000` (not just `localhost:8000`)
- Some browsers block local files - use a proper server
- Profile image path is absolute (`/assets/...`) so needs server

## Future Enhancements

Consider these if needed:
- Add a 404.html page
- Implement client-side search if adding multiple pages
- Add web analytics (privacy-friendly)
- Create a blog section with Jekyll (requires rebuild)

## Questions?

- GitHub Pages docs: https://docs.github.com/en/pages
- Domain setup: https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site
- Repository: https://github.com/grigb/grigb.github.io