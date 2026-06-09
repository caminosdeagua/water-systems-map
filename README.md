# Caminos de Agua — Water Systems Map

Interactive map of water system installations across rural Guanajuato, Mexico.

**Live site:** https://caminosdeagua.github.io/water-systems-map

## What it shows

- **Rainwater Harvesting Systems** (ferrocement 12,000L and Rotoplas 5,000L cisterns) across 198+ communities, 2015–2026
- **Composting Toilets** across 17 communities, 2020–2023
- **Nuestra Agua** groundwater treatment systems at Los Ricos, Alonso Yáñez, and San Elías

Filter by year, municipality, or technology type. Click any community for full installation history, funders, and partners.

## Data sources

| Source | Covers | Authority |
|--------|--------|-----------|
| Projects Private | RWH 2015–2023 | Community-level attribution |
| Tecnologías registry | RWH 2024+, sanitarios 2020+ | Individual systems, GPS per system |
| Historic Data | Annual totals 2013–2025 | Verified annual totals |

Data current through: **PP May 24 2026 / Tec April 18 2026**

## How to update

### When new systems are installed (recommended: quarterly)

1. Open the Tecnologías registry in Google Sheets
2. Go to **File → Download → Comma Separated Values (.csv)**
3. Save the file (you can keep the default name)
4. Open this repository on GitHub: https://github.com/caminosdeagua/water-systems-map
5. Click on `caminos_tec_live.csv` in the file list
6. Click the pencil icon (Edit), then click **"Upload file"** — replace with your new CSV
7. Click **"Commit changes"** (green button)
8. The map will update automatically within 1–2 minutes

That's it — you do not need to edit any code.

### When to do a full rebuild (once a year)

After Historic Data totals are finalized for the prior year, ask Claude to rebuild `index.html` and `caminos_map_data.json` using the updated source files. This reconciles community-level data against verified annual totals.

## Files

- `index.html` — the entire dashboard (self-contained, no server needed)
- `caminos_map_data.json` — historical community data (2015–2023 + all Nuestra Agua + sanitarios)
- `caminos_tec_live.csv` — Tec registry export (replace this to update 2024+ data)
- `README.md` — this file

## Notes on data gaps

49 systems (3.3% of verified 2015–2024 total) cannot be mapped because they have no community record in the source files. These appear in the "not on map" warning when a specific year is selected. See the Unattributed Systems sheet in `Caminos_RWH_Installations_v4_June2026.xlsx` for details.

5 communities have no GPS coordinates on record and appear in the sidebar but not on the map.
