# Tennis Activity Redirect Site

This is a simple static site that permanently redirects all traffic to https://activity-tennis.apps.stdiox.com/

## Quick Deploy to Netlify

### Option 1: Drag & Drop (Easiest)
1. Go to [Netlify Drop](https://app.netlify.com/drop)
2. Drag and drop the entire `tennis-redirect` folder
3. Done! Your site will be live instantly

### Option 2: Git + Netlify (Recommended for updates)
1. Initialize git in this folder:
   ```bash
   git init
   git add .
   git commit -m "Initial commit: redirect site"
   ```
2. Push to GitHub/GitLab/Bitbucket
3. Go to [Netlify](https://app.netlify.com/)
4. Click "Add new site" → "Import an existing project"
5. Connect your repository
6. Netlify will auto-detect the configuration and deploy

### Option 3: Netlify CLI
```bash
# Install Netlify CLI if you haven't already
npm install -g netlify-cli

# Login to Netlify
netlify login

# Deploy
cd tennis-redirect
netlify deploy --prod
```

## How it works

The redirect is implemented using three methods for maximum compatibility:

1. **Netlify's `_redirects` file**: Server-side 301 permanent redirect (primary method)
2. **netlify.toml configuration**: Backup server-side redirect configuration
3. **HTML meta refresh + JavaScript**: Client-side fallback for browsers

All paths are preserved during the redirect (e.g., `/page` → `https://activity-tennis.apps.stdiox.com/page`)

## Files

- `index.html` - Fallback HTML page with meta refresh and JavaScript redirect
- `_redirects` - Netlify redirects configuration (primary method)
- `netlify.toml` - Netlify build and redirect configuration
- `README.md` - This file

## Features

✅ **SEO-Friendly**: Uses 301 permanent redirects  
✅ **Path Preservation**: All paths are maintained in the redirect  
✅ **No Build Required**: Pure static files  
✅ **Multiple Fallbacks**: Works even if server-side redirects fail  
✅ **Instant Redirect**: Near-zero latency with Netlify's edge network

## Custom Domain (Optional)

After deploying, you can set up a custom domain in Netlify:
1. Go to Site settings → Domain management
2. Add your custom domain
3. Configure DNS as instructed by Netlify
4. Enable HTTPS (automatic with Netlify)

---

**Deploy Date**: February 26, 2026  
**Target URL**: https://activity-tennis.apps.stdiox.com/

