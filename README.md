# Vastraa Public Saree Catalogue

Open `admin.html` for the full owner workspace, or `index.html` for the customer-facing public catalogue.

## Included

- Responsive public catalogue with search, category filters, sorting, product detail modal, and mobile layout.
- Owner controls drawer for enabling/disabling public visibility, selecting public products, controlling price and availability visibility, and editing catalogue business information.
- Copy public URL, WhatsApp sharing, category-link sharing, per-design sharing, and print-to-PDF download.
- Local browser persistence via `localStorage` for the demo settings.
- Private owner workspace with dashboard, product management, stock adjustments, sales entry, customers, reports, public catalogue controls, and business settings.
- English / Gujarati navigation language switch in Business settings.
- Quick English / ગુજરાતી toggle in the top bar, persisted language selection workflow, and Gujarati navigation labels.
- Owner authentication gate with Sign in, Create Business, Join with Invite Code, persisted session, and Logout. Public catalogue remains login-free.
- Business-scoped local data isolation: products, catalogue settings, share settings, sales, and customers are stored under the authenticated business ID instead of one global key; owners joining the same invite share that business scope.
- Public catalogue is strictly view-only: Owner controls and public share actions are hidden from customers, and shared links include the business scope.
- Mobile layout pass: collapsible sidebar, compact topbar, two-column phone product grid, stacked forms, responsive colour rows, mobile-safe modals, and horizontally scrollable data tables.
- Product form colour-variant rows with colour swatch, variant stock quantity, and per-colour selling price fields.
- Image upload now validates supported formats, shows a read-complete preview before save, persists the uploaded data with the business product, and reports oversized/unreadable files.
- Notifications bell with low-stock, sale, and stock-change items; CSV report export helper.
- Amazon-style responsive Products grid with thumbnail fallback, search, category filtering, sorting, PDF selection, and three-dot actions.
- Add/Edit Product photo uploads for JPG, JPEG, PNG, and WEBP with preview, remove, cover-image ordering, and `localStorage` persistence in this standalone demo.
- Individual product sharing from the Products page, with per-field visibility controls for photos, design number, name, colours, price, and stock.
- Single-product and selected-product PDF-ready previews using the browser’s “Save as PDF” print flow, including real uploaded images.
- Invite Code copy and WhatsApp actions with success feedback.

## Production integration note

This is a front-end deliverable. Authentication and business isolation are simulated in browser `localStorage`, so they prevent accidental cross-account display inside the demo but are not a security boundary. Product uploads, product edits, selected products, and sharing settings persist locally; the demo uses the browser print dialog for PDF output. For production, wire these controls to authenticated server actions, RLS/database policies, and an existing storage service, expose a public read-only API/view that returns only explicitly shared product fields, use server-generated expiring share tokens, and keep customer, sales, stock-history, owner, and business-settings tables behind server-side authorization. Never rely on the browser for access control.
