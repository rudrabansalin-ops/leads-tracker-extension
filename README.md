# Leads Tracker Extension

A lightweight browser extension built with vanilla JavaScript that helps sales executives and researchers efficiently save and manage leads while conducting web research. Save URLs directly from the browser tab or paste custom lead links into a persistent list that syncs across your browser sessions.

## Overview

**Leads Tracker** is a simple yet powerful tool designed for sales teams who spend time researching prospects and competitors. Instead of juggling multiple browser tabs or scrambling to collect URLs, this extension lets you:

- **Save current tab URLs** with a single click
- **Manually add lead URLs** via text input
- **Persist data automatically** using browser localStorage
- **View and access leads** from any browser session
- **Clear all leads** with a double-click (safety feature)

The extension stores all your leads in your browser's local storage, ensuring your data stays private and accessible whenever you need it.

---

## Features

### Core Functionality

✅ **Save Current Tab** — Click the "SAVE TAB" button to instantly capture the URL of the active browser tab

✅ **Manual Entry** — Type or paste URLs into the input field and click "SAVE INPUT" to add custom leads

✅ **Persistent Storage** — All leads are saved to localStorage and automatically restored when you reopen the extension

✅ **Clickable Links** — View all saved leads as clickable links that open in a new tab

✅ **Bulk Delete** — Double-click the "DELETE ALL" button to clear all stored leads at once (double-click prevents accidental deletion)

✅ **Lightweight** — Built with vanilla JavaScript, HTML, and CSS—no dependencies, minimal resource usage

---

## Browser Compatibility

### ✅ Fully Tested & Supported

| Browser | Status | Tab Permission | Notes |
|---------|--------|-----------------|-------|
| **Google Chrome** | ✅ Fully Supported | Yes | Works perfectly with Manifest V3 |
| **Microsoft Edge** | ✅ Fully Supported | Yes | Chromium-based, identical behavior to Chrome |

### ⚠️ Not Tested (Compatibility Likely Varies)

| Browser | Status | Notes |
|---------|--------|-------|
| **Firefox** | ⚠️ Untested | May require manifest adjustments; Firefox uses different permission models and APIs |
| **Safari** | ⚠️ Untested | Safari extensions use a different architecture; likely requires significant rework |
| **Opera** | ⚠️ Untested | Chromium-based but has its own extension ecosystem |
| **Brave** | ⚠️ Untested | Chromium-based but may have additional restrictions |

### Why Other Browsers Aren't Tested

The extension uses Chrome's Tab API (`chrome.tabs.query`) which:
- ✅ Works natively in Chrome and Edge
- ⚠️ Requires different permission declarations in Firefox (via `permissions` instead of `tabs`)
- ⚠️ Works differently in Safari (uses `safari.application.windows`)
- ⚠️ May have restrictions or additional steps in Brave and Opera

**If you want to support other browsers**, you would need to:
1. Check the target browser's extension documentation for tab access APIs
2. Update the `manifest.json` permissions accordingly
3. Add conditional logic in `index.js` to detect the browser and use the appropriate API
4. Test thoroughly on the target browser

---

## Installation

### On Windows (Chrome or Edge)

#### Method 1: Developer Mode Installation (Recommended)

1. **Clone or Download the Repository**
   ```
   git clone https://github.com/YOUR_USERNAME/leads-tracker-extension.git
   ```
   Or download as ZIP and extract it

2. **Open the Extensions Management Page**
   - **Chrome**: Go to `chrome://extensions/`
   - **Edge**: Go to `edge://extensions/`

3. **Enable Developer Mode**
   - Look for the toggle in the top-right corner labeled "Developer mode"
   - Click it to enable developer mode

4. **Load the Extension**
   - Click the **"Load unpacked"** button
   - Navigate to the `leads-tracker-extension` folder (the one with `manifest.json` at the root)
   - Select this folder and click OK
   - The extension will appear in your extensions list with a unique ID

   ℹ️ **Note**: The extension folder structure is now organized with:
   - `manifest.json` at the root (required by Chrome/Edge)
   - `src/` folder containing HTML, CSS, and JavaScript files
   - `assets/` folder containing the extension icon
   - This structure works perfectly — no additional setup needed

5. **Pin the Extension (Optional)**
   - Click the puzzle icon in the top-right corner of your browser
   - Find "Leads Tracker" in the list
   - Click the pin icon to keep it visible in your toolbar

#### Method 2: Using a Permanent Folder Location (Alternative)

If you prefer to keep the extension in a specific location:

