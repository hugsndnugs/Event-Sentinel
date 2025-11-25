# Event Sentinel Documentation Suite

This repository contains a complete documentation suite for Event Sentinel, ready to be deployed to GitHub Pages.

## Quick Start

### Option 1: Use This Repository for Docs

1. **Create a new repository** named `Event-Sentinel-docs` (or your preferred name)
2. **Copy the `docs/` folder** to the new repository
3. **Enable GitHub Pages** in repository settings:
   - Go to Settings → Pages
   - Source: Deploy from a branch
   - Branch: `main` (or `gh-pages`)
   - Folder: `/docs` (or root if you move files)
4. **Push the files** and wait for GitHub Actions to deploy

### Option 2: Add to Existing Repository

1. **Create a `docs/` branch** or use the `main` branch
2. **Copy the `docs/` folder** to your repository
3. **Enable GitHub Pages** pointing to the `docs/` folder
4. **GitHub Actions will automatically deploy** on push to `main`

## Repository Structure

```
Event-Sentinel-docs/
├── docs/
│   ├── _config.yml          # Jekyll configuration
│   ├── _data/
│   │   └── navigation.yml   # Navigation structure
│   ├── index.md             # Homepage
│   ├── getting-started.md   # Setup guide
│   ├── features.md          # Features documentation
│   ├── configuration.md     # Configuration guide
│   ├── commands.md          # Commands reference
│   ├── faq.md               # FAQ
│   ├── support.md           # Support page
│   ├── privacy-policy.md    # Privacy policy
│   ├── terms-of-service.md  # Terms of service
│   ├── Gemfile              # Ruby dependencies
│   ├── README.md            # Docs README
│   └── assets/
│       └── css/
│           └── custom.css   # Custom styles
├── .github/
│   └── workflows/
│       └── pages.yml        # GitHub Actions deployment
└── README_DOCS.md          # This file
```

## Configuration

### Update Repository URLs

Before deploying, update the following in `docs/_config.yml`:

```yaml
url: https://YOUR_USERNAME.github.io
baseurl: /YOUR_REPO_NAME

github:
  repository_url: https://github.com/YOUR_USERNAME/YOUR_REPO_NAME
```

### Customize Theme

The documentation uses the "Just the Docs" theme. You can customize:

- Colors in `_config.yml` (`color_scheme`)
- Navigation in `_data/navigation.yml`
- Content in individual markdown files

## Local Development

To preview the documentation locally:

1. **Install Ruby and Bundler** (if not already installed)
2. **Navigate to docs folder:**
   ```bash
   cd docs
   ```
3. **Install dependencies:**
   ```bash
   bundle install
   ```
4. **Run Jekyll:**
   ```bash
   bundle exec jekyll serve
   ```
5. **Open browser:**
   ```
   http://localhost:4000
   ```

## Deployment

### Automatic Deployment (Recommended)

The included GitHub Actions workflow (`.github/workflows/pages.yml`) will automatically deploy your documentation when you push to the `main` branch.

**Requirements:**
- GitHub Pages must be enabled in repository settings
- The workflow will handle building and deploying automatically

### Manual Deployment

1. Build the site:
   ```bash
   cd docs
   bundle exec jekyll build
   ```
2. Push the `_site` folder to the `gh-pages` branch (or use GitHub Pages source setting)

## Customization

### Adding New Pages

1. Create a new `.md` file in the `docs/` directory
2. Add front matter:
   ```yaml
   ---
   layout: default
   title: Your Page Title
   nav_order: 10
   ---
   ```
3. Add to `_data/navigation.yml` if you want it in the navigation

### Modifying Navigation

Edit `docs/_data/navigation.yml` to change the navigation structure.

### Changing Colors

Modify `color_scheme` in `_config.yml`:
- `light` - Light theme
- `dark` - Dark theme  
- `auto` - Follows system preference

## Troubleshooting

### GitHub Pages Not Updating

- Check GitHub Actions workflow status
- Verify GitHub Pages is enabled in settings
- Ensure the workflow file is in `.github/workflows/`
- Wait a few minutes for deployment to complete

### Local Jekyll Errors

- Ensure Ruby 3.1+ is installed
- Run `bundle update` to update dependencies
- Check for syntax errors in `_config.yml`

### Missing Theme

- Verify `remote_theme: just-the-docs/just-the-docs` in `_config.yml`
- Check that `jekyll-remote-theme` is in `Gemfile`
- Run `bundle install` again

## Support

For issues with the documentation:

1. Check the [Jekyll documentation](https://jekyllrb.com/docs/)
2. Review [Just the Docs theme docs](https://just-the-docs.github.io/just-the-docs/)
3. Open an issue in the repository

## License

This documentation suite is provided as-is for use with Event Sentinel.

---

**Ready to deploy?** Follow the Quick Start guide above and your documentation will be live on GitHub Pages!

