# Event Sentinel Documentation

This directory contains the documentation site for Event Sentinel, designed to be hosted on GitHub Pages.

## Structure

- `index.html` - Main landing page
- `features.html` - Complete feature list
- `setup.html` - Setup and installation guide
- `configuration.html` - Configuration options
- `privacy.html` - Privacy Policy
- `terms.html` - Terms of Service
- `styles.css` - Main stylesheet

## GitHub Pages Setup

To deploy this documentation to GitHub Pages:

1. **Enable GitHub Pages:**
   - Go to your repository settings
   - Navigate to "Pages" in the left sidebar
   - Under "Source", select the branch containing the `docs` folder
   - Select `/docs` as the folder
   - Click "Save"

2. **Access Your Site:**
   - Your documentation will be available at:
   - `https://<username>.github.io/<repository-name>/`

3. **Custom Domain (Optional):**
   - Add a `CNAME` file in the `docs` folder with your domain name
   - Configure DNS settings as per GitHub's instructions

## Local Testing

To test the documentation locally, simply open `index.html` in a web browser or use a local server:

```bash
# Using Python
python -m http.server 8000

# Using Node.js (http-server)
npx http-server

# Then visit http://localhost:8000
```

## Notes

- The `.nojekyll` file tells GitHub Pages to serve the site as static HTML without Jekyll processing
- All pages use relative links, so they work both locally and on GitHub Pages
- The site is fully responsive and works on mobile devices


