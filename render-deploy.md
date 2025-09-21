# Deploy Mind AR App on Render

## Method 1: GitHub + Render (Recommended)

### Step 1: Push to GitHub
```bash
# Create GitHub repo first at https://github.com/new
git remote add origin https://github.com/YOUR_USERNAME/mind-ar-app.git
git push -u origin main
```

### Step 2: Deploy on Render
1. Go to https://render.com
2. Sign up/login with GitHub
3. Click "New +" → "Static Site"
4. Connect your GitHub repository
5. Configure:
   - **Build Command**: Leave empty (static files)
   - **Publish Directory**: `.` (root directory)
6. Click "Create Static Site"
7. Get your URL: `https://your-app-name.onrender.com`

## Method 2: Manual Upload

### Step 1: Create ZIP file
```bash
# Create deployment package (excluding .git)
tar -czf mind-ar-app.tar.gz --exclude='.git' --exclude='.claude' .
```

### Step 2: Upload to Render
1. Go to https://render.com
2. New + → Static Site
3. Choose "Deploy an existing image or build from a Git repository"
4. Upload your ZIP file
5. Configure and deploy

## Configuration for Render

### Create render.yaml (optional)
```yaml
services:
  - type: web
    name: mind-ar-app
    env: static
    buildCommand: ""
    staticPublishPath: .
    routes:
      - type: rewrite
        source: /*
        destination: /index.html
```

## Important Notes for AR Apps on Render

### HTTPS ✅
- Render provides HTTPS automatically
- Required for camera access on mobile

### File Paths ✅
- Your current setup works perfectly
- Static files served correctly

### Mobile Compatibility ✅
- Works on all mobile browsers
- Camera permissions handled properly

## Testing on Mobile

1. **Deploy to Render** → Get HTTPS URL
2. **Open URL on mobile browser**
3. **Allow camera permissions**
4. **Print target image** (`targets/target-1.png`)
5. **Point camera at target**
6. **Video appears in AR!**

## Quick Deploy Steps

1. **Push to GitHub**:
   ```bash
   git remote add origin https://github.com/YOUR_USERNAME/REPO_NAME.git
   git push -u origin main
   ```

2. **Deploy on Render**:
   - Connect GitHub repo
   - Deploy as Static Site
   - Get HTTPS URL

3. **Test on mobile** with target image

## Render Advantages

- ✅ **Free tier available**
- ✅ **Automatic HTTPS**
- ✅ **GitHub integration**
- ✅ **Auto-deploy on commits**
- ✅ **Global CDN**
- ✅ **Mobile optimized**

## Alternative: Direct Upload

If you don't want to use GitHub:
1. Zip your project folder
2. Use Render's manual upload option
3. Configure as static site
4. Deploy and get URL