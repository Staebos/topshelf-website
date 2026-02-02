# TopShelf Landing Page

Simple, beautiful landing page for TopShelf macOS app.

## Tech Stack

- **Pure HTML/CSS** - No frameworks, no build steps
- **Inter Font** - Google Fonts
- **Responsive** - Mobile, tablet, desktop

## Local Development

Simply open `index.html` in your browser:

```bash
open index.html
```

Or use a local server:

```bash
python3 -m http.server 8000
# Visit http://localhost:8000
```

## Deployment Options

### Option 1: GitHub Pages (Free, Recommended)

1. Push this repo to GitHub
2. Go to repo Settings → Pages
3. Source: Deploy from branch `main`
4. Folder: `/ (root)`
5. Save

Your site will be live at: `https://yourusername.github.io/topshelf-website`

**Custom Domain:**
- Add `CNAME` file with `mytopshelf.app`
- Configure DNS at Namecheap:
  - A record: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
  - CNAME record: `www` → `yourusername.github.io`

### Option 2: Netlify (Free, Auto-Deploy)

1. Push this repo to GitHub
2. Go to [netlify.com](https://netlify.com) and sign up
3. "New site from Git" → Connect your repo
4. Deploy settings:
   - Build command: (leave empty)
   - Publish directory: (leave empty or `/`)
5. Deploy!

Your site will be live at: `https://random-name.netlify.app`

**Custom Domain:**
- Netlify dashboard → Domain settings → Add custom domain
- Enter `mytopshelf.app`
- Update DNS at Namecheap to point to Netlify

### Option 3: Vercel (Free)

Similar to Netlify:
1. Push to GitHub
2. Import at [vercel.com](https://vercel.com)
3. Auto-deploys on every commit

## Adding Images

### Screenshots

Replace the placeholder in the hero section:

```html
<!-- In index.html, replace: -->
<div class="mockup-placeholder">
    <div class="mockup-text">App Screenshot</div>
</div>

<!-- With: -->
<img src="images/hero-screenshot.png" alt="TopShelf App" class="hero-screenshot">
```

### Favicons

Add favicon files to root:
- `favicon-16x16.png`
- `favicon-32x32.png`
- `apple-touch-icon.png` (180×180)

### OG Images

Add social media preview image:
- `images/og-image.jpg` (1200×630)

## Brand Colors

- **Cream:** `#FAF6F1` (background)
- **Burnt Orange:** `#D97636` (primary/CTA)
- **Charcoal:** `#2B2B2B` (text)
- **Sage Green:** `#8FAA8E` (accent)
- **Warm Brown:** `#8B6F47` (accent)

## File Structure

```
topshelf-website/
├── index.html          # Main landing page
├── style.css           # All styles
├── README.md           # This file
├── favicon-*.png       # Favicons (add these)
├── CNAME              # Custom domain (for GitHub Pages)
└── images/            # Screenshots & assets (add these)
    └── og-image.jpg
```

## Maintenance

This is a static site - no backend, no database, no dependencies.

To update:
1. Edit `index.html` or `style.css`
2. Commit and push to GitHub
3. Site auto-deploys (if using Netlify/Vercel/GitHub Pages)

## License

Same as TopShelf app - see main repository.
