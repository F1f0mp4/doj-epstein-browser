# Epstein Disclosure Library Navigator

A lightweight, single-file web application for browsing and viewing the U.S. Department of Justice Epstein Disclosure datasets (1-12) with automatic pagination support and keyboard navigation.

## Features

- **Multi-Dataset Support**: Browse all 12 official DOJ Epstein disclosure datasets
- **Automatic Pagination**: Detects and fetches all pages from each dataset automatically
- **Direct PDF Viewing**: Load PDFs directly in an embedded iframe
- **Keyboard Navigation**: Use arrow keys (↑↓←→) to navigate files
- **Age Verification Handling**: Cookies persist within the browser session
- **File List Search**: Sidebar shows all files for quick navigation
- **Debug Panel**: Optional status viewer (toggle with ⚙️ button)

## How to Use

### 1. **Open the File**
   - Open `epstein-navigator.html` in your web browser
   - Or double-click the file to open it in your default browser

### 2. **Select a Dataset**
   - From the sidebar on the left, select a dataset from the dropdown (Data Set 1 - 12)
   - The app will automatically fetch all pages and display the file list
   - A loading indicator shows progress: "Loading page 1...", "Loading page 2...", etc.

### 3. **Browse Files**
   - Click any file in the sidebar to view it
   - Use the **← Prev** and **Next →** buttons to navigate
   - Or use keyboard shortcuts:
     - **Arrow Right / Down**: Next file
     - **Arrow Left / Up**: Previous file

### 4. **Handling Age Verification (Important!)**

   **Recommended: Use a Private/Incognito Window**

   The DOJ requires age verification (18+) before accessing these documents. Follow these steps:

   1. **First Time Setup**:
      - Open the app in a **Private/Incognito window** (Ctrl+Shift+P on Windows/Linux, Cmd+Shift+N on Mac)
      - Select a dataset and click on a file
      - You will see the age verification page in the viewer
      - Click on green button **"Open original"** then on offitial site press **"Yes, I am 18 years or older"** then head back to `epstein-navigator.html`
      - You sould be good to go

   2. **After Verification**:
      - Your age verification is now cached in the browser session
      - Navigate to other files freely—they will load without showing the age gate again
      - The verification persists for your entire browsing session

   3. **If PDFs Don't Load Immediately**:
      - Click the **"Open Original ↗"** button (top-right, green button)
      - This opens the file in a new tab where you can confirm age again
      - Return to the main app and the PDFs should load properly
      - The session cache should now be refreshed

### 5. **Debug Panel** (Optional)
   - Click the **⚙️ Debug** button (top-right of viewer) to toggle debug information
   - Shows fetch status, content-type, and loading details
   - Useful for troubleshooting

## Features Explained

### Pagination
- The app automatically detects numeric pagination (`?page=1`, `?page=2`, etc.)
- Fetches all pages of a dataset on initial load
- Shows progress: "Loading page 1 (page=1)...", "Loading page 2 (page=1)...", etc.

### Keyboard Shortcuts
| Key | Action |
|-----|--------|
| **Arrow Right** or **Arrow Down** | Next file |
| **Arrow Left** or **Arrow Up** | Previous file |

### Direct PDF Loading
- PDFs load directly in the embedded iframe (no external windows)
- Your browser's native PDF viewer is used
- Cookies and session data persist, so age verification only happens once per session

## Troubleshooting

### "Are you 18 years or older?" appears repeatedly
- **Solution**: Close the private window and open a fresh private/incognito window
- Restart the app to reset the session cookie

### PDFs show blank or gray area
- **Solution**: Click **"Open Original ↗"** to verify age in a new tab, then return
- The session cache should refresh after manual verification

### No files appear in the list
- **Solution**: Check your internet connection
- Try selecting a different dataset
- Click the ⚙️ Debug button to see error details

### Keyboard navigation doesn't work
- **Solution**: Click inside the viewer area first to focus it
- Then use arrow keys to navigate

## Technical Details

- **No Backend Required**: Fully client-side application
- **Single File**: Everything in one HTML file
- **Uses Public APIs**: Fetches from justice.gov via CORS proxy for pagination
- **Direct PDF Load**: PDFs load directly via your browser's native handler
- **Session-Based**: Age verification stored in browser session (per-session only)

## Browser Compatibility

- **Modern browsers recommended**: Chrome, Firefox, Safari, Edge
- **Private/Incognito mode strongly recommended** for fresh cookies
- JavaScript must be enabled

## Notes

- This tool fetches publicly available DOJ disclosures
- Age verification is required by the DOJ (18+ only)
- All data is loaded directly from official DOJ sources
- No data is cached or stored locally beyond the browser session
- Keyboard navigation requires focus on the main viewer area

## License & Disclaimer

This tool is provided as-is for educational and research purposes. All documents are official U.S. Department of Justice materials. Respect all applicable laws and regulations when accessing and using these documents.
