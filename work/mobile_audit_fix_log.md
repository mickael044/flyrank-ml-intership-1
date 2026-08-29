# Mobile Audit & UI Polish Fix Log

## 1. Overview & Updated Live URL
- **Live Deployed Site:** `https://mickael044.github.io/flyrank-ml-intership-1/`
- **Device Tested:** Tested on physical mobile browser (iOS / Android viewports) and scaled mobile breakpoints down to 360px.

---

## 2. Identified Issues & Applied Fixes

| Category | Problem Identified (Before) | Fix Applied (After) | Impact |
| :--- | :--- | :--- | :--- |
| **Mobile Layout** | Code blocks and tables extended beyond screen width, causing horizontal scroll. | Applied CSS `overflow-x: auto` and max-width bounds to code containers. | Eliminates page-wide horizontal jitter on small screens. |
| **Readability** | Small body text size (13px) and low contrast gray on dark background. | Bumped body font size to 16px and increased contrast ratio to pass WCAG AA standards. | Comfortable reading experience without zooming. |
| **Touch Targets** | Navigation and footer social icons were too small and close together (<30px). | Increased padding and target hit area to a minimum of `44x44px`. | Prevents accidental misclicks on touchscreen devices. |
| **Asset Speed** | Raw images were oversized (~2MB) causing slow load times on mobile connections. | Compressed images to WebP format and defined explicit width/height tags. | Reduced overall page payload size by ~80%. |
| **Broken Links** | Relative links in navigation failed on sub-routes. | Converted repository internal links to absolute paths relative to root context. | All navigation and repository demo links resolve correctly. |

---

## 3. Accessibility & Performance Audit Summary
- **WCAG Contrast Check:** Passed with minimum 4.5:1 text contrast ratio.
- **Mobile Responsiveness:** Clean fluid scaling verified across mobile (360px–480px), tablet (768px), and desktop breakpoints.
