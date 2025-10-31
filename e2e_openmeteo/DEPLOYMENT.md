# OpenMeteo ETL - Documentation Deployment Guide

## Overview

The OpenMeteo project documentation has been redesigned to match your main portfolio with a modern dark theme, visual focus, and professional styling.

## What Was Changed

### 1. **MkDocs Configuration** (`mkdocs.yml`)
- Material theme with slate (dark) color scheme
- Cyan/blue accent colors matching main portfolio
- Navigation structure with tabs
- Custom CSS integration
- Social links and repository integration

### 2. **Custom Styling** (`docs/stylesheets/custom.css`)
- Dark theme matching main portfolio colors
- Feature cards with hover effects
- Hero section with gradient text
- Stats cards and tech stack grid
- Button styles and animations
- Enhanced dashboard preview styling

### 3. **Landing Page** (`docs/index.md`)
- Visual hero section with project overview
- 6 key feature cards with icons
- Prominent dashboard screenshot
- Enhanced architecture diagram (Mermaid)
- Tech stack showcase grid
- Key metrics with statistics
- "What Makes This Stand Out" section
- Quick start CTAs

### 4. **Dashboard Page** (`docs/dashboard.md`)
- Expanded dashboard documentation
- Feature highlights with visual cards
- Technical implementation details
- Setup instructions
- Potential extensions section

### 5. **GitHub Actions** (`.github/workflows/deploy-openmeteo-docs.yml`)
- Automatic deployment on push to main
- Builds and deploys to GitHub Pages
- Triggers only when docs or config change

## How to Deploy

### Option 1: Automatic Deployment (Recommended)

1. **Push to GitHub:**
   ```bash
   cd "F:\Projects\Github page\a-chmielewski.github.io"
   git add .
   git commit -m "Redesign OpenMeteo docs with dark theme"
   git push origin main
   ```

2. **GitHub Actions will automatically:**
   - Detect changes in `e2e_openmeteo/docs/` or `e2e_openmeteo/mkdocs.yml`
   - Install dependencies
   - Build the MkDocs site
   - Deploy to `gh-pages` branch
   - Site will be live at: `https://a-chmielewski.github.io/endtoend-etl-openmeteo/`

3. **Monitor deployment:**
   - Go to: `https://github.com/a-chmielewski/a-chmielewski.github.io/actions`
   - Watch the "Deploy OpenMeteo Docs" workflow

### Option 2: Manual Deployment

From the `e2e_openmeteo` directory:

```bash
# Install dependencies (if not already installed)
pip install mkdocs-material pymdown-extensions

# Preview locally first
mkdocs serve
# Open http://127.0.0.1:8000

# Deploy to GitHub Pages
mkdocs gh-deploy --force --clean
```

## Testing Locally

Before pushing, test the site locally:

```bash
cd e2e_openmeteo
mkdocs serve
```

Open `http://127.0.0.1:8000` in your browser to preview the site with live reload.

## GitHub Pages Configuration

Ensure GitHub Pages is configured correctly:

1. Go to repository **Settings** → **Pages**
2. **Source**: Deploy from a branch
3. **Branch**: `gh-pages` / `/ (root)`
4. **Custom domain** (optional): Leave blank for default

## Troubleshooting

### If GitHub Actions fails:

1. Check the Actions tab for error logs
2. Verify `mkdocs.yml` syntax is correct
3. Ensure all referenced files exist in `docs/`

### If site doesn't update:

1. Clear browser cache (Ctrl+Shift+R / Cmd+Shift+R)
2. Wait 2-3 minutes for GitHub Pages to update
3. Check if workflow completed successfully

### If images don't load:

1. Verify `assets/dashboard.png` exists in `docs/assets/`
2. Check image paths in markdown files
3. Rebuild with `mkdocs build --clean`

## File Structure

```
e2e_openmeteo/
├── mkdocs.yml                  # MkDocs configuration
├── docs/
│   ├── index.md               # Landing page (NEW design)
│   ├── dashboard.md           # Dashboard page (ENHANCED)
│   ├── architecture.md        # Architecture docs
│   ├── data_model.md          # Data model docs
│   ├── data_qulaity.md        # Data quality docs
│   ├── how_to_run.md          # Setup guide
│   ├── credits.md             # Credits
│   ├── stylesheets/
│   │   └── custom.css         # Custom styling (NEW)
│   ├── assets/
│   │   └── dashboard.png      # Dashboard screenshot
│   └── dbt/
│       └── index.html         # dbt docs
└── site/                      # Built site (auto-generated, ignored by git)
```

## Color Scheme (Matching Main Portfolio)

- **Primary Background**: `#0a0e27`
- **Secondary Background**: `#151a30`
- **Tertiary Background**: `#1e2542`
- **Accent Color**: `#00d4ff` (cyan/blue)
- **Text Primary**: `#ffffff`
- **Text Secondary**: `#b8c5d6`
- **Border Color**: `#2a3551`

## Next Steps

1. **Review locally** using `mkdocs serve`
2. **Commit and push** changes
3. **Monitor GitHub Actions** deployment
4. **Share the link** with potential employers!

The new design is:
- ✅ Visually stunning with modern dark theme
- ✅ Matches main portfolio aesthetic
- ✅ Highlights dashboard prominently
- ✅ Professional and impressive
- ✅ Mobile responsive
- ✅ Fast loading with optimized CSS

## Live URLs

After deployment:

- **Main Portfolio**: https://a-chmielewski.github.io/
- **OpenMeteo Project**: https://a-chmielewski.github.io/endtoend-etl-openmeteo/
- **GitHub Repo**: https://github.com/a-chmielewski/a-chmielewski.github.io

