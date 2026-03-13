# Magic Cakes Bakery Menu Display

## Overview
This project creates a responsive HTML5 menu display for Magic Cakes Bakery, featuring dynamic price updates via JSON, hidden admin form, and optimized layout for various devices including TVs with fixed browser resolutions like Amazon Silk on Fire TV.

## Development Process
1. **Initial Setup**: Started with a static HTML menu file (`magic_cakes_menu.html`).
2. **JSON Integration**: Added JSON-driven form for price updates with sync functionality to update HTML prices dynamically.
3. **Form Hiding**: Implemented toggle to hide/show the admin form for clean display.
4. **Data Separation**: Moved menu data to external `menu-data.json` file.
5. **Git Integration**: Initialized Git repo and pushed to GitHub.
6. **File Rename**: Renamed to `index.html` for standard web hosting.
7. **Responsiveness**: Added media queries for mobile, tablet, laptop, and large screens.
8. **TV Optimization**: Adjusted for Amazon Silk browser's 960x540px resolution on Fire TV, preventing stacking and scrolling.

## Specs Involved
- **Browser Compatibility**: Works on modern browsers; optimized for Amazon Silk (Fire TV) at 960x540px viewport.
- **Resolution Handling**:
  - Mobile: ≤768px (stacked columns)
  - Tablet: 769-1024px (row layout, compact fonts)
  - Laptop: 1025-1919px (standard fonts)
  - Large Screens: ≥1000px (ultra-compact for TVs/monitors)
- **Display Requirements**: Fits 42" monitor at 1080p without scrolling; scales for various aspect ratios.
- **Performance**: Lightweight HTML/CSS/JS, no external dependencies except Google Fonts.

## Replication Guide
1. **Clone the Repo**:
   ```
   git clone https://github.com/miabakeryiq/MCB_screen1.git
   cd MCB_screen1
   ```
2. **File Structure**:
   - `index.html`: Main menu page
   - `menu-data.json`: Menu data with categories and prices
3. **Local Testing**:
   - Open `index.html` in a browser.
   - For TV testing, use a device/browser simulating 960x540px (e.g., browser dev tools).
4. **Customization**:
   - Edit `menu-data.json` to update menu items/prices.
   - Modify CSS media queries in `index.html` for different breakpoints.
   - Toggle form visibility by changing `display: none` to `block` in `.form-container`.
5. **Deployment**:
   - Host on any web server; ensure CORS allows JSON fetching if needed.

## Evolution for Dynamic Screen Resolution Adjustment
To make the layout adapt dynamically to any screen resolution:

1. **JavaScript-Based Scaling**:
   - Use `window.innerWidth` and `window.innerHeight` to detect resolution.
   - Apply CSS transforms or font scaling based on detected size.
   - Example: Add to JS:
     ```javascript
     function adjustForResolution() {
       const width = window.innerWidth;
       const height = window.innerHeight;
       const scale = Math.min(width / 1920, height / 1080); // Scale to 1080p
       document.body.style.transform = `scale(${scale})`;
       document.body.style.transformOrigin = 'top left';
     }
     window.addEventListener('resize', adjustForResolution);
     adjustForResolution();
     ```

2. **CSS Custom Properties (Variables)**:
   - Define font sizes and margins as CSS variables.
   - Update variables dynamically with JS based on resolution.

3. **Media Query Enhancements**:
   - Add more granular breakpoints (e.g., 800px, 1200px).
   - Use `orientation: landscape` for TVs.
   - Detect device pixel ratio for high-DPI screens.

4. **Future Features**:
   - Auto-detect device type (TV, mobile) using user agent or screen size.
   - Implement progressive enhancement for older browsers.
   - Add accessibility features (ARIA labels, keyboard navigation).

## Technologies Used
- **HTML5**: Structure and semantics.
- **CSS3**: Responsive design with Flexbox/Grid, media queries, viewport units.
- **JavaScript (ES6)**: JSON fetching, DOM manipulation, form handling.
- **JSON**: Data storage for menu items.
- **Git/GitHub**: Version control and hosting.

## Contributing
- Fork the repo, make changes, submit PR.
- Test on multiple devices/resolutions.

## License
[Add license if needed]</content>
<parameter name="filePath">/Users/jackreid/Desktop/MCB/README.md