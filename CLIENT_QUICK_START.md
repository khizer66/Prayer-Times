# Quick Start Guide for Client

## 🚀 Getting Started (5 Minutes)

### Step 1: Access Your Site
1. Open your browser
2. Go to: `https://your-site.netlify.app` (or your deployed URL)
3. Enter password: `masjid2024` (⚠️ Change this!)

### Step 2: Access Admin Panel
1. Go to: `https://your-site.netlify.app/admin.html`
2. Enter password: `masjid2024` (⚠️ Change this!)
3. You can now manage hadiths

### Step 3: Set Up on TV
1. Connect TV to internet
2. Open browser on TV
3. Go to your site URL
4. Enter password
5. Set to fullscreen (F11 or TV's fullscreen button)
6. Leave it running!

---

## ⚙️ Quick Configuration

### Change Password (IMPORTANT!)
1. Open `index.html` in text editor
2. Find: `const ADMIN_PASSWORD = 'masjid2024';`
3. Change `'masjid2024'` to your password
4. Do the same in `admin.html`
5. Save and upload to your hosting

### Adjust TV Display
Open `index.html`, find these settings (around line 214):

```javascript
tvMode: true,          // true = Large text (for TV), false = Normal
allowScrolling: false, // true = Allow scrolling, false = No scroll
compactLayout: false,  // true = Compact spacing, false = Normal
showHadith: true      // true = Show hadith, false = Hide
```

**If content doesn't fit on TV:**
- Set `compactLayout: true` OR
- Set `allowScrolling: true` OR
- Set `showHadith: false`

---

## 📝 Managing Hadiths

### Add New Hadith
1. Go to admin panel (`/admin.html`)
2. Click "Add Hadith"
3. Enter hadith text and source
4. Click "Add"
5. Click "Save Hadiths" at bottom

### Import from Google Sheets
1. Create Google Sheet with columns: Text, Source
2. Publish as CSV (File → Share → Publish to web → CSV)
3. Copy the CSV URL
4. Paste in admin panel's "Google Sheets CSV URL" field
5. Click "Save Sheet URL"
6. Click "Save Hadiths"

---

## 🎯 What You Need to Do

- [ ] Change passwords in `index.html` and `admin.html`
- [ ] Test on your TV
- [ ] Adjust TV settings if needed
- [ ] Add your hadiths via admin panel
- [ ] Update announcements (in `index.html`)
- [ ] Verify Iqamah times are correct

---

## ❓ Common Questions

**Q: How do I update prayer times?**  
A: They update automatically! No action needed.

**Q: Can I use this offline?**  
A: Yes, but you need internet for fresh prayer times.

**Q: How do I change the mosque name?**  
A: Edit `index.html`, find `mosqueName` and `mosqueArabic`.

**Q: The text is too small on TV**  
A: Make sure `tvMode: true` in `index.html`.

**Q: Content doesn't fit on screen**  
A: Set `compactLayout: true` or `allowScrolling: true`.

---

**For detailed instructions, see `CLIENT_HANDOVER.md`**

