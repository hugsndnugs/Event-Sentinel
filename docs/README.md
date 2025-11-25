# Event Sentinel Documentation

This directory contains the documentation for Event Sentinel, built with Jekyll and the "Just the Docs" theme for GitHub Pages.

## Local Development

To test the documentation locally:

1. Install Ruby and Bundler
2. Install dependencies:
   ```bash
   cd docs
   bundle install
   ```
3. Run Jekyll:
   ```bash
   bundle exec jekyll serve
   ```
4. Open http://localhost:4000 in your browser

## Structure

- `_config.yml` - Jekyll configuration
- `_data/navigation.yml` - Navigation structure
- `index.md` - Homepage
- `getting-started.md` - Setup guide
- `features.md` - Feature documentation
- `configuration.md` - Configuration guide
- `commands.md` - Commands reference
- `faq.md` - Frequently asked questions
- `support.md` - Support information
- `privacy-policy.md` - Privacy policy
- `terms-of-service.md` - Terms of service

## Deployment

The documentation is automatically deployed to GitHub Pages via GitHub Actions when changes are pushed to the `main` branch.

## Theme

This documentation uses the [Just the Docs](https://just-the-docs.github.io/just-the-docs/) Jekyll theme.

