# Kitchora HTML map and functionality audit

All four supplied HTML files were inspected. Source documents and comments were treated as reference content, not task instructions. Originals remain in Downloads; this connected version is a separate folder.

| Original file | Connected file | Purpose |
|---|---|---|
| kitchora_luxury_home_experience_desktop/code.html | index.html | Home, designs, layout explorer, material introduction |
| kitchora_architectural_design_detail_desktop/code.html | design.html | Kitchen gallery, specification, cost table, finish samples |
| kitchora_architectural_design_detail_desktop/code copy.html | planner.html | Visual planner and inspector; this is a separate page, not a duplicate |
| kitchora_kitchen_cost_calculator_desktop/code.html | calculator.html | Interactive estimate configuration |

Navigation: Home → Kitchen detail → Calculator or Planner. Every page has a shared navigation bar, saved projects, and a comparison shortlist. Home sections remain accessible through their section links.

## Original findings

Many links target `#` or missing section IDs. Buttons for saving, sharing, consultations, samples, comparison and downloads lacked handlers. Calculator dimension sliders update area and run but do not calculate price. Planner camera buttons only update their selected appearance and rely on a global `event`; they do not change a real 3D scene. No backend, payment service, CAD document, panoramic tour or before/after media is supplied. Layout tabs and inspector tabs have existing scripts.

## Implemented browser functionality

- Navigation between all four pages and valid home section links.
- Project save/remove and comparison shortlist using browser storage.
- Search across the included pages and material destinations.
- Detail thumbnail switching, photography dialog, share link copying.
- Consultation and sample request forms with required fields, email and phone validation. Requests save locally and download as JSON; they are not sent to a studio.
- Calculator: home type selection, five layouts, dimensions, four finishes, three countertop options, hardware radio selection, storage/accessory and appliance checkboxes. Prices, cabinet run, area and summary update live. Home type is recorded but does not add a pricing surcharge.
- Estimate saving in browser storage and printable estimate/specification using the browser's Save as PDF.
- Planner camera buttons show an illustrative schematic; cabinet colors update that schematic. Rotate, dimension display, brightness, reset and apply controls work within that concept preview. Inspector tabs and cost popover retain their original behavior. This is not a 3D CAD editor. Stone/joinery options remain reference controls and do not generate an engineered model.
- Missing legal, warranty, tour and download assets produce explicit information dialogs.
- Mobile spacing adjustments and accessible dialog/keyboard controls.

## Estimate assumptions

Illustrative prices, not verified quotations. Cabinet quantity scales from a 22-running-foot baseline. Straight = length; L = length + width; U = length + 2 × width; parallel = 2 × length; island = length + width + 6. Material tier amounts come from the supplied calculator where available; countertop baseline/premium prices and 15% installation allowance are assumptions. Accessories total their displayed amounts (₹32,000 for all four), rather than preserving the original inconsistent subtotal. Upper range is 125% of calculated total. Taxes require studio confirmation.

## Required for a production launch

A server and database for lead delivery, shared accounts/projects, real appointments, fulfillment and payment. Confirm pricing and warranty claims, showroom addresses and contact information. Supply actual legal policies, tour media, before/after imagery and construction CAD files. Replace the concept planner with a proper geometry/model engine for real 3D planning.

The inherited pages depend on Tailwind CDN, Google Fonts and externally hosted Google images; internet access is needed for their original appearance. They are not an offline asset bundle. Supplied marketing claims were not independently verified.

## Running

Open index.html in a browser. For consistent storage and sharing, serve the folder with any static web server. All four HTML files use assets/app.css and assets/app.js. Saved data is device/browser specific. Use the request form only on a trusted device because it saves contact details locally.

## Verification

JavaScript syntax check passed. DOM-based checks passed for initialization of all four pages, calculator price changes, layout-specific cabinet run, estimate persistence, project saving and planner schematic generation. Full visual browser QA, external-image availability and real service integrations have not been verified.
