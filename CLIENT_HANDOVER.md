# Prayer Times Display - Client Handover Guide

## 📋 Overview

This document provides everything you need to know about the Prayer Times Display system, including setup instructions, features, and configuration options.

---

## 🎯 What Has Been Delivered

### ✅ Core Features
1. **Prayer Times Display** - Beautiful, real-time prayer times for Masjid Shkup, Skopje
2. **Admin Panel** - Easy-to-use interface for managing hadiths
3. **TV-Optimized Display** - Perfect for large screen displays
4. **Password Protection** - Secure access to both display and admin panel
5. **Offline Support** - Works even without internet (cached prayer times)
6. **Auto-Refresh** - Automatically updates at 3 AM daily

### ✅ Recent Enhancements
1. **TV Mode** - Larger text sizes optimized for TV viewing
2. **12-Hour Time Format** - All times displayed in 12-hour format with AM/PM
3. **Flexible Layout Options** - Adjustable spacing and scrolling for different TV sizes
4. **Security** - Password protection for both display and admin panel
5. **Google Sheets Integration** - Import hadiths from Google Sheets CSV

---

## 🚀 Deployment Instructions

### Option 1: Deploy to Netlify (Recommended)

1. **Create a Netlify account** (if you don't have one)
   - Go to https://www.netlify.com
   - Sign up for free

2. **Deploy the site**
   - Drag and drop your project folder to Netlify dashboard
   - OR connect your GitHub repository
   - Netlify will automatically deploy

3. **Get your URL**
   - Netlify will give you a URL like: `https://your-site.netlify.app`
   - You can customize this in Netlify settings

### Option 2: Deploy to Vercel

1. **Create a Vercel account**
   - Go to https://vercel.com
   - Sign up for free

2. **Deploy**
   - Import your project
   - Vercel will auto-detect and deploy

### Option 3: Use Existing Hosting

If you already have hosting (like the current Vercel deployment):
- Simply upload the updated files
- The site will automatically update

---

## 🔐 Access Information

### Main Display
- **URL**: Your deployed URL (e.g., `https://your-site.netlify.app`)
- **Password**: `masjid2024` (⚠️ **CHANGE THIS** - see Configuration section)

### Admin Panel
- **URL**: Your deployed URL + `/admin.html` (e.g., `https://your-site.netlify.app/admin.html`)
- **Password**: `masjid2024` (⚠️ **CHANGE THIS** - see Configuration section)

---

## ⚙️ Configuration Guide

### 1. Change Passwords (IMPORTANT!)

**For Main Display (`index.html`):**
1. Open `index.html` in a text editor
2. Find line 170: `const ADMIN_PASSWORD = 'masjid2024';`
3. Change `'masjid2024'` to your desired password
4. Save and redeploy

**For Admin Panel (`admin.html`):**
1. Open `admin.html` in a text editor
2. Find line 122: `const ADMIN_PASSWORD = 'masjid2024';`
3. Change `'masjid2024'` to your desired password
4. Save and redeploy

**⚠️ Security Note**: Use a strong password! The password is visible in the code, so this is basic protection only.

### 2. TV Display Settings

Open `index.html` and find the TV Display Settings section (around line 214):

```javascript
tvMode: true,              // true = Large text for TV, false = Normal text
allowScrolling: false,      // true = Allow scrolling, false = No scrolling
compactLayout: false,       // true = Compact spacing, false = Normal spacing
showHadith: true           // true = Show hadith section, false = Hide it
```

**Recommended Settings for TV:**
- `tvMode: true` - Makes text larger and more readable from a distance
- `allowScrolling: false` - Keeps everything on one screen (no scrolling)
- `compactLayout: false` - Normal spacing (set to `true` if content doesn't fit)
- `showHadith: true` - Shows hadith section (set to `false` if it doesn't fit)

### 3. Prayer Time Offsets (Iqamah Times)

In `index.html`, find the `iqamahOffset` setting (around line 211):

```javascript
iqamahOffset: { 
    Fajr: 20,    // 20 minutes after Adhan
    Dhuhr: 15,   // 15 minutes after Adhan
    Asr: 15,     // 15 minutes after Adhan
    Maghrib: 5,  // 5 minutes after Adhan
    Isha: 15     // 15 minutes after Adhan
}
```

Adjust these numbers to match your masjid's Iqamah schedule.

### 4. Announcements

Edit the announcements banner (around line 212):

```javascript
announcements: [
    "Jummah Prayer at 1:30 PM",
    "Islamic Classes - Sunday after Dhuhr",
    "Support Your Masjid - JazakAllah Khair"
]
```

Add or modify announcements as needed.

---

## 📱 How to Use

### For Viewers (General Public)

1. **Access the Display**
   - Open the website URL on any device
   - Enter the password when prompted
   - The display will show current prayer times

2. **What They See**
   - Current time and date
   - All 5 prayer times (Fajr, Dhuhr, Asr, Maghrib, Isha)
   - Iqamah times for each prayer
   - Active prayer highlighted
   - Countdown to next prayer
   - Rotating hadiths
   - Announcements banner

### For Administrators

1. **Access Admin Panel**
   - Go to: `your-site.com/admin.html`
   - Enter the admin password

2. **Manage Hadiths**
   - **Add Hadith**: Click "Add Hadith", enter text and source, click "Add"
   - **Edit Hadith**: Click the edit icon, modify text/source, click "Save"
   - **Delete Hadith**: Click the delete icon
   - **Import from Google Sheets**: 
     - Publish your Google Sheet as CSV
     - Copy the CSV URL
     - Paste in "Google Sheets CSV URL" field
     - Click "Save Sheet URL"
   - **Export to CSV**: Click "Export CSV" to download all hadiths

3. **Save Changes**
   - Always click "Save Hadiths" after making changes
   - Changes appear on the main display immediately

---

## 📺 TV Setup Instructions

### For Client: Setting Up on TV

1. **Connect TV to Internet**
   - Use WiFi or Ethernet cable
   - Ensure stable internet connection

2. **Open Browser on TV**
   - Most smart TVs have a built-in browser
   - Or use a device connected to TV (laptop, Raspberry Pi, etc.)

3. **Navigate to Your Site**
   - Enter the website URL
   - Enter password
   - Bookmark the page for easy access

4. **Set to Fullscreen**
   - Press F11 (on computer) or use TV's fullscreen mode
   - The display is optimized for fullscreen viewing

5. **Keep It Running**
   - Leave the browser open
   - The page auto-refreshes at 3 AM daily
   - Prayer times update automatically

### Recommended TV Settings

- **Resolution**: 1920x1080 (Full HD) or higher
- **Display Mode**: Fullscreen
- **Browser**: Chrome, Firefox, or Edge (latest version)
- **Auto-Start**: Set browser to open the site on startup (if possible)

---

## 🎨 Customization Options

### Colors and Themes
The display automatically changes colors based on:
- **Time of Day**: Different colors for each prayer time
- **Season**: Spring, Summer, Autumn, Winter themes
- **Active Prayer**: Currently active prayer is highlighted

### Mosque Information
Edit in `index.html` (around line 201):
```javascript
mosqueName: "MASJID SHKUP",
mosqueArabic: "مسجد شكوب",
```

### Timezone and Location
Already configured for:
- **City**: Skopje
- **Country**: Macedonia
- **Timezone**: Europe/Skopje
- **Calculation Method**: 3 (Muslim World League)

---

## 🔧 Troubleshooting

### Display Not Loading
- Check internet connection
- Clear browser cache (Ctrl+Shift+Delete)
- Try a different browser

### Password Not Working
- Make sure you're using the correct password
- Check if password was changed in the code
- Clear browser's sessionStorage (F12 → Application → Session Storage → Clear)

### Prayer Times Wrong
- Verify timezone is correct in `index.html`
- Check if calculation method (line 208) is appropriate
- Times are fetched from Aladhan API - verify API is working

### Content Doesn't Fit on TV
- Set `compactLayout: true` in `index.html`
- Or set `allowScrolling: true` to enable scrolling
- Or set `showHadith: false` to hide hadith section

### Hadiths Not Updating
- Make sure you clicked "Save Hadiths" in admin panel
- Clear browser cache
- Check if Google Sheets URL is correct (if using)

---

## 📞 Support & Maintenance

### Regular Maintenance
- **Weekly**: Check that prayer times are displaying correctly
- **Monthly**: Review and update announcements
- **As Needed**: Add/update hadiths via admin panel

### Updates
- The system automatically fetches prayer times daily
- No manual updates needed for prayer times
- Only update hadiths and announcements as needed

---

## 📝 Files Included

- `index.html` - Main prayer times display
- `admin.html` - Admin panel for managing hadiths
- `sw.js` - Service worker for offline support
- `manifest.json` - PWA configuration
- `netlify.toml` - Deployment configuration (if using Netlify)
- `favicon.svg` - Website icon
- `README.md` - Technical documentation
- `SECURITY.md` - Security information

---

## ⚠️ Important Notes

1. **Change Default Passwords** - The default password `masjid2024` should be changed immediately
2. **Backup Your Data** - Export hadiths regularly using the CSV export feature
3. **Test on TV** - Always test the display on the actual TV before going live
4. **Internet Required** - While offline mode works, fresh prayer times require internet
5. **Browser Compatibility** - Works best on modern browsers (Chrome, Firefox, Edge)

---

## 🎯 Next Steps for Client

1. ✅ **Deploy the site** (if not already deployed)
2. ✅ **Change passwords** in both `index.html` and `admin.html`
3. ✅ **Test on TV** - Set up on actual TV and verify everything fits
4. ✅ **Adjust TV settings** if needed (`tvMode`, `compactLayout`, etc.)
5. ✅ **Add hadiths** via admin panel
6. ✅ **Update announcements** to match your masjid's schedule
7. ✅ **Adjust Iqamah offsets** if your masjid uses different timings
8. ✅ **Bookmark the site** on TV browser for easy access

---

## 📧 Questions to Ask Client

Before finalizing, please confirm:

1. **TV Setup**
   - What size/resolution is the TV?
   - Does everything fit on one screen?
   - Is the text readable from viewing distance?

2. **Passwords**
   - What password do they want for the main display?
   - What password do they want for the admin panel?

3. **Prayer Times**
   - Are the Iqamah offsets correct? (Fajr: 20min, Dhuhr: 15min, etc.)
   - Is the calculation method (3 - Muslim World League) correct?

4. **Content**
   - Do they want to add their own hadiths?
   - What announcements should be displayed?
   - Is the mosque name and Arabic text correct?

5. **Preferences**
   - Do they prefer TV Mode ON (large text) or OFF (normal text)?
   - Should scrolling be enabled if content doesn't fit?

---

## ✨ Features Summary

### What Makes This Special

1. **Beautiful Design** - Modern, elegant interface with Islamic patterns
2. **Real-Time Updates** - Automatically shows current prayer and countdown
3. **TV Optimized** - Perfect for large screen displays
4. **Easy Management** - Simple admin panel for non-technical users
5. **Offline Support** - Works even without internet (cached data)
6. **Responsive** - Works on phones, tablets, computers, and TVs
7. **Secure** - Password protection for access control
8. **Auto-Refresh** - No manual maintenance needed

---

**Need Help?** Refer to `README.md` for technical details or contact your developer.

**Last Updated**: December 2024

