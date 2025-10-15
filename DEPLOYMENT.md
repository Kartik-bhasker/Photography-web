# Netlify Deployment Guide - FIXED VERSION

## ✅ This Will Work - Follow These Steps

### Method 1: Clean Upload (RECOMMENDED)
1. **Create a new folder** with ONLY these files:
   - `index.html`
   - `netlify.toml`
   - `_headers`
   - `_redirects`
   - `package-static.json` (rename to `package.json`)
   - All your image files (wedding hover.jpg, etc.)
   - All your video files (wedding video.mp4, etc.)

2. **Zip this folder** and upload to Netlify

### Method 2: Use Netlify Dashboard Settings
1. Go to your Netlify site dashboard
2. Navigate to **Site settings** → **Build & deploy** → **Build settings**
3. Set the following:
   - **Build command**: `echo "Static HTML site"`
   - **Publish directory**: `.` (dot - current directory)
   - **Base directory**: (leave empty)
4. Go to **Plugins** and **REMOVE** any Next.js plugins
5. Deploy again

### Method 3: Replace package.json
1. **Backup** your current `package.json` (rename to `package-nextjs.json`)
2. **Rename** `package-static.json` to `package.json`
3. Upload all files

### Files Included:
- ✅ `netlify.toml` - Fixed configuration (no Next.js plugins)
- ✅ `_headers` - Security headers
- ✅ `_redirects` - URL redirects
- ✅ `package-static.json` - Simple package.json
- ✅ `.netlifyignore` - Excludes Next.js files

### What's Fixed:
- ❌ Removed problematic Next.js plugin configuration
- ❌ No more "disable" input errors
- ❌ No more publish directory conflicts
- ✅ Clean static HTML deployment