1. Clone/download the repository to your preferred location (e.g., `C:\Users\YourUsername\Extensions\leads-tracker-extension`)
2. Follow steps 2-4 above, but select that permanent folder location
3. The extension remains loaded as long as the folder exists in that location

---

## Usage

### Saving Leads

#### Option 1: Save the Current Tab
1. While browsing a prospect or lead's website, click the **Leads Tracker** extension icon in your toolbar
2. Click the **"SAVE TAB"** button
3. The current tab's URL is instantly saved and appears in the leads list

#### Option 2: Manually Add a Lead
1. Click the **Leads Tracker** extension icon
2. Type or paste a URL in the text input field
3. Click the **"SAVE INPUT"** button
4. The URL is added to your leads list

### Viewing and Accessing Leads

- All saved leads appear as **clickable links** in the extension popup
- Click any link to open it in a new browser tab
- Links stay in the list even after you close and reopen the extension (data persists in localStorage)

### Clearing All Leads

- **Double-click** the **"DELETE ALL"** button to clear all saved leads
- The double-click requirement prevents accidental deletion
- Once cleared, leads cannot be recovered from the extension (but may be in your browser history)

---

## Data Storage

### How It Works

- **Storage Method**: Browser `localStorage`
- **Storage Location**: Unique to this extension (private to the Leads Tracker extension)
- **Persistence**: Data survives:
  - ✅ Browser restarts
  - ✅ Browser updates
  - ✅ Tab closures and reopenings
- **Data Loss Scenarios**:
  - ❌ Browser data is cleared (cache/cookies/storage)
  - ❌ Extension is uninstalled
  - ❌ Manual deletion via "DELETE ALL" button
  - ❌ Browser is reset

### Privacy

- ✅ All data is stored **locally on your machine** in your browser profile
- ✅ Data is **never sent to external servers** or cloud services
- ✅ No tracking, analytics, or third-party integrations
- ✅ Completely private to your browser profile

---

## Updating the Extension

### Update from GitHub/Repository

1. **Download the latest version** from the repository
2. Go to `chrome://extensions/` or `edge://extensions/`
3. Find "Leads Tracker" in your extensions list
4. Click the **refresh/update icon** (circular arrow) next to the extension
5. The extension reloads with the new version automatically

### Manual Update (If Automatic Doesn't Work)

1. **Download the new files** and replace the old files in your extension folder
2. Go to `chrome://extensions/` or `edge://extensions/`
3. Click the **reload icon** for Leads Tracker
4. Your data persists after the update

---

## Deployment to Another Machine

### Step-by-Step Guide

#### On the New Machine:

1. **Copy the extension folder**
   - Transfer the entire `leads-tracker-extension` folder to the new machine
   - You can use: USB drive, cloud storage, email, or any file transfer method
   - Example path: `C:\Users\YourUsername\Downloads\leads-tracker-extension`

2. **Open the Extensions Page**
   - In Chrome: Go to `chrome://extensions/`
   - In Edge: Go to `edge://extensions/`

3. **Enable Developer Mode**
   - Toggle "Developer mode" in the top-right corner (if not already enabled)

4. **Load the Extension**
   - Click **"Load unpacked"**
   - Select the folder you copied
   - The extension is now installed and ready to use

5. **Pin to Toolbar (Optional)**
   - Click the puzzle icon
   - Find Leads Tracker and pin it

### Cross-Machine Sync (Important Notes)

⚠️ **Leads do NOT sync across machines automatically**

Each browser profile on each machine maintains its own separate localStorage:
- Machine A has its own leads list
- Machine B has a separate, empty leads list
- To move leads between machines, you would need to:
  - Manually export leads (via developer console)
  - Transfer the data file
  - Manually import leads (requires code modification)

**Current workaround**: Screenshot your leads list or maintain a separate document if you need to reference the same leads across multiple machines.

---

## Project Structure

```
leads-tracker-extension/
├── README.md              # This file (displayed on GitHub home page)
├── manifest.json          # Extension configuration (MUST stay at root)
├── .gitignore             # Prevents unnecessary files from git
├── src/
│   ├── index.html         # UI structure (buttons, input, list)
│   ├── index.css          # Styling (colors, layout, typography)
│   └── index.js           # Logic (save, display, delete functionality)
└── assets/
    └── icon.png           # Extension icon (displayed in toolbar)
```

### File Descriptions

**manifest.json** (at root)
- Declares the extension metadata (name, version, permissions)
- Defines the popup window location: `"default_popup": "src/index.html"`
- Defines icon location: `"default_icon": "assets/icon.png"`
- Requests the `tabs` permission to access current tab URLs
- Uses Manifest V3 (modern Chrome/Edge standard)
- ⚠️ **Must stay at root** — Chrome/Edge require this file at the extension root to load the extension

