# Publications (`data/publications/`)

Research publications and references for HiClimaX framework and downscaling methods.

## Structure
```
data/publications/
├── publications.csv  # Publication metadata
└── README.md         # This file
```

## CSV Columns

| Column | Required | Format | Description |
|--------|----------|--------|-------------|
| **id** | Yes | pub### | Unique identifier (pub001, pub002, etc.) |
| **title** | Yes | Full title | "High-resolution climate projections..." |
| **authors** | Yes | "Author A. et al." | First author + co-author count |
| **year** | Yes | YYYY | 2024 |
| **journal** | Yes | Journal name | "Nature Climate Change" |
| **doi** | Yes | DOI | "10.1038/nclimate.2024.001" |
| **url** | No | Full URL | "https://example.com/paper" |
| **type** | Yes | Category | "Journal Article", "Data Paper", "Preprint" |
| **tags** | Yes | Comma-separated | "climate-modeling,downscaling,ai" |

## Publication Types

- **Journal Article**: Peer-reviewed research publications
- **Data Paper**: Datasets with methodology (Earth System Science Data, Scientific Data)
- **Conference Paper**: Proceedings from international conferences
- **Software Paper**: Software/framework descriptions
- **Preprint**: Pre-publication versions (arXiv, EarthArXiv)
- **Technical Report**: Extended documentation and technical details
- **Thesis**: PhD dissertations and Master's theses

## Tags for Organization

Common tags for filtering and discovery:
- **Methods**: downscaling, dynamical, statistical, machine-learning, ai
- **Applications**: climate-projection, urban-climate, extremes, heatwaves, flooding
- **Regions**: asia, africa, europe, tropical, temperate
- **Techniques**: ensemble, uncertainty-quantification, validation, attribution
- **Data**: high-resolution, observations, reanalysis, satellite

## Current Publications

6 publications documented:
- 1 Nature Climate Change article (Tokyo/urban downscaling)
- 1 Methods comparison (Geoscientific Model Development)
- 1 AI/ML paper (Journal of Climate)
- 1 Urban climate application (Urban Climate)
- 1 Framework overview (Earth System Science Data)
- 1 Uncertainty quantification (Climate Dynamics)

## Adding Publications

1. **Add entry** to `data/publications/publications.csv`:
   ```csv
   pub007,Advanced ensemble methods for climate projection,Smith J. et al.,2024,Nature Reviews Climate,10.1038/nreview.2024.001,https://doi.org/10.1038/nreview.2024.001,Journal Article,ensemble uncertainty-quantification
   ```

2. **DOI Format**: Use format starting with `10.` (e.g., `10.1038/nclimate.2024.001`)

3. **Authors Format**: Use "surname initial: Brown J. et al." for articles with 3+ authors

4. **Tags**: Use dash-separated lowercase (no spaces, commas separate tags)

## Next: Publication Pages

Future implementation: `publications.html` would:
- Load `publications.csv` via Fetch API
- Display publications grouped by type
- Filter by methods, regions, or tags
- Generate links to DOI/URLs
- Show BibTeX citations

Example filtering:
```javascript
const aiPubs = publications.filter(p => p.tags.includes('machine-learning'));
const tokyoPubs = publications.filter(p => p.tags.includes('tokyo'));
```

## Citation Formats

Generate citations from CSV fields:
```
APA: Authors. Year. Title. Journal, DOI.
BibTeX: @article{id,
  title={Title},
  author={Authors},
  year={Year},
  journal={Journal},
  doi={DOI}
}
```

## Integration with Research Pages

Publications can be linked from:
- Method detail pages (show publications by lead researcher)
- Case study pages (show relevant regional studies)
- Team pages (show each member's publications)
- Dedicated publications page with search/filter

## Best Practices

1. **Use full DOI URLs**: https://doi.org/10.1038/nclimate.2024.001
2. **Keep author lists consistent**: Use "et al." for 3+ authors
3. **Tag comprehensively**: Allow multiple perspectives on same paper
4. **Update annually**: Add new HiClimaX publications as they're published
5. **Archive preprints**: Track when preprints become published articles

See existing publications for format examples.
