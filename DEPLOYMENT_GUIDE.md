# Event Sentinel Documentation - Deployment Guide

This guide will help you deploy the Event Sentinel documentation to GitHub Pages.

## What Was Created

A complete documentation suite has been created in the `docs/` folder, including:

### Documentation Pages
- **Homepage** (`index.md`) - Welcome page with quick links
- **Getting Started** (`getting-started.md`) - Complete setup guide
- **Features** (`features.md`) - Detailed feature documentation
- **Configuration** (`configuration.md`) - Configuration guide
- **Commands** (`commands.md`) - Commands reference
- **FAQ** (`faq.md`) - Frequently asked questions
- **Support** (`support.md`) - Support information
- **Privacy Policy** (`privacy-policy.md`) - Privacy policy
- **Terms of Service** (`terms-of-service.md`) - Terms of service

### Configuration Files
- `_config.yml` - Jekyll configuration for GitHub Pages
- `_data/navigation.yml` - Navigation structure
- `Gemfile` - Ruby dependencies
- `.github/workflows/pages.yml` - Automatic deployment workflow

## Deployment Options

### Option 1: Deploy from This Repository

If you want to deploy from the main repository:

1. **Enable GitHub Pages:**
   - Go to your repository on GitHub
   - Navigate to Settings → Pages
   - Under "Source", select "Deploy from a branch"
   - Choose branch: `main` (or `gh-pages`)
   - Choose folder: `/docs`
   - Click Save

2. **Update Configuration:**
   - Edit `docs/_config.yml`
   - Update `url` and `baseurl` to match your repository:
     ```yaml
     url: https://YOUR_USERNAME.github.io
     baseurl: /YOUR_REPO_NAME
     ```
   - Update `github.repository_url` if needed

3. **Push and Deploy:**
   - The GitHub Actions workflow will automatically build and deploy
   - Your site will be available at: `https://YOUR_USERNAME.github.io/YOUR_REPO_NAME/`

### Option 2: Create a Separate Docs Repository (Recommended)

This is the recommended approach for cleaner organization:

1. **Create New Repository:**
   - Create a new repository named `Event-Sentinel-docs` (or your preferred name)
   - Make it public (required for free GitHub Pages)

2. **Copy Documentation:**
   - Copy the entire `docs/` folder to the new repository
   - Copy `.github/workflows/pages.yml` to the new repository
   - Commit and push

3. **Update Configuration:**
   - Edit `docs/_config.yml` in the new repository:
     ```yaml
     url: https://YOUR_USERNAME.github.io
     baseurl: /Event-Sentinel-docs  # or your repo name
     ```

4. **Enable GitHub Pages:**
   - Go to Settings → Pages
   - Source: "GitHub Actions" (the workflow will handle deployment)
   - Or use "Deploy from a branch" → `main` → `/docs`

5. **Access Your Site:**
   - Your documentation will be at: `https://YOUR_USERNAME.github.io/Event-Sentinel-docs/`

## Configuration Details

### Updating Repository URLs

Before deploying, update these in `docs/_config.yml`:

```yaml
# For user/organization pages (username.github.io):
url: https://username.github.io
baseurl: ""

# For project pages (username.github.io/repo-name):
url: https://username.github.io
baseurl: "/repository-name"
```

### Customizing the Theme

The documentation uses the "Just the Docs" theme. You can customize:

- **Color Scheme:** Change `color_scheme` in `_config.yml`:
  - `light` - Light theme
  - `dark` - Dark theme
  - `auto` - Follows system preference

- **Navigation:** Edit `_data/navigation.yml` to modify the sidebar

- **Colors:** Customize embed colors in the configuration guide

## Testing Locally

Before deploying, test locally:

1. **Install Ruby and Bundler** (if not installed)
   - Windows: Download from [rubyinstaller.org](https://rubyinstaller.org/)
   - Mac: `brew install ruby`
   - Linux: `sudo apt-get install ruby-full`

2. **Install Dependencies:**
   ```bash
   cd docs
   bundle install
   ```

3. **Run Jekyll:**
   ```bash
   bundle exec jekyll serve
   ```

4. **View Locally:**
   - Open http://localhost:4000 in your browser
   - Make changes and see them update automatically

## Troubleshooting

### GitHub Pages Not Updating

- **Check Actions Tab:** Verify the workflow ran successfully
- **Wait a Few Minutes:** Deployment can take 1-5 minutes
- **Check Settings:** Ensure GitHub Pages is enabled
- **Verify Branch:** Make sure you're pushing to the correct branch

### Build Errors

- **Check `_config.yml`:** Ensure YAML syntax is correct
- **Verify Dependencies:** Run `bundle install` in the `docs/` folder
- **Check Logs:** Review GitHub Actions logs for specific errors

### Missing Theme

- **Verify Remote Theme:** Check `remote_theme: just-the-docs/just-the-docs` in `_config.yml`
- **Check Gemfile:** Ensure `jekyll-remote-theme` is included
- **Update Dependencies:** Run `bundle update`

### 404 Errors

- **Check Base URL:** Verify `baseurl` in `_config.yml` matches your repository name
- **Verify Links:** Ensure internal links use `{{ site.baseurl }}` prefix
- **Check Permalinks:** Verify page front matter is correct

## Customization

### Adding New Pages

1. Create a new `.md` file in `docs/`
2. Add front matter:
   ```yaml
   ---
   layout: default
   title: Your Page Title
   nav_order: 10
   ---
   ```
3. Add to `_data/navigation.yml` if needed

### Modifying Content

- All pages are in Markdown format
- Edit any `.md` file to update content
- Use Jekyll/Liquid syntax for dynamic content
- Images go in `assets/images/` (create if needed)

## Next Steps

1. ✅ Review and customize the documentation
2. ✅ Update repository URLs in `_config.yml`
3. ✅ Test locally (optional but recommended)
4. ✅ Deploy to GitHub Pages
5. ✅ Share the documentation URL with users

## Support

For issues with deployment:

- Check [GitHub Pages Documentation](https://docs.github.com/pages)
- Review [Jekyll Documentation](https://jekyllrb.com/docs/)
- See [Just the Docs Theme Docs](https://just-the-docs.github.io/just-the-docs/)
- Open an issue in your repository

---

**Your documentation is ready to deploy!** Follow the steps above to get it live on GitHub Pages.

