# Plattentaufe – Hugo Site

Travel blog converted from Jimdo Free to Hugo static site, deployed via GitHub Pages.

## Structure

```
hugo-site/
├── content/
│   ├── _index.md          # Homepage
│   ├── posts/             # Blog posts (YYYY-MM-DD-slug.md)
│   ├── galerie/           # Gallery page
│   ├── ueber-uns/         # About page
│   ├── kontakt/           # Contact page
│   └── impressum/         # Legal notice
├── themes/plattentaufe/   # Custom theme
│   ├── assets/css/        # Stylesheets
│   ├── layouts/           # Hugo templates
│   └── layouts/shortcodes/gallery.html
├── .github/workflows/     # CI/CD pipeline
└── hugo.toml              # Site configuration
```

## Local development

```bash
# Install Hugo extended (≥ 0.128)
# https://github.com/gohugoio/hugo/releases

cd hugo-site
hugo server --buildDrafts
# → http://localhost:1313/
```

## Deployment

Push to `main` branch → GitHub Actions builds and deploys to GitHub Pages.

### Setup

1. Create a GitHub repository
2. Push this `hugo-site/` folder (or the whole workspace)
3. In repo **Settings → Pages**, set source to **GitHub Actions**
4. Update `baseURL` in `hugo.toml` to match your GitHub Pages URL:
   ```toml
   baseURL = "https://YOUR-USERNAME.github.io/YOUR-REPO/"
   ```

## Content migration

Blog posts were converted from the original Jimdo export using `../convert.py`.
Images remain hosted on the Jimdo CDN (`image.jimcdn.com`) – no image files are
stored in this repository.

To re-run the conversion:
```bash
cd ..   # workspace root
python3 convert.py
```
