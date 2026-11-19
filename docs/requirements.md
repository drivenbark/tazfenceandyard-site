# Tazmanian Fence & Yard — requirements

## Public website (this repo) — shipped in site-refresh
- REQ-TFY-001: Given a visitor on a phone, when the page loads, then a tap-to-call button for 907-252-1374 is visible without scrolling and in a persistent bottom bar.
- REQ-TFY-002: Given the existing 13 gallery photos, when the site is refreshed, then all 13 remain (originals untouched in `assets/Gallery-*.jpg`) and display via optimized copies in `assets/web/` with a tap-to-enlarge viewer.
- REQ-TFY-003: Given a visitor submits the estimate form, when the request is valid, then it POSTs to the existing Google Apps Script endpoint with the unchanged payload keys (name, phone, email, area, details, source). Fence type is folded into `details`.
- REQ-TFY-004: Given a search engine, when it crawls, then it finds title, description, canonical, Open Graph, LocalBusiness JSON-LD, robots.txt and sitemap.xml.
- REQ-TFY-005: Site text is editable through `content.site.json` (hero, services, areas, contact hours, gallery list, branding).

## Owner app (NOT in this repo — separate private project; Tier A: auth, payments, PII)
From owner discovery call (Nov 2026):
- REQ-APP-001: Given an address, when the owner opens the map, then he sees satellite imagery WITH the house and KPB parcel/property lines overlaid, and segment lengths in feet. Target accuracy ~1 ft.
- REQ-APP-002: Given a measured fence run (with gates), when he saves it, then the app computes footage, line/corner/gate posts, rails/pickets/panels and hardware list for the chosen fence type.
- REQ-APP-003: Given a drawn layout, when he sends a quote, then the customer receives a picture of the drawing plus a line-item quote.
- REQ-APP-004: Given a card/ACH payment option on a quote, when the customer pays, then a 3% processing fee is shown on the quote and added to the bill; payments handled by a hosted processor (Square), never hand-rolled.
- REQ-APP-005: Given a crew member, when they sign in with phone number + 6-digit SMS code, then they see ONLY their own weekly timesheet and can log hours; the owner sees all hours; crew cannot see owner data. Supports multiple pay rates (travel / yard / job).
- REQ-APP-006: Given logged income/expenses/hours, when the owner opens the tax view, then he sees a running quarterly estimated-tax summary.
- Open questions: domain (~$15/yr), SMS provider, KPB parcel data source/licensing, whether to license to other fence companies later (multi-tenant from day one?).
- REQ-TFY-006: Given the estimate form, when phone is missing or under 10 digits, then submit is blocked with a message (leads previously arrived with no phone). Fence-type list adds "Chain link with privacy slats", "Fence repair", "Other" based on real lead requests. Vinyl/field fence intentionally NOT added until Jared confirms he offers them.
