# WASH Decision Support Platform

Open-source, source-driven web GIS for humanitarian WASH decision support.

## Nepal Flood 2026 pilot

This repository contains the first implementation for the Nepal Flood 2026 WASH response. The platform is deliberately modular so the same codebase can be reused for future emergencies.

### Core operating principle

> **Update raw data at source. Everything downstream is handled automatically.**

### Current v1 modules

- Interactive MapLibre map using CARTO basemaps
- Municipality-level WASH severity / priority map for 17 affected municipalities
- Clickable municipality profiles
- P1 / P2 / P3 driver display
- User-adjustable scenario weights without altering official results
- Flood extent layer
- Holding-centre layer
- Road/access status layer
- Available ward-boundary layer
- Data status and provenance views
- CSV export of municipality priority results

### Analytical model

Official default weighting:

- **P1 — Flood Impact & WASH Service Disruption:** 45%
- **P2 — Current WASH Conditions:** 35% (provisional)
- **P3 — Pre-existing Vulnerability & Aggravating Factors:** 20%

Response footprint and evidence confidence are interpretation layers and do not reduce Need Severity.

### Source architecture

- Maintained analytical source: Google Sheets
- Maintained spatial sources: authoritative GIS files
- Static public outputs: JSON / GeoJSON in `data/`
- Frontend: static HTML/CSS/JavaScript + MapLibre
- Hosting: GitHub Pages
- Automation: GitHub Actions

### Important

The files under `data/` are generated/publication outputs, not the intended editing surface. The dashboard is public and contains no authentication.

### Phase 2

The operational 5W Google Sheet will be ingested later as a separate response-monitoring module.