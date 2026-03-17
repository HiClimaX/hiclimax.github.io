# Partners & Organizations (`data/partners/`)

Collaborating institutions and research organizations in the HiClimaX network.

## Structure
```
data/partners/
├── partners.csv      # Partner organizations metadata
├── logos/            # Organization logos and branding
└── README.md         # This file
```

## CSV Columns

| Column | Required | Format | Description |
|--------|----------|--------|-------------|
| **id** | Yes | lowercase | Unique identifier (tsukuba, ethz, mit) |
| **name** | Yes | Organization name | "University of Tsukuba" |
| **type** | Yes | Category | "Academic Institution", "Research Organization", "Government Agency" |
| **region** | Yes | Geographic region | "Asia", "Europe", "North America" |
| **website** | Yes | Full URL | "https://www.tsukuba.ac.jp" |
| **logo** | No | Path to image | "data/partners/logos/tsukuba.png" |
| **focus_areas** | Yes | Comma-separated | "Climate modeling · Computational science" |
| **status** | Yes | active, inactive | "Active", "Archived" |

## Partner Categories

- **Academic Institutions**: Universities and research centers
- **Research Organizations**: National institutes, Max Planck groups
- **Government Agencies**: Meteorological institutes, climate bureaus
- **Private Sector**: Companies contributing technology/infrastructure
- **NGOs**: Non-profit organizations supporting climate research

## Current Partners

8 partner organizations across 3 continents:

**Asia** (3 institutions)
- University of Tsukuba (Japan) - Computational science
- Indian Institute of Science (India) - Urban microclimate
- University of Science Vietnam - Tropical climate

**Europe** (4 institutions)
- ETH Zurich (Switzerland) - Alpine climate
- Swedish Meteorological Institute - Regional forecasting
- University of Bologna (Italy) - Regional modeling
- Max Planck Institute (Germany) - Climate modeling & AI

**North America** (1 institution)
- MIT (USA) - Earth systems dynamics

## Adding New Partners

1. **Create logo** (preferred: SVG or transparent PNG, 200-300px)
   - Save to `data/partners/logos/` with kebab-case name
   - Example: `data/partners/logos/new-university.png`

2. **Add CSV entry**:
   ```csv
   univ-xx,University of XX,Academic Institution,Region,https://www.universityofxx.edu,data/partners/logos/univ-xx.png,Focus area 1 · Focus area 2,Active
   ```

3. **Organize by region** for future geospatial visualization:
   - Asia, Europe, North America, South America, Africa, Oceania

## Logo Guidelines

- **Format**: SVG preferred (scalable), PNG acceptable
- **Size**: 200-300px width, transparent background
- **Color**: Full color (not grayscale) - shows institution branding
- **Naming**: Use kebab-case matching partner id (tsukuba.svg, ethz.png)
- **Location**: `data/partners/logos/` directory

## Partner Status

- **Active**: Ongoing collaboration
- **Inactive**: Historical partnership or completed projects
- **Archived**: Partnerships no longer continuing

Update status field when partnerships change.

## Future: Partnerships Page

Planned page (`partnerships.html`) would:
- Load `partners.csv` and display organization grid
- Show logos with links to institution websites
- Filter by region, type, or focus area
- Display contact researcher for each partner
- Map partner locations geographically (Leaflet.js or Mapbox)

Example rendering:
```javascript
const partnerships = await fetch('data/partners/partners.csv');
const partners = parseCSV(partnerships);
partners.forEach(p => {
  // Create logo card with link to website
  // Show focus areas as tags
  // Link to lead researcher from team.csv
});
```

## Collaboration Framework

Partner institutions typically:
1. Contribute method expertise (one downscaling approach)
2. Lead case studies in their region
3. Host team members or postdocs
4. Provide computational resources
5. Co-author publications
6. Contribute to governance/steering committee

## Contact & Outreach

To add your institution:
1. Contact HiClimaX leadership
2. Complete partnership agreement
3. Designate lead researcher
4. Provide high-quality logo
5. Define specific contribution areas
6. Add to CSV once formalized

See team.html for team member affiliations and find the representative from desired partner institution.
