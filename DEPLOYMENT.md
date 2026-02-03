# TopShelf Website Deployment

**Site:** mytopshelf.app
**Hosting:** Netlify
**Repo:** github.com/Staebos/topshelf-website

---

## Auto-Deploy Setup

**Status:** ✅ Configured and working

- **Connected to:** GitHub repository (topshelf-website)
- **Branch:** main
- **Deploy trigger:** Automatic on push to main
- **Build command:** None (static HTML/CSS)
- **Publish directory:** / (root)

---

## Making Updates

### Standard Workflow (Auto-Deploy)

1. **Edit files locally:**
   ```bash
   cd ~/Development/claude-workspaces/topshelf-website
   # Edit index.html, style.css, etc.
   ```

2. **Commit and push:**
   ```bash
   git add .
   git commit -m "Description of changes"
   git push origin main
   ```

3. **Wait for auto-deploy:**
   - Netlify detects the push via webhook
   - Usually takes 30-60 seconds
   - Site auto-deploys to mytopshelf.app

### Manual Deploy (If Auto-Deploy Fails)

**Via Netlify Dashboard:**
1. Go to https://app.netlify.com
2. Select "mytopshelf.app" project
3. Click "Deploys" in sidebar
4. Click "Trigger deploy" → "Deploy site"

**Via Command Line (Faster):**
```bash
# Install Netlify CLI (one-time)
npm install -g netlify-cli

# Login to Netlify (one-time)
netlify login

# Deploy from website directory
cd ~/Development/claude-workspaces/topshelf-website
netlify deploy --prod

# Or shorter version
cd ~/Development/claude-workspaces/topshelf-website && netlify deploy --prod
```

---

## Quick Deploy Command

**Copy/paste this when you need to deploy:**

```bash
cd ~/Development/claude-workspaces/topshelf-website && \
git add . && \
git commit -m "Update website" && \
git push origin main && \
echo "✅ Pushed to GitHub - Netlify will auto-deploy in ~60 seconds"
```

**Or force manual deploy:**

```bash
cd ~/Development/claude-workspaces/topshelf-website && netlify deploy --prod
```

---

## Current Deployment Info

**Site ID:** hilarious-mandazi-0e48a3
**Site URL:** https://mytopshelf.app
**Admin URL:** https://app.netlify.com/sites/hilarious-mandazi-0e48a3

**Latest Production Deploy:**
- Commit: c63fd0d
- Message: "Update download link to v1.2.0 signed ZIP"
- Date: 2026-02-03
- Status: Published ✅

**Download Link:**
- Points to: `https://github.com/Staebos/TopShelf/releases/download/v1.2.0/TopShelf-1.2.0-signed.zip`

---

## Troubleshooting

### Site not updating after push?

**Check deploy status:**
```bash
cd ~/Development/claude-workspaces/topshelf-website
netlify status
```

**View recent deploys:**
```bash
netlify deploy:list
```

**Check if auto-deploy is enabled:**
1. Netlify Dashboard → Site settings → Build & deploy
2. Look for "Build hooks" section
3. Verify GitHub webhook is active

**Manual trigger if auto-deploy stuck:**
```bash
cd ~/Development/claude-workspaces/topshelf-website
netlify deploy --prod
```

### Wrong content showing?

**Clear browser cache:**
- Hard refresh: Cmd+Shift+R (Chrome/Safari)
- Or open in incognito/private window

**Check what's actually deployed:**
```bash
curl -I https://mytopshelf.app/index.html
# Look at Last-Modified date
```

### Deploy failed?

**View build logs:**
1. Netlify Dashboard → Deploys
2. Click on failed deploy
3. Scroll to "Deploy log"

**Common issues:**
- Missing files referenced in HTML
- Large images (>10MB)
- Syntax errors in HTML/CSS

---

## File Structure

```
topshelf-website/
├── index.html              # Main landing page
├── style.css               # All styles
├── README.md               # Development docs
├── DEPLOYMENT.md           # This file
├── favicon-*.png           # Favicons
├── apple-touch-icon.png    # iOS icon
└── images/                 # Screenshots & assets
    ├── logo.png
    ├── hero-*.png
    ├── ui-*.png
    └── og-image.png
```

---

## Domain Configuration

**Domain:** mytopshelf.app
**Registrar:** Namecheap
**DNS:** Managed by Netlify

**DNS Records (configured at Namecheap):**
- A record → Netlify IP
- CNAME www → mytopshelf.app
- All managed through Netlify's DNS service

**To check DNS:**
```bash
dig mytopshelf.app
nslookup mytopshelf.app
```

---

## Security

**HTTPS:** ✅ Enabled (Let's Encrypt)
**Certificate:** Auto-renewed by Netlify
**Force HTTPS:** Enabled (redirects HTTP → HTTPS)

---

## Common Tasks

### Update Download Link

**File to edit:** `index.html`
**Lines to change:** 58, 253

```html
<!-- Hero section (line ~58) -->
<a href="#download" class="btn btn-primary">Download for macOS</a>

<!-- Download section (line ~253) -->
<a href="https://github.com/Staebos/TopShelf/releases/download/v1.2.0/TopShelf-1.2.0-signed.zip" class="btn btn-primary btn-large">Download TopShelf v1.2.0</a>
```

**After editing:**
```bash
cd ~/Development/claude-workspaces/topshelf-website
git add index.html
git commit -m "Update download link to v1.X.X"
git push origin main
```

### Add New Screenshot

1. Save image to `images/` folder
2. Reference in HTML: `<img src="images/your-image.png" alt="Description">`
3. Commit and push:
   ```bash
   git add images/your-image.png index.html
   git commit -m "Add new screenshot"
   git push origin main
   ```

### Change Site Title/Description

**File:** `index.html`
**Lines:** 6-20 (meta tags)

```html
<title>TopShelf - Your Top Priorities, Beautifully Organized</title>
<meta name="description" content="...">
```

---

## Performance

**Current metrics:**
- Load time: < 2 seconds
- Page size: ~18MB (includes screenshots)
- Lighthouse score: (check with Chrome DevTools)

**Optimization tips:**
- Compress images before uploading
- Use WebP format for better compression
- Enable Netlify's image optimization (Asset Optimization settings)

---

## Rollback

**If deployment breaks the site:**

1. **Via Netlify Dashboard:**
   - Deploys → Click on previous working deploy
   - Click "Publish deploy" button

2. **Via Git:**
   ```bash
   cd ~/Development/claude-workspaces/topshelf-website
   git revert HEAD
   git push origin main
   ```

---

## Analytics (Future)

**Not yet configured.**

Options:
- Netlify Analytics ($9/mo)
- Google Analytics (free)
- Plausible Analytics ($9/mo, privacy-focused)
- Fathom Analytics ($14/mo, privacy-focused)

---

**Last Updated:** 2026-02-03
**Maintained By:** Jeffrey Staebler

**See also:**
- Website README.md (development instructions)
- TopShelf CLAUDE.md (main project docs)
- TopShelf DISTRIBUTION.md (app distribution)
