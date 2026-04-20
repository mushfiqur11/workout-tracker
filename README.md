# Workout Tracker App - Setup Guide

## 🎯 What You Have

Five files that work together:
1. **workout-tracker.html** - The main app
2. **workout-config.json** - Your exercise database
3. **manifest.json** - PWA configuration (for home screen install)
4. **workout-icon-192.png** - App icon (192x192)
5. **workout-icon-512.png** - App icon (512x512)
6. **workout-icon-180.png** - iOS app icon (180x180)

## 📱 Quick Start (Test Locally First)

1. Download all 6 files to the same folder
2. Double-click `workout-tracker.html` to open in your browser
3. The app will work immediately (uses embedded config as fallback)
4. The custom dumbbell icon will appear when you add to home screen

## 🚀 Deploy to GitHub Pages

### Step 1: Create GitHub Repository

1. Go to https://github.com
2. Click "New repository" (green button)
3. Name it: `workout-tracker`
4. Make it **Public**
5. Click "Create repository"

### Step 2: Upload Files

**Option A - Via GitHub Website (Easier):**
1. On your new repo page, click "uploading an existing file"
2. Drag ALL 6 files:
   - workout-tracker.html
   - workout-config.json
   - manifest.json
   - workout-icon-192.png
   - workout-icon-512.png
   - workout-icon-180.png
3. Click "Commit changes"

**Option B - Via Git Command Line:**
```bash
git clone https://github.com/YOUR_USERNAME/workout-tracker.git
cd workout-tracker
# Copy all 6 files here
git add .
git commit -m "Initial workout tracker with icons"
git push
```

### Step 3: Enable GitHub Pages

1. Go to your repo Settings
2. Click "Pages" in left sidebar
3. Under "Source", select "main" branch
4. Click "Save"
5. Wait 1-2 minutes

### Step 4: Access Your App

Your app will be live at:
```
https://YOUR_USERNAME.github.io/workout-tracker/workout-tracker.html
```

**Bookmark this URL on your phone!**

## 📲 Install as PWA (Optional)

On your phone:
1. Open the app URL in Safari (iOS) or Chrome (Android)
2. **iOS**: Tap Share → "Add to Home Screen"
3. **Android**: Tap Menu (3 dots) → "Add to Home Screen"

Now it works like a real app!

## ✏️ Editing Exercises

### To Modify the Workout Plan:

1. Go to your GitHub repo
2. Click on `workout-config.json`
3. Click the pencil icon (Edit)
4. Make your changes
5. Click "Commit changes"

**Everyone's app will auto-update next time they open it!**

### Example: Add New Exercise

```json
{
  "id": "cable-fly",
  "name": "Cable Chest Fly",
  "sets": 3,
  "reps": "12-15",
  "rest": "45s",
  "notes": "Keep slight bend in elbows",
  "videoUrl": "https://www.youtube.com/watch?v=EXAMPLE"
}
```

### Example: Remove Exercise

Just delete the entire exercise block (including the curly braces)

### Example: Change Exercise Details

Edit any field directly:
```json
"sets": 4,           // Changed from 3 to 4
"reps": "8-10",      // Changed from 10-12
"rest": "90s"        // Changed from 60s
```

## 🔧 Important Notes

### The Config URL

In `workout-tracker.html`, line 486, you'll see:
```javascript
const CONFIG_URL = './workout-config.json';
```

**After deploying to GitHub Pages, change this to:**
```javascript
const CONFIG_URL = 'https://YOUR_USERNAME.github.io/workout-tracker/workout-config.json';
```

This ensures the app always loads the latest config from GitHub.

### For Your Wife

Simply share the GitHub Pages URL with her. She'll get her own copy with separate:
- Workout history
- Weight tracking
- Hidden exercise preferences

All data is stored locally on her device.

## 📊 Features

✅ Track workouts by day  
✅ Log weights for each exercise  
✅ Mark exercises as Complete/Partial/Skip  
✅ Watch embedded YouTube videos  
✅ Hide exercises you don't want  
✅ View workout stats and streaks  
✅ Export/import workout history  
✅ Mobile-optimized dark theme  

## 🔄 Future: Multi-User with Firebase

When you're ready to add login/sync:

1. Create Firebase project
2. Enable Authentication + Firestore
3. I'll provide updated code with Firebase integration
4. Migration will be smooth (designed for it)

## 🐛 Troubleshooting

**App shows old exercises after updating config:**
- Clear browser cache (Settings → Clear Data)
- Or use Private/Incognito mode

**Videos won't play:**
- Some videos require YouTube app on mobile
- Try different browser

**Data disappeared:**
- Check Settings → Export Data (always keep backups!)
- Import your last backup

## 📝 Quick Reference

### File Structure
```
workout-tracker/
├── workout-tracker.html  (The app)
└── workout-config.json   (Exercise database)
```

### Exercise ID Format
Use lowercase with hyphens:
- ✅ `chest-press`
- ✅ `lat-pulldown`
- ❌ `ChestPress`
- ❌ `chest_press`

### Video URL Format
Always full YouTube URLs:
- ✅ `https://www.youtube.com/watch?v=xUm0BiZCWlQ`
- ❌ `xUm0BiZCWlQ`

---

## 💪 You're All Set!

1. Test locally first
2. Deploy to GitHub Pages
3. Share URL with your wife
4. Start tracking your gains!

Questions? Check the code comments or modify as needed. The app is yours to customize!