**src/index.html**
- Simple form with three buttons: "SAVE INPUT", "SAVE TAB", "DELETE ALL"
- Text input field for manual URL entry
- Unordered list to display saved leads

**src/index.css**
- Minimal, clean styling
- Green accent color (#5f9341) for a professional look
- Responsive design for popup window
- Styled input, buttons, and links

**src/index.js**
- Loads leads from localStorage on extension open
- Saves new leads (from manual entry or tab capture) to localStorage
- Renders the leads list dynamically
- Handles the delete-all functionality (double-click trigger)
- Uses Chrome's `tabs` API to capture current tab URL

**assets/icon.png**
- Visual identifier for the extension in the browser toolbar
- Appears in the extensions list and toolbar

**README.md** (at root)
- Documentation displayed on GitHub repository home page
- Contains installation, usage, and troubleshooting information

**.gitignore** (at root)
- Prevents OS files (.DS_Store, Thumbs.db), IDE files (.vscode, .idea), and temporary files from being committed to git
- Keeps repository clean and focused on actual project files

---

## Troubleshooting

### Extension Won't Load

**Problem**: "Load unpacked" button is grayed out or missing

**Solution**:
1. Make sure Developer mode is enabled (toggle in top-right)
2. Restart the browser if you just enabled Developer mode
3. Ensure the folder contains all required files (manifest.json is mandatory)

### "SAVE TAB" Button Doesn't Work

**Problem**: Clicking "SAVE TAB" does nothing or shows an error

**Solution**:
1. Ensure the `tabs` permission is declared in `manifest.json`
2. Reload the extension (click the refresh icon on `chrome://extensions/`)
3. If still broken, open the browser console (F12) and check for error messages
4. Verify you're using Chrome, Edge, or another Chromium-based browser

### Leads Aren't Saving

**Problem**: Entered URLs don't appear in the list after saving

**Solution**:
1. Check if browser localStorage is enabled (usually is by default)
2. Verify localStorage is not full (rarely happens unless saving large data)
3. Open browser Developer Tools (F12 → Application → Local Storage) and check if data exists
4. Try reloading the extension (F5 in the popup or refresh from `chrome://extensions/`)

### Data Disappeared After Browser Update

**Problem**: Leads list is empty after updating Chrome/Edge

**Solution**:
1. This is rare but can happen if the browser clears extension storage
2. Check your browser history to find previously saved URLs
3. Re-add leads manually or use a backup if you maintained one
4. **Recommendation**: Periodically export your leads to a backup (via copy/paste)

### Extension Works on Chrome But Not Edge (or Vice Versa)

**Problem**: Extension loads on one browser but not the other

**Solution**:
1. Verify you're using a recent version of both browsers (Chromium-based)
2. Try unloading and reloading the extension
3. Check that `manifest.json` is valid JSON (no syntax errors)
4. Both browsers should use identical installation steps

---

## Development Notes

### Built With

- **HTML5** — Simple semantic structure
- **CSS3** — Flexbox layout, no frameworks
- **Vanilla JavaScript** — No dependencies, no build step
- **Chrome/Edge Tab API** — To capture active tab URLs
- **localStorage API** — To persist data client-side

### Future Enhancements (Ideas)

- 🔍 Search/filter leads by keyword
- 🏷️ Add categories or tags to leads
- 📋 Export leads to CSV or JSON
- ⭐ Star/favorite important leads
- 🔗 Show lead metadata (title, domain)
- 📱 Sync leads across devices (would require backend)
- 🎨 Customizable color themes
- ⌨️ Keyboard shortcuts for quick save

### Why Vanilla JavaScript?

This project intentionally uses no frameworks or build tools to:
- ✅ Keep the extension lightweight and fast
- ✅ Eliminate dependency management overhead
- ✅ Make the code easy to understand and modify
- ✅ Ensure compatibility without version conflicts
- ✅ Reduce security surface area

---

## License

This project is provided as-is for personal and team use. Feel free to modify and extend it for your needs.

---

## Support & Feedback

If you encounter issues or have suggestions:

1. **Check the Troubleshooting section** above
2. **Review the browser console** (F12) for error messages
3. **Verify all files are in the extension folder**
4. **Try disabling and re-enabling** the extension
5. **Restart the browser** (surprisingly effective!)

---

## Version History

**v1.0** (Current)
- Initial release
- Save tab URLs
- Manual URL entry
- Persistent localStorage
- Delete all leads
- Chrome and Edge support

---

**Happy lead tracking! 🚀**
