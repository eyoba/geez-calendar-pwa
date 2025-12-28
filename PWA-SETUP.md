# PWA Setup Instructions for Geez Calendar

## Current Status

The Progressive Web App (PWA) implementation for the Eritrean Orthodox Geez Calendar is complete! Here's what has been implemented:

### ✅ Completed Components

1. **manifest.json** - PWA configuration file with app metadata
2. **service-worker.js** - Handles offline caching and app installation
3. **index.html** - Updated with PWA meta tags and service worker registration
4. **Install prompt** - User-friendly installation prompt in the UI

## Next Steps to Complete Setup

### Step 1: Generate PWA Icons

1. Open [generate-icons.html](generate-icons.html) in your web browser
2. Click "Generate Both Icons" button
3. Save the downloaded files:
   - `icon-192.png` - Save in the CHURCH-CALENDAR folder
   - `icon-512.png` - Save in the CHURCH-CALENDAR folder

### Step 2: Deploy to a Web Server

PWAs require HTTPS to work (except on localhost). You have several options:

#### Option A: Deploy to GitHub Pages (Free)
```bash
# Initialize git repo if not already done
git init
git add .
git commit -m "Add Geez Calendar PWA"

# Create GitHub repo and push
git remote add origin https://github.com/yourusername/geez-calendar.git
git push -u origin main

# Enable GitHub Pages in repository settings
```

#### Option B: Deploy to Netlify (Free)
1. Go to https://netlify.com
2. Drag and drop the CHURCH-CALENDAR folder
3. Your app will be live at a HTTPS URL

#### Option C: Test Locally
```bash
# Navigate to CHURCH-CALENDAR folder
cd c:\churchwebsite\CHURCH-CALENDAR

# Using Python (if installed)
python -m http.server 8000

# Using Node.js http-server (if installed)
npx http-server -p 8000

# Then visit: http://localhost:8000
```

### Step 3: Test PWA Installation

1. **On Chrome/Edge (Desktop):**
   - Open the website
   - Look for install icon in address bar
   - Click "Install" button in the app
   - App will be installed and can be launched from desktop

2. **On Android Chrome:**
   - Open the website
   - Tap the install prompt or menu → "Add to Home Screen"
   - App icon will appear on home screen

3. **On iOS Safari:**
   - Open the website
   - Tap Share button
   - Tap "Add to Home Screen"

### Step 4: Test Offline Functionality

1. Install the app using steps above
2. Open the installed app
3. Turn off your internet connection or enable airplane mode
4. The app should still work with full calendar functionality
5. All Geez calendar features should be available offline

## PWA Features Implemented

### 🚀 Core Features
- ✅ Works offline after first visit
- ✅ Installable on all devices (desktop, mobile, tablet)
- ✅ Fast loading with service worker caching
- ✅ Standalone app experience (no browser UI)
- ✅ App icons and splash screens
- ✅ Responsive design for all screen sizes

### 📱 User Experience
- ✅ Install prompt with "Install App" button
- ✅ Dismissable install prompt
- ✅ Beautiful gradient design
- ✅ Geez and English bilingual support
- ✅ Portrait-optimized layout

### 🔧 Technical Details
- Cache strategy: Cache-first with network fallback
- Offline fallback: Returns index.html
- Cache version: geez-calendar-v1
- Service worker lifecycle: Install → Activate → Fetch

## File Structure

```
CHURCH-CALENDAR/
├── index.html              # Main HTML file with PWA integration
├── manifest.json           # PWA manifest configuration
├── service-worker.js       # Service worker for offline support
├── geez_calendar.js        # Calendar logic
├── geez_calendar.css       # Calendar styles
├── generate-icons.html     # Icon generator tool
├── icon-192.png           # App icon 192x192 (generate this)
├── icon-512.png           # App icon 512x512 (generate this)
└── PWA-SETUP.md           # This file
```

## Troubleshooting

### Install Button Not Showing
- Make sure you're using HTTPS (or localhost)
- Check browser console for service worker errors
- Try in incognito/private mode
- Clear browser cache and reload

### Offline Mode Not Working
- Ensure service worker registered successfully (check console)
- Visit the page at least once while online
- Check that all files are cached correctly
- Look for console errors

### Icons Not Showing
- Make sure icon files are in the correct location
- Icons must be named exactly: icon-192.png and icon-512.png
- File paths in manifest.json must match actual file locations
- Clear cache and reinstall the app

## Browser Support

- ✅ Chrome (Android & Desktop)
- ✅ Edge (Desktop)
- ✅ Samsung Internet
- ✅ Firefox (Desktop)
- ⚠️ Safari (iOS) - Limited PWA support, use "Add to Home Screen"

## Updating the PWA

When you make changes to the app:

1. Update the cache version in service-worker.js:
   ```javascript
   const CACHE_NAME = 'geez-calendar-v2'; // Increment version
   ```

2. The service worker will automatically update on user's next visit
3. Old caches will be cleaned up automatically

## Additional Enhancements (Optional)

Consider adding these features in the future:

- Push notifications for holy days and fasting periods
- Background sync for sharing calendar events
- Dark mode theme
- Calendar event sharing functionality
- Multiple language support (Tigrinya, Amharic, Arabic)
- Integration with device calendar
- Reminder notifications

## Support

For issues or questions:
- Check browser console for errors
- Test in different browsers
- Verify HTTPS connection
- Ensure all files are properly cached

---

**የግእዝ ዘመን አቆጣጠር - Eritrean Orthodox Calendar**

*Works offline, installable on all devices!*

© 2025 Debre Iyesus
