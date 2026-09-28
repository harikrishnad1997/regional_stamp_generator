# Passport Stamp Maker (NPS Regional Stamp Generator)

A web-based application designed to create high-resolution, full-color custom photo passport stamps for National Park Service (NPS) sites and personal travel journals.

---

## 🌟 Key Features

- 📸 **Photo Upload & Framing Controls**
  - Instant photo upload supporting standard image formats (`.jpg`, `.png`, `.webp`).
  - Real-time controls for **Zoom** (30% to 300%), **Horizontal Shift**, and **Vertical Shift**.
  - Optional photo credit overlay with shadowed typography.

- 📍 **EXIF Geolocation & Automatic Park Matching**
  - Built-in EXIF metadata extraction to read embedded `GPSLatitude` and `GPSLongitude`.
  - Automated distance calculation (Haversine formula) to match photos to the nearest official NPS site within a 150 km radius.

- 🏛️ **Dual-Source NPS Park Data**
  - Connects to the **Live NPS API** (`developer.nps.gov`) to fetch site names, park codes, designations, state locations, and descriptions.
  - Resilient offline fallback using a bundled dataset when network connectivity is unavailable.
  - Interactive auto-suggest search box for finding park sites quickly.

- 🎨 **Authentic Regional Styling & Color Palettes**
  - Supports all 10 official NPS regions:
    - North Atlantic
    - Mid-Atlantic
    - National Capital
    - Southeast
    - Midwest
    - Southwest
    - Rocky Mountain
    - Western
    - Pacific Northwest & Alaska
    - National
  - State-to-region lookup tool (50 US states + US territories) for automatic region selection.

- 📝 **Caption & Description Cards**
  - Toggleable description card below the main stamp banner.
  - Auto-populates site descriptions from official NPS records.
  - Includes a direct reference link to `nps.gov` search for the selected park.

- 🖨️ **300 DPI Print-Ready Export**
  - Strictly rendered at **768 × 650 pixels** (matching standard **6.5 cm × 5.5 cm** passport stamp dimensions at 300 DPI).
  - One-click PNG export with iOS / mobile touch-and-hold fallback support.

- 🌓 **Modern Responsive UI**
  - Native Light and Dark mode theme support (`prefers-color-scheme`).
  - Clean typography powered by Google Fonts (*Barlow Condensed* & *Source Sans 3*).

---

## 🚀 Recent Updates

- 🔄 **Resilient Auto-Load & Connection Error Handling**: Enhanced API auto-loading with automatic fallback to local dataset when offline or rate-limited.
- 🖼️ **Image Crop & Framing Accuracy**: Improved canvas math to keep aspect ratios crisp and prevent stretching during zoom and offset adjustments.
- 🧭 **EXIF GPS Matching Engine**: Added spatial distance threshold matching to auto-fill park metadata directly from photo geotags.
- 📱 **Enhanced Mobile Compatibility**: Responsive layout optimization with dedicated touch fallback controls.

---

## 💻 Quick Start & Usage

1. **Open the App**: Simply open `Passport Stamp Maker.html` in any web browser (no local server or build tools required).
2. **Upload a Photo**: Click **"Choose or take a photo"**. If your photo contains GPS geotags, the closest National Park will be detected automatically.
3. **Adjust Framing**: Use the **Zoom** and **Shift** sliders to frame your photo perfectly.
4. **Customize Site & Region**:
   - Type or search for a site name to auto-fill park details and descriptions.
   - Choose a US State to suggest the correct NPS region.
5. **Export**: Click **"Save as PNG"** to download your 300 DPI stamp ready for printing or digital journaling.

---

## 🛠️ Technical Stack

- **Frontend**: HTML5, CSS3 (CSS Custom Properties, Flexbox, Grid), Vanilla JavaScript (ES6+).
- **Canvas Engine**: HTML5 2D Canvas API for real-time compositing, text wrapping, and image scaling.
- **Libraries**: [exif-js](https://github.com/exif-js/exif-js) for client-side JPEG EXIF metadata extraction.
- **Data Source**: National Park Service (NPS) Developer API & fallback dataset.