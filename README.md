# የግእዝ ዘመን - Eritrean Orthodox Geez Calendar PWA

A Progressive Web App (PWA) for the Eritrean Orthodox Tewahedo Church Calendar.

## ✅ Status: READY FOR TESTING

### 🚀 Local Server Running
**URL:** http://localhost:8000

The PWA is currently running and ready for testing!

## 📱 Features

- **Offline First**: Works completely offline after first visit
- **Installable**: Can be installed on any device (desktop, mobile, tablet)
- **Fast**: Service worker caching for instant loading
- **Bilingual**: Geez (የግእዝ) and English
- **Church Logo**: Uses authentic church logo as app icon
- **Standalone**: Opens as a native app without browser UI

## 📂 Project Structure

```
CHURCH-CALENDAR/
├── index.html              # Main HTML with PWA integration
├── manifest.json           # PWA manifest
├── service-worker.js       # Service worker for offline support
├── geez_calendar.js        # Calendar logic (53KB)
├── geez_calendar.css       # Styling
├── icon-192.png           # App icon 192x192 (church logo)
├── icon-512.png           # App icon 512x512 (church logo)
├── TEST-RESULTS.md        # Detailed testing instructions
├── PWA-SETUP.md           # Setup and deployment guide
└── README.md              # This file
```

## 🧪 Testing the PWA

### Quick Test Steps:

1. **Open in Browser**
   - Navigate to: http://localhost:8000
   - You should see the calendar with beautiful gradient background

2. **Install the App**
   - Look for "Install App" button at the top
   - Or click install icon in browser address bar
   - Follow installation prompts

3. **Test Offline**
   - Install the app first
   - Open the installed app
   - Turn off WiFi/enable airplane mode
   - Reopen the app - it should work perfectly!

For detailed testing instructions, see [TEST-RESULTS.md](TEST-RESULTS.md)

## 🛠️ Technical Details

### PWA Configuration
- **Cache Strategy**: Cache-first with network fallback
- **Cache Name**: geez-calendar-v1
- **Display Mode**: Standalone
- **Theme Color**: #336699
- **Orientation**: Portrait-primary

### Cached Resources
All resources are cached for offline use:
- HTML, CSS, JavaScript files
- Manifest and icons
- Service worker automatically updates cache

### Browser Support
- ✅ Chrome (Desktop & Android)
- ✅ Edge (Desktop)
- ✅ Firefox (Desktop)
- ✅ Samsung Internet
- ⚠️ Safari (iOS) - Use "Add to Home Screen"

## 📦 Deployment

For production deployment, see [PWA-SETUP.md](PWA-SETUP.md)

Deployment options:
- GitHub Pages (free)
- Netlify (free)
- Any web server with HTTPS

## 🎨 Icons

Currently using the church logo from:
`churches-project/backend/public/uploads/church-logo-1-1765532862670.jpg`

The logo features:
- የቤተ.ክ.ዮሴፍ ቤርገን (Debre Iyesus Bergen)
- Christ with disciples
- Established 2011
- Church seal design

## 🔧 Development

### Start Local Server
```bash
cd CHURCH-CALENDAR
npx http-server -p 8000 -c-1
```

### Update Cache Version
When making changes, update the cache version in `service-worker.js`:
```javascript
const CACHE_NAME = 'geez-calendar-v2'; // Increment version
```

## 📖 Documentation

- [TEST-RESULTS.md](TEST-RESULTS.md) - Complete testing guide
- [PWA-SETUP.md](PWA-SETUP.md) - Setup and deployment instructions

## 🌐 Calendar Features

- Geez/Ethiopian calendar dates
- Eritrean Orthodox holidays
- Fasting periods and dates
- Month/year navigation
- Bilingual display (Geez & English)

## 📱 Installation on Different Devices

### Android (Chrome)
1. Open http://localhost:8000
2. Tap the install banner or menu > "Add to Home Screen"
3. App icon appears on home screen with church logo

### iOS (Safari)
1. Open http://localhost:8000
2. Tap Share button (square with arrow)
3. Tap "Add to Home Screen"
4. Enter name and tap "Add"

### Desktop (Chrome/Edge)
1. Open http://localhost:8000
2. Click install icon in address bar
3. Or click "Install App" button
4. App opens in standalone window

## 🎯 Next Steps

1. ✅ Icons created using church logo
2. ✅ Server running locally
3. ✅ All PWA files ready
4. 🔲 Test installation and offline functionality
5. 🔲 Deploy to production server

## 💡 Tips

- First visit requires internet to cache resources
- After first visit, works completely offline
- Install prompt shows automatically on supported browsers
- Can be uninstalled like any other app
- Updates automatically when cache version changes

## 📞 Support

For issues or questions, check:
- Browser console (F12) for errors
- Application tab in DevTools for service worker status
- Network tab to verify caching
- Cache Storage to see cached files

## 🙏 Credits

**የግእዝ ዘመን አቆጣጠር**
Eritrean Orthodox Tewahedo Church Calendar

© 2025 Debre Iyesus Bergen Norge

---

**🎉 The PWA is ready! Open http://localhost:8000 to start testing.**
