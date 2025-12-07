# How to Test Your Prayer Times Display

## Quick Test Steps

### 1. Start Local Server
Double-click `serve.bat` or run:
```bash
python serve.py
```

### 2. Open in Browser
Go to: `http://localhost:8000/index.html`

### 3. Enter Password
- Password: `masjid2024` (default)
- This is required because password protection is enabled

### 4. See the Changes

The changes are subtle but important for TV displays. Here's what to look for:

#### **Current Settings (tvMode: true)**
- **Larger text sizes** - Clock, prayer times, and hadith text are bigger
- **Better spacing** - More readable from a distance
- **No scrolling** - Everything fits on one screen

#### **To See the Difference:**

**Option A: Compare with tvMode OFF**
1. Open `index.html` in a text editor
2. Find line 214: `tvMode: true,`
3. Change to: `tvMode: false,`
4. Save and refresh browser
5. You'll see smaller text sizes

**Option B: Test Compact Layout**
1. Find line 216: `compactLayout: false,`
2. Change to: `compactLayout: true,`
3. Save and refresh
4. You'll see reduced spacing

**Option C: Test Scrolling**
1. Find line 215: `allowScrolling: false,`
2. Change to: `allowScrolling: true,`
3. Save and refresh
4. You can now scroll if content doesn't fit

**Option D: Hide Hadith**
1. Find line 217: `showHadith: true,`
2. Change to: `showHadith: false,`
3. Save and refresh
4. Hadith section will disappear

## Visual Comparison

### With tvMode: true (Current)
- Clock: Very large (text-8xl to text-[12rem])
- Prayer times: Large (text-4xl to text-7xl)
- Hadith: Large (text-xl to text-3xl)
- Mosque icon: 70px

### With tvMode: false
- Clock: Medium (text-7xl to text-9xl)
- Prayer times: Medium (text-3xl to text-5xl)
- Hadith: Medium (text-lg to text-xl)
- Mosque icon: 60px

## Testing on TV

1. **Deploy to your hosting** (Netlify/Vercel)
2. **Open on TV browser** or connect laptop to TV
3. **Check if everything fits** on one screen
4. **If content is cut off:**
   - Set `allowScrolling: true`
   - Or set `compactLayout: true`
   - Or set `showHadith: false`

## Quick Test Script

To quickly see the difference, try this:
1. Open browser console (F12)
2. Type: `document.body.style.zoom = "0.8"` (makes everything smaller)
3. Type: `document.body.style.zoom = "1.2"` (makes everything larger)

This simulates different TV sizes!

