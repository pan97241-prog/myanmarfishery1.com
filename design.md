# Design Specification for Myanmar Fishery Portal & Trade Platform

---

## 1. Project Vision
A clean, mobile‑responsive, single‑page web portal that showcases daily wholesale market prices, export‑grade seafood products, a photo gallery, and a B2B inquiry form. The UI should feel modern, ocean‑themed, and be built entirely with **HTML5**, **Tailwind CSS CDN**, **FontAwesome CDN**, and **vanilla JavaScript**.

---

## 2. Design System
### 2.1 Color Palette
| Role | Hex |
|------|-----|
| **Primary Ocean Navy** (background, headers) | `#0a192f` |
| **Secondary Deep Teal** (accent, hover) | `#0d9488` |
| **Accent Gold** (call‑to‑action, badges) | `#f59e0b` |
| **Background Slate** (page background) | `#f8fafc` |
| **Card Background** (white surfaces) | `#ffffff` |

### 2.2 Typography
- **Font Family**: System UI (fallback to `sans-serif`).
- **Headings**: `font-bold` with Tailwind size scale (`text-4xl` for hero, `text-2xl` for sections).
- **Body**: `text-base` with `text-gray-800` for readability.

### 2.3 Icons
- FontAwesome 6.4.0 CDN for social, navigation, and badge icons.

### 2.4 Images (Unsplash CDN URLs)
| Asset | Description | URL |
|-------|-------------|-----|
| **Hero Banner** | Oceanic fishery background | `https://images.unsplash.com/photo-1544551763-46a013bb70d5?auto=format&fit=crop&w=1600&q=80` |
| **Export Products** | Rohu, Hilsa, Tiger Sea Prawn, Soft‑Shell Crab, Grouper, Freshwater Prawn | See spec lines 31‑36 for URLs |
| **Gallery** | Aquaculture farming, processing, cold storage, marine harvesting | See spec lines 38‑41 for URLs |

---

## 3. UI Components
| Component | Description | Tailwind/JS Details |
|-----------|-------------|---------------------|
| **Top Navigation Bar** | Fixed, dark navy background, brand logo (🐟), links: Home, Market Prices, Export Products, Gallery, B2B Inquiry. Hamburger toggles a vertical menu on mobile. | `flex`, `items-center`, `justify-between`; JS toggles `hidden`/`block` on `<ul>`.
| **Hero Section** | Full‑width background image with gradient overlay, large heading, subtitle, two CTA buttons. | `bg-cover`, `bg-center`, `bg-gradient-to-r`; Buttons use `bg-gold` hover effects.
| **Price Tracker Table** | Responsive table with live search box; columns: Product (Burmese/English), Category, Size/Spec, Wholesale Price, Export Grade. | Tailwind `overflow-x-auto`; JS filters rows based on search input (case‑insensitive).
| **Export Product Card Grid** | 2‑column (mobile) / 3‑column (tablet) / 4‑column (desktop) cards; each shows thumbnail, badge tags, short desc, price tier, "View Details" button. | `grid` layout with `gap-6`; Modal popup populated via data attributes.
| **Product Detail Modal** | Centered overlay with larger image, specifications list, and close icon. | Hidden by default (`hidden`), shown by adding `flex` via JS.
| **Photo Gallery** | Card layout of 4‑6 images; clicking opens a lightbox preview. | Lightbox uses a full‑screen fixed div with fade‑in transition.
| **B2B Inquiry Form** | Fields: Full Name, Company, Email, Country, Product Interested, Estimated Quantity. Submit triggers client‑side validation and toast confirmation. | `grid` form layout; validation with simple JS checks; toast uses Tailwind animation utilities.

---

## 4. Page Wireframes (Markdown Sketches)
### 4.1 Desktop Layout
```
+-----------------------------------------------------------+
| NAVBAR (fixed)                                            |
+-----------------------------------------------------------+
| HERO (full‑width image, heading, two CTA buttons)         |
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
- Navigation collapses to hamburger.
- Hero height reduces, CTAs stacked.
- Table becomes a vertical list with key‑value rows.
- Card grids collapse to 1‑column.
- Gallery images stack vertically.

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