# Datasets (`data/datasets/`)

Publicly available climate downscaling datasets produced by HiClimaX and collaborating institutions.

## Structure
```
data/datasets/
├── datasets.csv      # Dataset catalog and metadata
├── previews/         # Preview images and sample data visualizations
└── README.md         # This file
```

## CSV Columns

| Column | Required | Format | Description |
|--------|----------|--------|-------------|
| **id** | Yes | kebab-case | Unique dataset identifier |
| **name** | Yes | Descriptive title | "Tokyo Dynamical Downscaling 2050/2100" |
| **domain** | Yes | Region/city | "Tokyo metro area", "Mekong Delta", "Global" |
| **methods** | Yes | Method codes | "D-DS", "PGW·SD-DS" (dot-separated if multiple) |
| **spatial_res** | Yes | Grid resolution | "4 km", "500 m", "100 m", "25 km" |
| **temporal_coverage** | Yes | Year range | "2020-2100", "1980-2050" |
| **variables** | Yes | Dot-separated list | "Tmax·Tmin·Precip·Wind·SolarRad" |
| **frequency** | Yes | Time step | "Daily", "Hourly", "Monthly", "Seasonal", "Event-based" |
| **status** | Yes | Dataset state | "Available", "In Review", "Under Curation", "Coming Soon" |
| **doi** | No | DOI identifier | "10.5281/zenodo.tokyo-dd-2020" or "preprint" |
| **institution** | Yes | Organization(s) | "Tokyo Metropolitan University" |
| **size** | Yes | Data volume | "42 GB", "2.3 TB" |
| **access_url** | Yes | Download link | "https://zenodo.org/datasets/..." |

## Current Datasets

### Urban-Focused (City Scale)
1. **Tokyo Dynamical Downscaling** (4 km, 2020-2100)
   - Method: Physics-based dynamical downscaling
   - Variables: Temperature extremes, precipitation, wind, solar radiation
   - Institution: Tokyo Metropolitan University
   - Size: 42 GB | Status: Available

2. **Ho Chi Minh City Pseudo-Global Warming** (1 km, 2010-2050)
   - Method: PGW for extremes detection
   - Variables: Extreme rainfall, heatwaves, sea-level rise
   - Institution: University of Science Vietnam
   - Size: 18 GB | Status: Available

3. **Brussels Statistical-Dynamical** (500 m, 2020-2050)
   - Method: Hybrid statistical-dynamical
   - Variables: Precipitation, temperature, humidity, pressure
   - Frequency: Hourly data
   - Institution: Royal Meteorological Institute Belgium
   - Size: 156 GB | Status: Available

4. **Urban Heat Island LSP Dataset** (100 m, 2015-2050)
   - Method: Land-surface physics focusing on urban microclimates
   - Covers: 20+ global cities (Tokyo, Mumbai, Lagos, Bangkok, etc.)
   - Variables: Surface temperature, urban canyon effects, radiation
   - Resolution: 30-minute timesteps for intra-day heating cycles
   - Size: 780 GB | Status: Available

### Regional-Scale (Continent/Continental)
5. **Global Statistical Downscaling Ensemble** (25 km, 1980-2100)
   - Method: Statistical downscaling with ensemble
   - Spatial coverage: Global land + coastal areas
   - Variables: Temperature, precipitation, pressure
   - Institution: Max Planck Institute
   - Size: 2.3 TB | Status: Available
   - Monthly data for long-term climate change analysis

6. **Alpine Region Dynamical Downscaling** (2 km, 1971-2100)
   - Method: Dynamical downscaling (physics-based)
   - Coverage: European Alps and adjacent regions
   - Variables: Precipitation, snowpack, glaciers, temperature
   - Validation: 30+ years of historical data
   - Institution: ETH Zurich
   - Size: 340 GB | Status: Available

7. **Tropical Monsoon PGW Dataset** (5 km, 1961-2050)
   - Method: Pseudo-Global Warming approach
   - Focus: South Asian monsoon dynamics
   - Variables: Monsoon index, extremes, flooding risk, drought
   - Partner institutions: University of Lagos, University of Tokyo
   - Size: 95 GB | Status: Available

### Specialized Applications
8. **Fire Weather Derived Downscaling** (500 m, 1980-2050)
   - Methods: Statistical downscaling + SDS
   - Geography: Mediterranean basin, Australian fire zones
   - Variables: Temperature, humidity, wind speed, drought indices
   - Use case: Wildfire risk assessment and forecasting
   - Institution: Met Office UK
   - Size: 310 GB | Status: Available

9. **Coastal Storm Surge & LSP** (200 m, 2010-2100)
   - Method: Land-surface physics + sea-level coupling
   - Focus: Major port cities (Singapore, Rotterdam, Shanghai, etc.)
   - Variables: Sea level rise, wind, pressure, wave heights
   - Resolution: Hourly for storm event analysis
   - Institution: Barcelona Supercomputing Center
   - Size: 2.1 TB | Status: Under Curation

10. **Alpine Snowpack & Wind** (1 km, 1980-2100)
    - Method: Dynamical downscaling specialized for mountains
    - Region: Hindu Kush-Himalayas (water stress critical)
    - Variables: Snowpack, wind extremes, temperature, precipitation
    - Daily resolution for water resource planning
    - Institution: International Centre for Integrated Mountain Development (ICIMOD)
    - Size: 420 GB | Status: Available

