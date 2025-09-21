# Deploy Mind AR App Online

## Option 1: GitHub Pages (Recommended - Free)

### Steps:
1. **Create GitHub Repository**
   ```bash
   git init
   git add .
   git commit -m "Initial Mind AR app"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/mind-ar-app.git
   git push -u origin main
   ```

2. **Enable GitHub Pages**
   - Go to your repo → Settings → Pages
   - Source: Deploy from a branch
   - Branch: main / (root)
   - Save

3. **Access your app**
   - URL: `https://YOUR_USERNAME.github.io/mind-ar-app`
   - HTTPS enabled automatically ✅

## Option 2: Netlify (Free)

### Steps:
1. **Drag & Drop Deployment**
   - Go to https://netlify.com
   - Drag your project folder to Netlify
   - Get instant HTTPS URL

2. **Or Connect GitHub**
   - New site from Git
   - Connect GitHub repo
   - Auto-deploy on commits

## Option 3: Vercel (Free)

### Steps:
1. **Install Vercel CLI**
   ```bash
   npm i -g vercel
   ```

2. **Deploy**
   ```bash
   vercel
   ```
   - Follow prompts
   - Get instant HTTPS URL

## Option 4: Surge.sh (Free)

### Steps:
1. **Install Surge**
   ```bash
   npm install -g surge
   ```

2. **Deploy**
   ```bash
   surge
   ```
   - Choose domain or use random
   - HTTPS available

## Mobile Testing Tips

### Camera Requirements:
- ✅ **HTTPS required** (all above options provide this)
- ✅ **Mobile browser support**: Chrome, Safari, Firefox
- ✅ **Permissions**: Camera access must be granted

### Testing Process:
1. Open URL on mobile browser
2. Allow camera permissions
3. Print target image or display on another device
4. Point camera at target
5. Video should appear in AR

### Troubleshooting:
- **No camera**: Check HTTPS and permissions
- **Poor tracking**: Ensure good lighting, steady hands
- **Video not playing**: Check mobile video format support
- **Slow loading**: Optimize video file size

## File Size Optimization

### Before deploying:
```bash
# Compress video (if ffmpeg installed)
ffmpeg -i vidoes/butterfly.mp4 -c:v libx264 -crf 28 -c:a aac vidoes/butterfly_compressed.mp4

# Or use online tools:
# - CloudConvert
# - HandBrake
# - Online-Convert
```

### Update video reference:
```html
<video src="./vidoes/butterfly_compressed.mp4">
```

## Quick Deploy Commands

### For GitHub Pages:
```bash
# Initialize git (if not done)
git init
git add .
git commit -m "Mind AR app ready for deployment"

# Create GitHub repo and push
# Then enable Pages in repo settings
```

### For Netlify Drop:
```
1. Zip your project folder
2. Go to https://app.netlify.com/drop
3. Drag zip file
4. Get instant URL
```

## Testing Checklist

- [ ] HTTPS URL working
- [ ] Camera permissions granted
- [ ] Target image clearly visible
- [ ] Video plays on target detection
- [ ] Works on different mobile devices
- [ ] Performance acceptable on mobile