# HTML to MP4 Video Converter

Convert HTML pages with images into professional MP4 videos with background music and smooth transitions.

## Features

✅ Convert HTML pages to MP4 videos  
✅ Support for embedded images and external image URLs  
✅ Add background music (mp3, wav, flac, aac)  
✅ Customizable slide duration and transitions  
✅ Automatic resolution and quality settings  
✅ Easy-to-use CLI and Node.js API  

## Requirements

- **Node.js** 14+ 
- **FFmpeg** (for video encoding)
- **Puppeteer** (headless browser for HTML rendering)

## Installation

### 1. Clone the repository
```bash
git clone https://github.com/chandrashekar2026english/html-to-video-converter.git
cd html-to-video-converter
```

### 2. Install Node.js dependencies
```bash
npm install
```

### 3. Install FFmpeg

**Windows (via Chocolatey):**
```bash
choco install ffmpeg
```

**macOS (via Homebrew):**
```bash
brew install ffmpeg
```

**Linux (Ubuntu/Debian):**
```bash
sudo apt-get install ffmpeg
```

## Quick Start

### Basic Usage

```bash
node converter.js --input pages.json --music background.mp3 --output video.mp4
```

### Configuration File (pages.json)

```json
{
  "pages": [
    {
      "html": "page1.html",
      "duration": 5
    },
    {
      "html": "page2.html",
      "duration": 5
    },
    {
      "html": "page3.html",
      "duration": 5
    }
  ],
  "resolution": "1920x1080",
  "fps": 30,
  "quality": "high"
}
```

### Command Line Options

```bash
Options:
  --input <file>      Path to JSON configuration file (required)
  --music <file>      Path to background music file (mp3, wav, flac, aac)
  --output <file>     Output MP4 file path (default: output.mp4)
  --duration <sec>    Duration per page in seconds (overrides config)
  --resolution <res>  Resolution (default: 1920x1080)
  --fps <num>         Frames per second (default: 30)
  --quality <level>   Video quality: low/medium/high (default: high)
  --transition <type> Transition effect: fade/zoom/slide (default: fade)
```

## Examples

### Example 1: Simple video with music

```bash
node converter.js \
  --input config.json \
  --music soundtrack.mp3 \
  --output my-video.mp4 \
  --duration 8
```

### Example 2: High quality with custom resolution

```bash
node converter.js \
  --input config.json \
  --music background.wav \
  --output video.mp4 \
  --resolution 2560x1440 \
  --quality high \
  --fps 60
```

### Example 3: With slide transition

```bash
node converter.js \
  --input config.json \
  --music music.mp3 \
  --output presentation.mp4 \
  --transition slide
```

## Using as a Node.js Module

```javascript
const HTMLToMP4 = require('./lib/converter');

const options = {
  inputFile: 'pages.json',
  musicFile: 'background.mp3',
  outputFile: 'video.mp4',
  duration: 5,
  resolution: '1920x1080',
  fps: 30,
  quality: 'high',
  transition: 'fade'
};

HTMLToMP4.convert(options)
  .then(() => console.log('Video created successfully!'))
  .catch(err => console.error('Error:', err));
```

## Supported Audio Formats

- MP3
- WAV
- FLAC
- AAC
- OGG

## Supported Image Formats

- PNG
- JPG/JPEG
- GIF
- WebP
- SVG

## Transition Effects

- **fade**: Smooth fade between slides
- **zoom**: Zoom in/out effect
- **slide**: Slide from one side to another
- **none**: No transition effect

## Project Structure

```
html-to-video-converter/
├── converter.js              # CLI entry point
├── lib/
│   ├── converter.js         # Main conversion logic
│   ├── html-renderer.js     # HTML to image rendering
│   ├── image-processor.js   # Image processing utilities
│   ├── video-composer.js    # Video and audio composition
│   └── transitions.js       # Transition effects
├── examples/
│   ├── sample-config.json
│   ├── page1.html
│   ├── page2.html
│   └── background.mp3
├── package.json
└── README.md
```

## Troubleshooting

### FFmpeg not found
Make sure FFmpeg is installed and in your PATH:
```bash
ffmpeg -version
```

### Puppeteer download issues
Clear cache and reinstall:
```bash
rm -rf node_modules
npm cache clean --force
npm install
```

### Out of memory
For large projects, increase Node.js memory:
```bash
node --max-old-space-size=4096 converter.js --input config.json
```

### Audio sync issues
Try adjusting the duration per page:
```bash
node converter.js --input config.json --duration 6
```

## Performance Tips

1. **Optimize images** before converting (resize to target resolution)
2. **Use H.264 codec** for best compatibility
3. **Reduce fps** for faster processing (24 instead of 30)
4. **Use medium quality** for quick previews

## Contributing

Contributions welcome! Please submit pull requests or issues.

## License

MIT License - see LICENSE file for details

## Support

For issues and questions, please open an issue on GitHub.

---

**Created by:** Chandrashekar  
**Last Updated:** 2026-09-07
