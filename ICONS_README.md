# Icon Files Required

This project references several icon files that should be created for optimal display:

## Required Files

1. **favicon.svg** ✅ (Created)
   - Already created in the root directory
   - Used as the browser favicon

2. **icon-192.png** (192x192 pixels)
   - Used for PWA icon on mobile devices
   - Should be a square version of the mosque icon
   - Can be generated from favicon.svg

3. **icon-512.png** (512x512 pixels)
   - Used for PWA icon and app store listings
   - High-resolution version
   - Can be generated from favicon.svg

4. **apple-touch-icon.png** (180x180 pixels)
   - Used for iOS home screen icon
   - Should be square with no transparency
   - Can be generated from favicon.svg

5. **og-image.png** (1200x630 pixels)
   - Used for social media sharing (Open Graph)
   - Should include mosque name and design
   - Recommended format: PNG or JPG

## Generating Icons

You can use online tools or image editing software to generate these from the favicon.svg:

- **Online Tools:**
  - https://realfavicongenerator.net/
  - https://www.pwabuilder.com/imageGenerator
  - https://favicon.io/

- **Command Line (if you have ImageMagick):**
  ```bash
  # Convert SVG to PNG at different sizes
  convert favicon.svg -resize 192x192 icon-192.png
  convert favicon.svg -resize 512x512 icon-512.png
  convert favicon.svg -resize 180x180 apple-touch-icon.png
  ```

## Temporary Solution

The app will work without these files, but:
- Browser will show default favicon
- PWA installation may not show custom icon
- Social media shares won't have preview image

## Note

The manifest.json and HTML already reference these files, so once you create them, they'll automatically be used.


