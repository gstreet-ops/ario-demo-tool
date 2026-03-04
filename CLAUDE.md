# Ario Demo Tool - Claude Context

## What This Project Is
A self-contained interactive pre-sales demo tool for Ario (ariodata.com). Ario is a retail data intelligence platform that gives brands customer-consented, SKU-level purchase data from other retailers, so brands can see what their customers buy beyond their own store.

This tool is designed for pre-sales education, not deal closing. It makes Ario's value proposition tangible through narrative-driven synthetic customer stories.

## Primary File
**ario-demo.html** - The complete application. Single HTML file, ~130KB, no build step, no server needed. React 18 via CDN, all data embedded as JS constants. Open directly in any browser.

## Data File
**ario-synthetic-data.json** - All synthetic data in JSON format for review/editing.
Data is also embedded directly inside ario-demo.html as the DATA constant.

## Key Architecture Decisions
- Single-file by design - maximum portability (email, USB, iframe, hosted page)
- All synthetic data embedded in JS - no API calls, works offline
- React + Babel Standalone via CDN - no npm, no build step required
- CSS custom properties for design system - all tokens at top of style block

## Design System
- Primary blue: #2356F6
- Navy: #0F1B3D
- Fonts: DM Serif Display (headings) + DM Sans (body)
- Border radius: 12px (standard), 20px (cards)

## Three Demo Modes
1. Brand Story - pick brand, pick persona, step through guided narrative
2. Use Case - pick strategic goal, tool surfaces relevant brand story
3. Simulate Your Brand - enter company name + category, personalized demo

## Brands & Personas (15 total across 9 brand scenarios)
- IKEA: Eliza Santos (Bathroom Renovator), Maria Chen (New Parent)
- Ashley Furniture: Brian Kowalski (Man Cave Builder), Maria Chen (New Parent)
- Sephora: Derek Pham (Premium Male Groomer), Sofia Reyes (Pregnancy Life Stage)
- Hunter Douglas: Carol Martinez (Whole Home Refresh), James & Priya Okafor (New Home Buyers)
- Stitch Fix: Priya Nair (Career Wardrobe Upgrader), Lauren Kim (Life Event Dresser)
- Rejuvenation: Tom Bergstrom (Historic Home Restorer)
- Energizer: Marcus Thompson (Techie/High-Drain Device Owner), Sarah O'Connell (Parent/Emergency Buyer)
- TextNow [NEW]: Jaylen Brooks (Young Parent - Household Buyer, Walmart data)
- Rejuvenation 2 [NEW]: Marcus & Dana Webb (Design Consultation Candidate, serial Wayfair returner)

## Use Cases (5 total)
1. Life Stage Targeting - new parent, new home, career change signals
2. Competitive Intelligence - customers buying from competitors invisibly
3. Smarter Personalization - project intent vs. item intent marketing
4. Ad Targeting Uplift [NEW] - real household purchase data vs. demographic proxies (TextNow)
5. Design Consultation Intercept [NEW] - high-budget buyers at peak uncertainty (Rejuvenation)

## Screen Flow
Landing -> Mode Selection -> Setup -> Data Scan Animation -> Panelist Hub -> Behavioral Insights -> Before/After -> Strategic Questions -> CTA

## Mobile Responsiveness (updated v1.1)
- Stepper scrolls horizontally with hidden scrollbar on mobile
- Tables scroll horizontally inside .table-card
- Brand grid collapses to 2-column on mobile
- Before/After toggle expands to full width
- Panelist tabs scroll horizontally
- Buttons stack vertically at 480px breakpoint
- All padding tightened for small screens

## Visual Polish (v1.1)
- "New" badge on TextNow and Rejuvenation 2 brand cards
- "New" badge on Ad Targeting Uplift and Design Consultation Intercept use case tiles
- Use case grid supports 5 items (3+2 layout)
- Hero stats updated to reflect 9 brands, 15 personas, 5 use cases

## Website Integration Options
1. Iframe embed - one line of HTML, works anywhere
2. Dedicated page - host as ariodata.com/demo
3. Native integration - extract into site codebase (Webflow, Next.js, etc.)
4. Gated version - add email capture before demo loads (~2hrs dev work)

## Iframe Embed Code
<iframe src='ario-demo.html' width='100%' height='900px' frameborder='0' style='border-radius:12px;border:1px solid #E2E8F0;'></iframe>

## How to Update Data
1. Edit ario-synthetic-data.json for review/approval
2. Copy updated brand/persona objects into the DATA constant in ario-demo.html
3. No build step needed - save and refresh browser

## Important Disclaimer
All data is synthetic. Every customer profile, purchase history, and insight is invented for illustration purposes. No real consumer data is used. The disclaimer banner must remain visible in any public deployment.

## Category to Brand Mapping (Simulate Mode)
- Beauty / Health & Personal Care -> Sephora
- Home & Kitchen / Appliances -> IKEA
- Tools & Home Improvement -> Hunter Douglas
- Electronics / Toys & Games / Sports -> Energizer
- Clothing, Shoes & Jewelry -> Stitch Fix
- Arts, Crafts & Sewing -> Rejuvenation
- Cell Phones & Accessories / Grocery -> TextNow
- All others -> IKEA (default)

## CTA Target
https://ariodata.com - update the href in BeforeAfterPanel component if needed.

## Phase 2 Recommendations
- Email gate before demo (~2hrs)
- Analytics event tracking (~1hr)
- Offline bundle (fonts + React local) (~4hrs)
- New brand verticals as Ario expands
- Website integration (Webflow / Next.js / iframe embed)
