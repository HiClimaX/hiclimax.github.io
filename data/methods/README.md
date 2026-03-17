# Methods/Models (`data/methods/`)

Reference documentation for HiClimaX downscaling methodologies.

## Structure
```
data/methods/
├── methods.csv       # Method metadata and descriptors
└── README.md         # This file
```

## CSV Columns

| Column | Required | Format | Description |
|--------|----------|--------|-------------|
| **id** | Yes | lowercase | Method ID (dd, pgw, sd, lsp, sds, ai) |
| **name** | Yes | Short name | "Dynamical Downscaling" |
| **abbreviation** | Yes | 2-4 chars | "D-DS", "PGW" |
| **full_name** | Yes | Descriptive | "Dynamical Downscaling System" |
| **emoji** | No | Visual marker | 💨, 🌍, 📊, etc. |
| **description** | Yes | 1-2 sentences | Technical approach explanation |
| **lead_researcher** | No | Name | "Dr. Marco Bianchi" |
| **use_cases** | Yes | Comma-separated | "Regional projections, seasonal forecasting" |
| **resolution** | Yes | Grid scale | "~4-12 km", "City-scale", "Fine-scale grid" |
| **time_scale** | Yes | Temporal scope | "Daily to seasonal", "Monthly to decadal" |

## Methods in HiClimaX

1. **Dynamical Downscaling (D-DS)**
   - Lead: Dr. Marco Bianchi
   - Approach: Physics-based nested high-resolution simulations
   - Resolution: ~4-12 km
   - Best for: Regional climate projections, long-term scenarios

2. **Pseudo-Global Warming (PGW)**
   - Lead: Dr. Amara Okonkwo
   - Approach: Combines historical climate with global warming signals
   - Resolution: Variable
   - Best for: Attribution studies, event-based analysis

3. **Statistical-Dynamical (SD-DS)**
   - Lead: Dr. Helena Pettersson
   - Approach: Statistical relationships with dynamical model outputs
   - Resolution: Fine-scale
   - Best for: Rapid projections, monthly to seasonal forecasts

4. **Land-Surface Physics (LSP-DS)**
   - Lead: Dr. Rajesh Patel
   - Approach: Urban-scale heat and moisture interactions
   - Resolution: City-scale
   - Best for: Urban climate effects, microclimate modeling

5. **Statistical Downscaling System (SDS)**
   - Lead: Dr. Yuki Tanaka
   - Approach: Machine learning and statistical relationships
   - Resolution: Fine-scale grid
   - Best for: Extreme event modeling, daily timescales

6. **AI-Based Methods (AI-DS)**
   - Lead: Dr. Lena Mueller
   - Approach: Deep learning and neural networks
   - Resolution: Flexible
   - Best for: Pattern recognition, real-time predictions

## Comparison Matrix

| Aspect | D-DS | PGW | SD-DS | LSP | SDS | AI-DS |
|--------|------|-----|-------|-----|-----|-------|
| Computational Cost | High | Low | Medium | Medium | Medium | High |
| Uncertainty Quantification | ✓ | ✓ | ✓ | ✓ | ✓ | ⚠️ |
| Physical Basis | Full | Hybrid | Partial | Full | Partial | None |
| Scalability | Regional | Global | Fine-scale | Urban | Global | Variable |
| Interpretability | High | Medium | Medium | High | Low | Low |

## Adding Methodology Documentation

Store detailed technical documentation in method subdirectories:

```
data/methods/
├── dd/
│   ├── README.md          # Detailed technical description
│   ├── publications.json   # Related publications
│   └── parameters.csv      # Configurable parameters
├── pgw/
│   └── ...
```

## Integration with Pages

### In index.html
Method cards pull from method descriptions:
```javascript
const methods = await fetch('data/methods/methods.csv');
// Render 6 method cards with emoji, name, description
```

### Future: Dedicated Methods Pages
Create pages like `method-details.html?id=dd` that:
- Show full description and use cases
- Display comparison table
- Link to lead researcher
- Provide references and publications

## Updates & Versioning

When methods evolve:
1. Update CSV with new descriptions/parameters
2. Add version notes to `description` field
3. Create separate `methods-v2.csv` if major changes
4. Document in method README why changes occurred

See `methods.csv` for current state and `index.html` rendering logic.
