# Case Studies (`data/case_studies/`)

Documentation for regional case study demonstrations and climate impact scenarios.

## Structure
```
data/case_studies/
├── cases.csv         # Case study metadata and metrics
├── assets/           # Photos, maps, climate data visualizations
└── README.md         # This file
```

## CSV Columns

| Column | Required | Format | Description |
|--------|----------|--------|-------------|
| **id** | Yes | lowercase-kebab | Unique identifier (e.g., "tokyo", "hcmc") |
| **city** | Yes | City name | "Tokyo", "Ho Chi Minh City", "Brussels" |
| **region** | Yes | Geographic region | "Kanto", "Southeast Asia", "Central Europe" |
| **country** | Yes | Country name | "Japan", "Vietnam", "Belgium" |
| **emoji** | No | Unicode emoji | Regional or climate-relevant emoji |
| **description** | Yes | 1-2 sentences | Key climate challenges and focus areas |
| **climate_context** | Yes | Climate classification | "Temperate oceanic", "Tropical monsoon" |
| **metrics_temp** | Yes | Temperature change | "±2.5°C", "-0.5°C to 2.5°C scenarios" |
| **metrics_precip** | Yes | Precipitation change | "±15%", "+10% to +20% extreme rainfall" |
| **lead_researcher** | No | Name | "Dr. Kenji Yamamoto" |
| **organization** | No | Institution | "Tokyo Metropolitan University" |
| **photo** | No | Path to image | "data/case_studies/assets/tokyo-skyline.jpg" |

## Current Case Studies

1. **Tokyo** (id: tokyo)
   - Focus: Urban heat island in mega-city
   - Climate: Temperate with seasonal variation
   - Lead: Dr. Kenji Yamamoto (Tokyo Metropolitan University)

2. **Ho Chi Minh City** (id: hcmc)
   - Focus: Tropical delta and sea-level rise
   - Climate: Tropical monsoon
   - Lead: Dr. Nguyen Anh Duc (University of Science Vietnam)

3. **Brussels** (id: brussels)
   - Focus: Urban adaptation and rainfall intensification
   - Climate: Temperate oceanic
   - Lead: Dr. Romain Hamdi (Royal Meteorological Institute)

## Adding a New Case Study

1. **Create entry** in `data/case_studies/cases.csv`:
   ```csv
   mumbai,Mumbai,Western India,India,🌊,Rapid urbanization and monsoon intensification,Tropical monsoon,+2.0°C to +4.0°C,+15% to +25% monsoon rainfall,Dr. [Name],Institution,data/case_studies/assets/mumbai-harbor.jpg
   ```

2. **Add assets** to `data/case_studies/assets/`:
   - City skyline or landmark photo
   - Climate maps or visualizations
   - Data charts (temperature/precipitation trends)

3. **Update related pages**:
   - Add city card to index.html (if applicable)
   - Create dedicated case study page (e.g., `case-study-mumbai.html`)
   - Link from main case studies section

## Asset Guidelines

- **Images**: JPG/PNG, high quality, 1200px+ width
- **Charts**: Interactive (D3.js, Plotly) or static SVG
- **Maps**: Regional context showing city and climate zones
- **File naming**: Use kebab-case matching case study ID (mumbai-harbor.jpg, mumbai-monsoon-map.svg)

## Future Expansion

As case studies expand, consider:
- Adding `baseline_climate.csv` per city with historical data tables
- Including `hourly_projections.csv` for detailed time-series data
- Storing `methodology_details.md` explaining downscaling choices per city
- Adding `uncertainty_quantification.csv` for ensemble ranges

## Loading in Pages

Use pattern from `team.html`:
```javascript
const response = await fetch('data/case_studies/cases.csv');
const text = await response.text();
const cases = parseCSV(text);
// Render each case...
```

See existing implementations for renderCase() patterns.
