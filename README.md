# Caminos de Agua — Water Systems Maps

Two interactive maps showing water technology installations across rural Guanajuato, Mexico.

**Community Map (live):** https://caminosdeagua.github.io/water-systems-map
**Technology Registry (live):** https://caminosdeagua.github.io/water-systems-map/registry.html

---

## Map 1: Water Systems by Community (`index.html`)

Historical overview of all rainwater harvesting, composting toilet, and Nuestra Agua installations by community, 2015–present.

**What it shows:**
- One pin per community, sized by number of systems installed
- Rainwater harvesting systems (ferrocement 12,000L and Rotoplas 5,000L)
- Composting toilets
- Nuestra Agua groundwater treatment systems (Los Ricos, Alonso Yáñez, San Elías)
- Cumulative totals by year — select a year to see everything installed through that point

**Data source:** `caminos_map_data.json` — built from Projects Private (2015–2023), Tecnologías registry (2024+), and Historic Data annual totals.

**Data current through:** Projects Private May 24, 2026 · Tecnologías registry April 18, 2026 · Historic Data 2024 final / 2025 partial

**Note:** 49 RWH systems (3.3% of verified 2015–2024 total) have no community-level record and cannot be mapped. 5 communities have no GPS coordinates and appear in the sidebar only.

---

## Map 2: Technology Installation Registry (`registry.html`)

Individual system-level registry from the Tecnologías tracking sheet, 2020–present. Primarily covers 2024+ where records are most complete.

**What it shows:**
- One dot per system installed (RWH, filters, composting toilets)
- Filters by year, technology type, municipality, funder, collaborator, and project
- "AEA — Todas las ministraciones" filter shows all Agua en Acción systems across all ministraciones
- Summary table: totals by technology, funder, and year
- Photo links where available (Google Photos and Google Drive)

**Technology types:**
- SCALL — Ferrocemento (12,000L)
- SCALL — Rotoplas (5,000L)
- Filtro — Aguadapt
- Filtro — EOZ
- Filtro — Sawyer
- Sanitarios secos

**Data source:** `registry_data.json` — built from Tecnologías registry CSV export.

**Data current through:** April 2026

**Note:** Only 12% of systems have GPS coordinates currently. Map shows placed systems only; all systems appear in the sidebar and summary table regardless of GPS. Coordinates will be completed in future registry updates.

---

## Files in this repo

| File | Purpose |
|------|---------|
| `index.html` | Community map — all HTML, CSS, and data embedded |
| `registry.html` | Registry map — all HTML, CSS, and data embedded |
| `caminos_map_data.json` | Data for community map |
| `registry_data.json` | Data for registry map |
| `README.md` | This file |

---

## How to update

### Update the registry map (when new Tec data is available)

The registry map data needs to be rebuilt by Claude when you have a new Tec export. In the Caminos Project Records project in Claude:

1. Upload the new Tec registry CSV
2. Ask Claude to rebuild `registry_data.json` and `registry.html` using `build_registry.py`
3. Upload the new files to this repo

### Update the community map (annually)

After Historic Data totals are finalized for the prior year, ask Claude to rebuild `caminos_map_data.json` and `index.html` using `build_final.py`. Do this once a year.

### Add/update content (Nuestra Agua details, community notes, etc.)

Edit `caminos_map_data.json` directly or ask Claude to update it, then rebuild `index.html`.

---

## Embed on website (Squarespace)

Add a Code Block and paste:

```html
<!-- Community map -->
<iframe src="https://caminosdeagua.github.io/water-systems-map"
  width="100%" height="650px" style="border:none;border-radius:8px;"
  title="Mapa de sistemas de agua — Caminos de Agua"></iframe>

<!-- Registry map -->
<iframe src="https://caminosdeagua.github.io/water-systems-map/registry.html"
  width="100%" height="650px" style="border:none;border-radius:8px;"
  title="Registro de tecnologías — Caminos de Agua"></iframe>
```

---

## Build scripts (stored in Claude project, not needed on GitHub)

- `build_final.py` — rebuilds `index.html` and `caminos_map_data.json`
- `build_registry.py` — rebuilds `registry.html` and `registry_data.json`
