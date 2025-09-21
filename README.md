# Mind AR Video Player

A simple web-based augmented reality app that plays a video when an image target is detected using Mind AR.js.

## Files

- `index.html` - Main AR application
- `compile-target.html` - Tool to compile target images into .mind files
- `README.md` - This file

## Setup Instructions

### 1. Compile Your Target Image

1. Open `compile-target.html` in your browser
2. Select a target image (recommended: high contrast, distinct features, 500x500px+)
3. Click "Compile Target" to generate `targets.mind` file
4. Save the downloaded `targets.mind` file in the same directory as `index.html`

### 2. Serve the App

Since AR requires camera access, you need to serve the files over HTTPS or localhost:

**Option A: Python Server**
```bash
# Python 3
python -m http.server 8000

# Python 2
python -m SimpleHTTPServer 8000
```

**Option B: Node.js Server**
```bash
npx http-server -p 8000
```

**Option C: VS Code Live Server**
- Install Live Server extension
- Right-click `index.html` and select "Open with Live Server"

### 3. Access the App

1. Open your browser and go to `http://localhost:8000`
2. Allow camera permissions when prompted
3. Point your camera at the target image
4. The video should appear and play when the target is detected

## Customization

### Change Video
Edit the video source in `index.html`:
```html
<video id="ar-video" src="YOUR_VIDEO_URL_HERE" ...>
```

### Adjust Video Size/Position
Modify the `a-video` element properties:
```html
<a-video 
    src="#ar-video" 
    position="0 0 0" 
    height="1" 
    width="1.78" 
    rotation="0 0 0">
</a-video>
```

### Use Local Video
1. Place your video file in the project directory
2. Update the src attribute: `src="./your-video.mp4"`

## Tips

- Use high-contrast images with clear features for better tracking
- Keep target images well-lit and unobstructed
- Video files should be web-optimized (MP4/WebM)
- For mobile compatibility, ensure videos have `playsinline` and `muted` attributes

## Browser Support

- Chrome/Chromium (recommended)
- Firefox
- Safari (iOS 11.3+)
- Edge

## Troubleshooting

- **Camera not working**: Check browser permissions and use HTTPS/localhost
- **Target not detected**: Ensure good lighting and clear view of target image
- **Video not playing**: Check video format and autoplay policies
- **AR not loading**: Verify `targets.mind` file is in the correct location