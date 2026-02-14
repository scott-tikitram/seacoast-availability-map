# Sea Coast Rentals — Availability Map

## Overview

Public-facing property availability viewer for Sea Coast Rentals. Guests browse available vacation rental properties by date with location filtering, map/list views, and booking links. No authentication required.

Based on the vendor-deal-viewer architecture from EventureMap.

## Tech Stack

- **Frontend**: Vanilla HTML/JS/CSS (single-page, self-contained)
- **Maps**: Google Maps API
- **API**: Property Management API (public fields only)
- **Deployment**: AWS Amplify (separate from admin dashboard)

## Project Structure

```
availability-map/
├── index.html                  # Main app (v1.1.0, ~all-in-one)
├── amplify.yml                 # Amplify deployment config
├── CircleDolphinNoAlpha200.png # Sea Coast Rentals logo
├── seacoastrentalslogo.png     # Header logo
├── DEPLOY.md                   # Deployment notes
└── README.md
```

## Development Commands

```bash
# Local dev — open index.html directly in browser
# No build step needed (vanilla HTML/JS)
```

## Key Features

- **Date navigation**: Browse availability day-by-day with arrow controls
- **Location filter**: Quick-filter dropdown by property location
- **Advanced filters**: Amenities, bedrooms, bathrooms in modal dialog
- **Map view**: Google Maps with property markers
- **List view**: Property cards with images and details
- **Booking links**: Direct links to booking pages
- **Mobile responsive**: Optimized for phone browsing

## API Integration

- Uses `property-management-api` with `fields=public` filter
- Header: `X-Company-Key` (no `x-api-key` to avoid CORS preflight)
- Only returns non-sensitive public property information
- Tenant: `seacoastrentals` (hardcoded)

## Deployment

Deployed via AWS Amplify. See top-level CLAUDE.md for deployment workflow.

## Related Projects

- **Admin Dashboard**: `../eventuremap/webtools/admin-dashboard/` — property management UI
- **Guesty Integration**: Properties synced from Guesty PMS
