# Deployment Guide

This guide explains how to deploy the Sagaing Fault Seismicity map to GitHub Pages.

## Prerequisites

- GitHub account
- Git installed on your computer
- Basic command line knowledge

## Step 1: Create GitHub Repository

1. Go to [GitHub](https://github.com) and log in
2. Click the **"+"** icon in the top right and select **"New repository"**
3. Repository settings:
   - **Name**: `sagaing-fault-seismicity`
   - **Description**: Interactive map of Sagaing Fault earthquakes (March-December 2025)
   - **Visibility**: Public
   - **Initialize**: ☐ Do not initialize (we have existing files)
4. Click **"Create repository"**

## Step 2: Upload Files

### Option A: Using Git Command Line

```bash
# Navigate to the project directory
cd sagaing-fault-seismicity

# Initialize git repository
git init

# Add all files
git add .

# Commit the files
git commit -m "Initial commit: Sagaing Fault seismicity map"

# Add remote repository (replace YOUR_USERNAME)
git remote add origin https://github.com/YOUR_USERNAME/sagaing-fault-seismicity.git

# Push to GitHub
git branch -M main
git push -u origin main
```

### Option B: Using GitHub Web Interface

1. Go to your new repository page
2. Click **"uploading an existing file"**
3. Drag and drop all files:
   - `index.html`
   - `README.md`
   - `LICENSE`
   - `CONTRIBUTING.md`
   - `DATA.md`
   - `.gitignore`
4. Add commit message: "Initial commit"
5. Click **"Commit changes"**

## Step 3: Enable GitHub Pages

1. Go to your repository on GitHub
2. Click **"Settings"** tab
3. Scroll to **"Pages"** in the left sidebar
4. Under **"Source"**:
   - Branch: Select `main`
   - Folder: Select `/ (root)`
5. Click **"Save"**
6. Wait a few minutes for deployment

## Step 4: Access Your Map

Your map will be available at:
```
https://YOUR_USERNAME.github.io/sagaing-fault-seismicity/
```

Example:
```
https://drtinkooo.github.io/sagaing-fault-seismicity/
```

## Step 5: Verify Deployment

1. Visit your GitHub Pages URL
2. Check that:
   - ✅ Map loads correctly
   - ✅ Earthquakes are displayed
   - ✅ Tectonic lineaments load
   - ✅ All interactive features work
   - ✅ Statistics panel shows correct data
   - ✅ Magnitude filter works
   - ✅ Layer controls function properly

## Troubleshooting

### Issue: 404 Page Not Found
**Solution**: 
- Check that `index.html` is in the root directory
- Verify GitHub Pages is enabled in Settings
- Wait 5-10 minutes after enabling Pages

### Issue: Map doesn't load
**Solution**:
- Open browser console (F12) to check for errors
- Verify internet connection (base maps require it)
- Check that earthquake data is embedded in HTML

### Issue: Tectonic lineaments don't appear
**Solution**:
- Check console for CORS or network errors
- Verify the GitHub URL for tectonic data is accessible
- Check internet connection

### Issue: Changes not appearing
**Solution**:
- Clear browser cache (Ctrl+F5 or Cmd+Shift+R)
- Wait a few minutes for GitHub Pages to rebuild
- Check that changes were committed and pushed

## Updating the Site

### Update Earthquake Data

1. Download new data from USGS
2. Update the `earthquakeData` variable in `index.html`
3. Commit and push changes:

```bash
git add index.html
git commit -m "Update earthquake data to December 31, 2025"
git push
```

4. GitHub Pages will automatically redeploy (takes 1-5 minutes)

### Update Documentation

```bash
# Make changes to README.md or other files
git add .
git commit -m "Update documentation"
git push
```

## Custom Domain (Optional)

To use a custom domain:

1. Purchase a domain from a registrar (e.g., Namecheap, GoDaddy)
2. In your repository Settings > Pages:
   - Enter your custom domain
   - Click "Save"
3. Configure DNS with your registrar:
   - Add A records pointing to GitHub Pages IPs:
     - 185.199.108.153
     - 185.199.109.153
     - 185.199.110.153
     - 185.199.111.153
   - Or add CNAME record: `YOUR_USERNAME.github.io`
4. Wait for DNS propagation (can take 24-48 hours)
5. Enable HTTPS in GitHub Pages settings

## Performance Tips

### Optimize Load Time
- ✅ Data is already embedded (no external JSON calls)
- ✅ Using CDN for Leaflet library
- ✅ Minimal external dependencies

### Caching
GitHub Pages automatically caches static files for faster subsequent loads.

### Analytics (Optional)
Add Google Analytics to track visitors:

1. Get Google Analytics tracking code
2. Add to `index.html` before `</head>`:

```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_MEASUREMENT_ID');
</script>
```

## Security

### HTTPS
- ✅ GitHub Pages provides free HTTPS
- ✅ Certificate automatically managed
- ✅ All connections are secure

### Data Privacy
- ✅ No personal data collected
- ✅ No cookies used
- ✅ USGS earthquake data is public domain

## Monitoring

Check deployment status:
1. Go to repository "Actions" tab
2. View deployment workflows
3. Check for any errors

## Backup

Regular backups:
```bash
# Clone to backup location
git clone https://github.com/YOUR_USERNAME/sagaing-fault-seismicity.git backup/

# Or pull latest changes
cd backup/sagaing-fault-seismicity
git pull
```

## Support

If you encounter issues:
1. Check [GitHub Pages documentation](https://docs.github.com/en/pages)
2. Open an issue in the repository
3. Check GitHub Status page for service disruptions

## Next Steps

After successful deployment:
- ✅ Share your map URL
- ✅ Add to your profile README
- ✅ Submit to relevant research communities
- ✅ Consider publishing a paper about the visualization
- ✅ Keep data updated with latest earthquakes

---

**Congratulations!** Your interactive earthquake map is now live on the web! 🌍🎉