### In Development
11. **AI-Based Seasonal Forecasting** (10 km, 2020-2050)
    - Method: Deep learning neural networks
    - Coverage: Asia-Pacific region
    - Variables: Seasonal precipitation, temperature, extremes, drought indicators
    - Status: **In Review** at Nature Climate Change
    - Institution: Max Planck Institute
    - Size: 120 GB

12. **Agricultural Impact Downscaling** (1 km, 2000-2050)
    - Method: Statistical downscaling optimized for crops
    - Coverage: Global agricultural regions
    - Variables: Precipitation, Tmax/Tmin, solar radiation, drought metrics
    - Use case: Crop yield projections, agricultural adaptation planning
    - Status: **Coming Soon** (Q2 2026)
    - Size: Pending

## How to Access Datasets

### Download Options
1. **Zenodo Repository**: All datasets with proper DOI citations (recommended)
2. **Direct FTP**: Large datasets available via FTP for institutional users
3. **Cloud Storage**: AWS S3 buckets with daily/monthly rolling access
4. **Data Portal** (planned): Interactive web interface with subset downloads

### Basic Information by Status

| Status | Meaning | Access |
|--------|---------|--------|
| **Available** | Fully processed, quality checked, published | Download immediately |
| **In Review** | Peer review / paper in submission | Preprint available, final data soon |
| **Under Curation** | Final QA checks, metadata completion | Early access on request |
| **Coming Soon** | Processing/validation in progress | Contact institution for timeline |

## Dataset Citation

When using HiClimaX datasets, cite with DOI:

**APA Format Example:**
```
Yamamoto, K., Chen, S., Bianchi, M., et al. (2024). 
Tokyo Dynamical Downscaling 2050/2100 Dataset. 
Zenodo. https://doi.org/10.5281/zenodo.tokyo-dd-2020
```

**BibTeX:**
```bibtex
@dataset{tokyo_dd_2024,
  author = {Yamamoto, K. and Chen, S. and Bianchi, M.},
  title = {Tokyo Dynamical Downscaling 2050/2100 Dataset},
  year = {2024},
  doi = {10.5281/zenodo.tokyo-dd-2020},
  publisher = {Zenodo}
}
```

## Data Specifications

### File Formats
- **NetCDF4** (CF-compliant) - Primary format for climate data
  - Self-describing, includes metadata, compression
  - Tools: Python (xarray, netCDF4), R (ncdf4), CDO
- **GeoTIFF** - For spatial maps and visualizations
- **CSV/Parquet** - Summary statistics and temporal series

### Variable Naming Conventions
- **Tmax** = Maximum daily temperature (°C)
- **Tmin** = Minimum daily temperature (°C)
- **Precip** = Precipitation amount (mm)
- **Wind** = Wind speed (m/s)
- **SolarRad** = Downwelling shortwave radiation (W/m²)
- **RelHumidity** = Relative humidity (%)
- **SeaLevel** = Sea level anomaly (mm)

### Global Attributes (Metadata)
Every dataset includes:
- Title, institution, contact author
- Method description and parameters
- Grid projection (typically WGS84 or local UTM)
- Temporal resolution and units
- References to methodology papers
- Quality flags and uncertainty estimates

## Data Quality & Validation

### QA/QC Procedures
- Validation against observations (where available)
- Cross-method ensemble consistency checks
- Physical bounds checking (e.g., no negative precipitation)
- Temporal continuity verification
- Bias quantification reports included

### Uncertainty Quantification
Most datasets include:
- Ensemble member ranges (min/max/std) when applicable
- Bias corrections applied (documented)
- Confidence intervals for diagnosed extremes
- Uncertainty attributable to: method choice, input GCM, downscaling parameters

## Adding New Datasets

1. **Complete dataset entry** in `data/datasets/datasets.csv`:
   ```csv
   new-dataset-id,Dataset Full Name,Geographic Domain,Method1·Method2,1 km,2020-2050,Var1·Var2·Var3,Daily,Available,10.5281/zenodo.xxxxx,Institution Name,500 GB,https://zenodo.org/xxxxx
   ```

2. **Register DOI** with Zenodo/DataCite
   - Include comprehensive metadata
   - Attach methodology paper or paper DOI
   - Add dataset tags: hiclimax, downscaling, [method], [region]

3. **Create preview** for datasets.html:
   - Sample map image (spatial coverage)
   - Time series example graph
   - Data availability calendar
   - Save to `data/datasets/previews/`

4. **Update documentation**:
   - Add new dataset section above with key details
   - Include access/citation information
   - Link related methodology paper

## Future Dataset Features

- [ ] Interactive data portal with subset downloads
- [ ] On-demand regridding to user-specified resolution
- [ ] Web-based visualization of dataset previews
- [ ] API endpoint for programmatic access
- [ ] Comparison tool: "Find similar datasets"
- [ ] Dataset discovery by climate variable or region
- [ ] Real-time data quality dashboard

## Questions or Access Issues?

Each dataset lists **institution and contact researcher** — reach out directly for:
- Technical specifications beyond CSV metadata
- Custom subsetting or processing requests
- Permissions for non-academic use
- Collaboration opportunities

See [data/partners/partners.csv](../partners/) for institutional contacts by region.
