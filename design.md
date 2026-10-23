# Design Specification for Myanmar Fishery Portal & Trade Platform

---

## 1. Project Vision
A mobile‑responsive, single‑page trade portal connecting buyers with Myanmar seafood, indicative wholesale references, export products, and a B2B inquiry demo. The UI uses a coastal market-board aesthetic and is built with **HTML5**, **Tailwind CSS CDN**, **FontAwesome CDN**, and **vanilla JavaScript**.

---

## 2. Design System
### 2.1 Color Palette
| Role | Hex |
|------|-----|
| **Primary Deep Estuary** (headers, inquiry panel) | `#102d35` |
| **Secondary Sea Teal** (bands, accents) | `#17585a` |
| **Accent Sand** (call‑to‑action, badges) | `#e8b765` |
| **Background Sea Foam** (page background) | `#f7f6f0` |
| **Card Background** (white surfaces) | `#ffffff` |
| **Coral** (small highlights) | `#d97859` |

### 2.2 Typography
- **Font Family**: System UI (fallback to `sans-serif`).
- **Headings**: Editorial serif display type paired with system UI body text.
- **Body**: System UI with muted slate-green supporting text for readability.

### 2.3 Icons
- FontAwesome 6.4.0 CDN for social, navigation, and badge icons.

### 2.4 Images (Unsplash CDN URLs)
| Asset | Description | URL |
|-------|-------------|-----|
| **Hero Banner** | Oceanic fishery background | `https://images.unsplash.com/photo-1544551763-46a013bb70d5?auto=format&fit=crop&w=1600&q=80` |
| **Export Products** | Rohu, Hilsa, Tiger Sea Prawn, Soft‑Shell Crab, Grouper, Freshwater Prawn | See `index.html`; the broken crab image asset was replaced with a working Unsplash image. |
| **Gallery** | Aquaculture farming, processing, cold storage, marine harvesting | See spec lines 38‑41 for URLs |

---

## 3. UI Components
| Component | Description | Tailwind/JS Details |
|-----------|-------------|---------------------|
| **Top Navigation Bar** | Sticky deep-estuary header, fish-mark wordmark, market/product/gallery links, and trade CTA. Mobile menu expands vertically. | Responsive flex layout; JavaScript toggles the menu and updates `aria-expanded`.
| **Hero Section** | Coastal photo with dark ocean overlay, editorial headline, market/product CTAs, and a trade-introduction panel. | Responsive two-column layout collapses on mobile.
| **Price Tracker Table** | Searchable wholesale reference table with Burmese species names, category, typical size, MMK/viss price, and grade availability. References are marked indicative, not live quotes. | Horizontally scrollable table; JavaScript filters rows case-insensitively.
| **Export Product Card Grid** | Six seafood cards in a 1-column mobile / 2-column tablet / 3-column desktop grid, with product image, catch-format tag, indicative price, and details action. | JavaScript reads product data attributes to populate the details dialog.
| **Product Detail Modal** | Centered product dialog with image, format, description, indicative price, and inquiry link. Escape, backdrop, and close button dismiss it; keyboard focus stays within the dialog. | Hidden by default and opened from product actions.
| **Photo Gallery** | Four labeled supply-chain images in an asymmetric grid; clicking opens a keyboard-operable lightbox preview. | Responsive CSS grid with labeled buttons.
| **B2B Inquiry Form** | Required buyer/company/product fields with native validation and an honest demo-only confirmation; submissions are not transmitted or stored. | Accessible status toast reports demo behavior.

---

## 4. Page Wireframes (Markdown Sketches)
### 4.1 Desktop Layout
```
+-----------------------------------------------------------+
| NAVBAR (sticky, trade CTA)                                |
+-----------------------------------------------------------+
| HERO (coastal image, trade intro, product/prices CTAs)    |
+-----------------------------------------------------------+
| SECTION: Daily Market Prices (search + table)            |
+-----------------------------------------------------------+
| SECTION: Export Products (grid of cards)                 |
+-----------------------------------------------------------+
| SECTION: Photo Gallery (grid of images)                  |
+-----------------------------------------------------------+
| SECTION: B2B Inquiry Form                                 |
+-----------------------------------------------------------+
| FOOTER (©2026 Myanmar Fishery)                           |
+-----------------------------------------------------------+
```
### 4.2 Mobile Layout (breakpoint <640px)
- Navigation collapses to an accessible menu toggle.
- Hero panel stacks and CTAs wrap or stack.
- Market table remains horizontally scrollable for clear column labels.
- Product cards collapse to 1‑column.
- Gallery adapts to a compact two-column mosaic.

---

## 5. Interaction Flow
1. **Page Load** – Tailwind CDN and FontAwesome load; hero background image fetched.
2. **Nav Toggle** – User clicks hamburger → JS toggles `hidden` class on the mobile menu.
3. **Live Search** – `input` event filters table rows; case‑insensitive contains match.
4. **View Details** – Click on a product card → JS reads `data‑` attributes, populates modal content, shows modal.
5. **Lightbox** – Click gallery image → overlay displays larger image; click `×` or outside to close.
6. **Form Submit** – Validate required fields; on success, show toast `Thank you! We'll contact you soon.`.

---

## 6. Accessibility & SEO
- Semantic HTML5 elements (`<header>`, `<nav>`, `<main>`, `<section>`, `<footer>`).
- Alt text for all images (provided in `aria-label` or `alt` attribute).
- Keyboard‑navigable modals (focus trap, `Esc` to close).
- Sufficient color contrast (tested against WCAG AA).
- Meta tags: `title`, `description`, `viewport`.

---

## 7. Technical Considerations
- **Single‑File Delivery** – All CSS via Tailwind CDN, JS inline within `<script>` tags; no external build steps.
- **Performance** – Lazy‑load gallery images using `loading="lazy"`; keep HTML size minimal.
- **Future Extensibility** – Data for products and prices can later be swapped with a JSON fetch; current implementation uses static HTML for rapid prototyping.
- **Browser Compatibility** – Tested on modern Chromium, Firefox, Edge; graceful fallback for older browsers (no grid layout fallback to Flexbox).

---

## 8. Acceptance Checklist
- [ ] Entire UI fits within a single `index.html` file.
- [ ] All color values, fonts, and images match the spec.
- [ ] Responsive breakpoints (`sm`, `md`, `lg`) render correctly.
- [ ] Navigation works on desktop and mobile.
- [ ] Live search filters the price table instantly.
- [ ] Product detail modal displays correct data for each card.
- [ ] Lightbox works for all gallery images.
- [ ] Form validation prevents empty required fields and shows toast on success.
- [ ] No console errors; page passes HTML validator.

---

*Generated from the original PRD (`myanmar_fishery_portal_specification.md`).*