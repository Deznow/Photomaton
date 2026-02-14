# Vintage Photomaton

A browser-based photobooth application that recreates the nostalgic experience of classic photo strip booths from the 1960s-1980s. Built with vanilla JavaScript, HTML5, and CSS3.


---

## Overview

Vintage Photomaton captures the aesthetic and experience of traditional photo strip booths. The application provides real-time image filtering, automated photo sequences, and downloadable photo strips without requiring any external dependencies or backend infrastructure.

### Key Features

- Zero dependencies - built entirely with vanilla JavaScript, HTML5, and CSS3
- Privacy-first - all image processing occurs client-side
- Single HTML file architecture enables instant deployment
- Cross-platform compatibility with modern browsers
- Lightweight footprint (approximately 15KB)

---

## Features

### Core Functionality

- Real-time webcam preview with instant filter application
- Automated 4-photo sequence with countdown timer (3-2-1)
- Nine professional-grade vintage filters applied in real-time
- Download complete strips as high-quality JPEG files
- Responsive design optimized for desktop, tablet, and mobile
- Authentic photobooth flash effect for each capture

### Available Filters

- **Original** - Unfiltered capture
- **Sepia** - Classic warm brown tones
- **Black & White** - High-contrast monochrome
- **Vintage** - Retro film aesthetic
- **Dreamy** - Soft ethereal glow
- **Nostalgia** - Gentle nostalgic warmth
- **Polaroid** - Instant camera style
- **Sunset** - Golden hour ambiance
- **Moonlight** - Cool blue tones

---

## Installation

### Option 1: Direct Usage

```bash
git clone https://github.com/deznow/vintage-photomaton.git
cd vintage-photomaton
open photomaton.html
```

### Option 2: Local Server

```bash
# Using Python 3
python -m http.server 8000

# Using Node.js
npx http-server -p 8000

# Using PHP
php -S localhost:8000
```

Then navigate to `http://localhost:8000` in your browser.

### Option 3: GitHub Pages



---

## Usage

1. Open the application in a modern web browser
2. Grant camera permission when prompted
3. Select a filter from the available options
4. Position yourself in the video preview
5. Click "Take 4 Photos" to begin the countdown sequence
6. Download your photo strip as a JPEG file

---

## Browser Compatibility

| Browser | Minimum Version |
|---------|----------------|
| Chrome | 53+ |
| Firefox | 36+ |
| Safari | 11+ |
| Edge | 12+ |
| Opera | 40+ |

### Requirements

- Modern web browser with WebRTC support
- Webcam or camera device
- No additional software or dependencies required

---

## Technical Details

### Architecture

The application uses a three-layer architecture:

1. **User Interface Layer** - HTML5 and CSS3 with responsive grid layout
2. **Application Logic Layer** - Vanilla JavaScript ES6+ for event handling and state management
3. **Media Processing Layer** - WebRTC for camera access, Canvas API for image manipulation, CSS Filters for real-time preview

### Performance

- Image Resolution: 640x480 (configurable)
- Filter Processing: Less than 16ms per frame for 60fps preview
- Memory Usage: Approximately 50MB during typical operation
- Photo Strip Size: Approximately 500KB for 4-photo strip

---

## Customization

### Adding Custom Filters

**Step 1: Define CSS Filter**

```css
#video.filter-customname {
    filter: sepia(50%) brightness(1.2) contrast(1.1);
}
```

**Step 2: Add Filter Button**

```html
<button class="filter-btn" data-filter="customname">
    Custom Name
</button>
```

**Step 3: Implement Canvas Processing**

```javascript
case 'customname':
    for (let i = 0; i < data.length; i += 4) {
        data[i]     = Math.min(255, data[i] * 1.1);     // Red
        data[i + 1] = Math.min(255, data[i + 1] * 1.0); // Green
        data[i + 2] = Math.min(255, data[i + 2] * 0.9); // Blue
    }
    break;
```

### Configuration Options

```javascript
const PHOTO_COUNT = 4;              // Number of photos per strip
const COUNTDOWN_START = 3;          // Countdown seconds
const DELAY_BETWEEN_PHOTOS = 1500;  // Milliseconds between captures
const VIDEO_WIDTH = 640;            // Video resolution width
const VIDEO_HEIGHT = 480;           // Video resolution height
const JPEG_QUALITY = 0.9;           // Image export quality (0-1)
```

---

## Contributing

Contributions are welcome. Please follow these guidelines:

### Development Setup

```bash
git clone https://github.com/deznow/photomaton.git
cd vintage-photomaton
git checkout -b feature/your-feature-name
```

### Guidelines

- Follow existing code formatting and conventions
- Test on multiple browsers before submitting
- Update documentation for significant changes
- Use clear, descriptive commit messages
- Check existing issues before creating new ones

### Areas for Contribution

- Additional filter implementations
- Custom frame and border designs
- Internationalization
- Accessibility improvements
- Enhanced mobile experience
- Audio effects
- Social media sharing integration
- Local storage functionality
- Sticker and text overlay features

---

## License

MIT License

Copyright (c) 2025 @deznow/zine

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

---

## Support

- Report bugs via [GitHub Issues]
- Request features through the issue tracker
- Use GitHub Discussions for questions and community chat

---

## Acknowledgments

- Inspired by classic Polaroid photo booths and vintage instant photography
- Built with modern web standards and progressive enhancement principles

---

**Made by [@deznow](https://github.com/deznow)**
