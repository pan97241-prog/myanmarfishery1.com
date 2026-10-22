# Product Requirement Document (PRD) & Antigravity Agent Prompt

## Project Name: Myanmar Fishery Portal & Trade Platform
## Tech Stack: Pure HTML5, CSS3, Vanilla JavaScript (Single-file Ready)

---

### 1. Project Overview & Objectives

Build a comprehensive, modern, mobile-responsive web portal for **Myanmar Fishery Industry & Trade**. The application functions as a single-page B2B platform showcasing daily wholesale seafood market prices, export-grade marine products, aquaculture gallery showcases, and direct trade inquiry forms.

---

### 2. Design System & Image Specifications

#### Color Palette
- **Primary Ocean Navy:** `#0a192f`
- **Secondary Deep Teal:** `#0d9488`
- **Accent Gold:** `#f59e0b`
- **Background Slate:** `#f8fafc`
- **Card Background:** `#ffffff`

#### CDN Dependencies
- **Tailwind CSS CDN:** `https://cdn.tailwindcss.com`
- **FontAwesome CDN:** `https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css`

#### Explicit Image Assets (Unsplash CDN URLs)
1. **Hero Banner Background:**
   - URL: `https://images.unsplash.com/photo-1544551763-46a013bb70d5?auto=format&fit=crop&w=1600&q=80`
2. **Export Product Catalog Images:**
   - **Rohu (ငါးမြစ်ချင်း):** `https://images.unsplash.com/photo-1534483509719-3feaee7c30da?auto=format&fit=crop&w=600&q=80`
   - **Hilsa (ငါးသလောက်):** `https://images.unsplash.com/photo-1519708227418-c8fd9a32b7a2?auto=format&fit=crop&w=600&q=80`
   - **Tiger Sea Prawn (ပင်လယ်ပုစွန်):** `https://images.unsplash.com/photo-1565680018434-b513d5e5fd47?auto=format&fit=crop&w=600&q=80`
   - **Soft-Shell Crab (ပျော့ခွံဂဏန်း):** `https://images.unsplash.com/photo-1559742811-822863c46f83?auto=format&fit=crop&w=600&q=80`
   - **Grouper Fish (ကျောက်ငါး):** `https://images.unsplash.com/photo-1524704654690-b56c05c78a00?auto=format&fit=crop&w=600&q=80`
   - **Freshwater Prawn (ပုစွန်ထုတ်):** `https://images.unsplash.com/photo-1551248429-40975aa4de74?auto=format&fit=crop&w=600&q=80`
3. **Photo Gallery Images (With Lightbox Preview):**
   - **Aquaculture Farming:** `https://images.unsplash.com/photo-1500382017468-9049fed747ef?auto=format&fit=crop&w=800&q=80`
   - **Seafood Processing:** `https://images.unsplash.com/photo-1574484284002-952d92456975?auto=format&fit=crop&w=800&q=80`
   - **Cold Storage Packaging:** `https://images.unsplash.com/photo-1586528116311-ad8dd3c8310d?auto=format&fit=crop&w=800&q=80`
   - **Marine Harvesting:** `https://images.unsplash.com/photo-1534447677768-be436bb09401?auto=format&fit=crop&w=800&q=80`

---

### 3. Web Page Architecture & Features

#### Section 1: Top Navigation Bar
- Brand Name: `🐟 MYANMAR FISHERY`
- Navigation Links: Home, Market Prices, Export Products, Gallery, B2B Inquiry.
- Mobile Hamburger Toggle Menu (JavaScript Driven).

#### Section 2: Hero Section
- High-resolution ocean fishery background banner with gradient overlay.
- Heading: "Myanmar Fishery Portal & Trade Platform"
- Subtitle: "Connecting Local Aquaculture & Marine Fisheries to Global Markets."
- Buttons: `[ View Daily Prices ]` and `[ Send Trade Inquiry ]`.

#### Section 3: Daily Wholesale Market Price Tracker
- Live Search & Filter Bar (searches by product name or grade).
- Dynamic Table Columns:
  1. Product Name (Burmese & English)
  2. Category (Freshwater / Marine / Farmed)
  3. Size / Spec
  4. Wholesale Price (MMK / Viss)
  5. Export Grade Status

#### Section 4: Export Product Showcase & Detail Modal
- Product grid cards with image thumbnail, badge tags (Frozen/Live/IQF), description, and price tier.
- Clickable **"View Details"** button on each card triggering a JavaScript Modal Popup with comprehensive product specifications.

#### Section 5: Photo Gallery & Lightbox Viewer
- 4 to 6 image cards showcasing farming, harvesting, and cold storage facilities.
- **JavaScript Lightbox Feature:** Clicking any gallery image opens a modal displaying the full-sized image with a close button (`×`).

#### Section 6: B2B Trade Inquiry Form
- Input fields: Full Name, Company Name, Email, Country, Product Interested, Estimated Quantity.
- Submit Button with JavaScript form validation and a popup toast confirmation alert.

---

### 4. Antigravity AI Agent Prompt (Copy & Paste directly into Antigravity)

```text
Build a complete, standalone `index.html` web application for "Myanmar Fishery Portal & Trade Platform" using standard HTML5, Tailwind CSS via CDN, and Vanilla JavaScript inside embedded `<script>` tags.

Requirements:
1. Include Tailwind CSS CDN (`https://cdn.tailwindcss.com`) and FontAwesome Icon CDN in the `<head>`.
2. Apply an oceanic navy theme (#0a192f) with deep teal (#0d9488) and gold accents (#f59e0b).
3. Include explicit Unsplash CDN URLs for all media elements:
   - Hero Section background image (Fishery/Ocean).
   - 6 Export Product Cards with images (Rohu, Hilsa, Tiger Prawn, Soft-shell Crab, Grouper, Giant Freshwater Prawn).
   - 4 Gallery images depicting aquaculture ponds, processing plants, cold storage, and harvesting.
4. Implement interactive JavaScript logic:
   - Mobile navigation toggle.
   - Live Search filter for the Daily Wholesale Market Price Table.
   - Product Details Modal Popup when clicking "View Details" on product cards.
   - Lightbox Image Preview Modal: Clicking any photo gallery item opens a full-screen image preview overlay.
   - B2B Inquiry Form submission alert.
5. Deliver all code inside a single self-contained `index.html` file.
```