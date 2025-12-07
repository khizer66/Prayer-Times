# Masjid Shkup Prayer Times Display

A beautiful, modern digital display for showing daily Islamic prayer times at Masjid Shkup in Skopje, Macedonia.

## Features

- ✨ **Dynamic Visual Themes** - Different color schemes and animations for each prayer time
- 🌍 **Real-time Updates** - Automatic prayer time fetching from Aladhan API
- 📱 **Responsive Design** - Works on all screen sizes
- 💾 **Offline Support** - Cached prayer times work without internet
- 🕌 **Islamic Aesthetics** - Beautiful Arabic typography and Islamic patterns
- ⏰ **Iqamah Times** - Automatically calculated with configurable offsets
- 📅 **Hijri Calendar** - Displays Islamic calendar date
- 📜 **Rotating Hadiths** - Inspirational quotes from authentic sources
- 🎨 **Seasonal Colors** - Theme adapts to spring, summer, autumn, and winter
- ⚙️ **Admin Panel** - Easy hadith management via `admin.html`

## Deployment

This project is deployed on Netlify at: https://prayertimes5.netlify.app/

### Local Development

1. Clone the repository
2. Open `index.html` in a browser or use a local server:
   ```bash
   # Using Python
   python -m http.server 8000
   
   # Using Node.js
   npx serve .
   ```
3. Open `http://localhost:8000` in your browser

### Production Deployment

1. Push to your Git repository
2. Connect to Netlify
3. Deploy automatically on push

## Configuration

Edit the `CONFIG` object in `index.html` to customize:

```javascript
const CONFIG = {
  mosqueName: "MASJID SHKUP",
  mosqueArabic: "مسجد شكوب",
  city: "Skopje",
  country: "Macedonia",
  timezone: "Europe/Skopje",
  method: 3, // Calculation method (1-15)
  iqamahOffset: { 
    Fajr: 20, 
    Dhuhr: 15, 
    Asr: 15, 
    Maghrib: 5, 
    Isha: 15 
  },
  announcements: [
    "Jummah Prayer at 1:30 PM",
    "Islamic Classes - Sunday after Dhuhr",
    "Support Your Masjid - JazakAllah Khair"
  ]
};
```

## Prayer Calculation Methods

The `method` parameter uses the following calculation methods:
- 1 = University of Islamic Sciences, Karachi
- 2 = Islamic Society of North America
- 3 = Muslim World League
- 4 = Umm al-Qura, Makkah
- 5 = Egyptian General Authority of Survey
- And more...

See [Aladhan API documentation](https://aladhan.com/prayer-times-api) for full list.

## Managing Hadiths

### Admin Panel (Recommended)

1. Open `admin.html` in your browser (e.g., `https://prayertimes5.netlify.app/admin.html`)
2. Add, edit, or remove hadiths using the visual editor
3. Click "Save All Changes" to store hadiths in browser localStorage
4. The main display will automatically use the updated hadiths

### Google Sheets Integration

1. Create a Google Sheet with two columns: `text` | `source`
2. Add your hadiths (one per row)
3. Go to **File → Share → Publish to web**
4. Select **Comma-separated values (.csv)** and publish
5. Copy the CSV URL
6. Open `admin.html` and paste the URL in the "Google Sheets URL" field
7. Click "Save" - the display will fetch hadiths from your sheet automatically

### Direct Editing

You can also edit hadiths directly in `index.html` by modifying the `defaultHadiths` array in the CONFIG section.

## Keyboard Shortcuts (Development Mode)

When `productionMode` is `false`:
- `1-5` - Preview prayer themes
- `S` - Cycle through seasons
- `R` - Reset preview
- `Escape` - Exit preview mode

## Browser Support

- Chrome/Edge (latest)
- Firefox (latest)
- Safari (latest)
- Mobile browsers

## Performance

- Service Worker for offline caching
- localStorage for prayer times cache (24 hours)
- Optimized animations (60fps target)
- Lazy loading of resources

## Security

- Content Security Policy headers
- XSS protection
- Secure headers via Netlify configuration

## Maintenance

### Regular Tasks

- **Weekly**: Verify prayer times accuracy
- **Monthly**: Review and update announcements
- **Quarterly**: Update dependencies
- **Yearly**: Review and update hadiths

### Updating Prayer Times

Prayer times are automatically fetched daily from the Aladhan API. The app caches times for 24 hours to ensure offline functionality.

## Troubleshooting

### Prayer times not loading
- Check internet connection
- Verify API endpoint is accessible
- Check browser console for errors
- App will use cached data if available

### Service Worker not working
- Clear browser cache
- Unregister old service worker
- Hard refresh (Ctrl+Shift+R / Cmd+Shift+R)

### Hadiths not updating
- Make sure you've saved changes in `admin.html`
- If using Google Sheets, verify the CSV URL is correct and the sheet is published
- Clear browser cache and localStorage if needed
- Check that the same browser is used for both admin panel and display

## Files Structure

```
Prayer-Times/
├── index.html      # Main prayer times display
├── admin.html      # Hadith management panel
├── sw.js           # Service worker for offline support
├── manifest.json   # PWA manifest
├── netlify.toml    # Netlify deployment configuration
└── README.md       # This file
```

## License

This project is created for Masjid Shkup. All rights reserved.

## Credits

- Prayer times API: [Aladhan API](https://aladhan.com)
- Icons: Custom SVG icons
- Fonts: Google Fonts (Amiri, Outfit)

## Support

For issues or questions, please contact the mosque administration.


