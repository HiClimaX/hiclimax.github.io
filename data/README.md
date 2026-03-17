# HiClimaX Data Structure

Centralized, scalable data management for all website content. Each content type has its own folder with CSV data and supporting assets.

## Directory Overview

```
data/
├── team/                    # Team member information
│   ├── members.csv         # 16 team members with roles, affiliations, photos
│   ├── photos/             # Headshot photos (JPG/PNG)
│   └── README.md           # Team documentation & guidelines
│
├── case_studies/           # Regional case study demonstrations
│   ├── cases.csv           # Tokyo, Ho Chi Minh City, Brussels + future cities
│   ├── assets/             # City photos, climate maps, visualizations
│   └── README.md           # Case study documentation & expansion guide
│
├── datasets/               # Publicly available climate downscaling datasets
│   ├── datasets.csv        # 12+ datasets with metadata and access info
│   ├── previews/           # Dataset preview images and visualizations
│   └── README.md           # Dataset catalog and access guide
│
├── methods/                # HiClimaX downscaling methodologies
│   ├── methods.csv         # 6 methods (D-DS, PGW, SD-DS, LSP, SDS, AI-DS)
│   └── README.md           # Method descriptions & comparison matrix
│
├── publications/           # Research publications & references
│   ├── publications.csv    # 6+ peer-reviewed articles and data papers
│   └── README.md           # Publication tracking & citation guidance
│
├── partners/               # Collaborating institutions
│   ├── partners.csv        # 8+ universities and research organizations
│   ├── logos/              # Organization logos (SVG/PNG)
│   └── README.md           # Partnership information & collaboration framework
│
└── README.md               # This file
```

## Quick Start

### Adding Team Members
1. Open [data/team/members.csv](team/README.md#adding-team-members)
2. Add row with: name, role, affiliation, category
3. Optionally add photo path and contact links
4. Photos go in `data/team/photos/`

See [data/team/README.md](team/README.md) for all options.

### Adding Case Studies
1. Open [data/case_studies/cases.csv](case_studies/README.md#adding-a-new-case-study)
2. Create entry with city, region, climate context, and metrics
3. Add assets (photos, maps) to `data/case_studies/assets/`
4. Link from relevant pages

See [data/case_studies/README.md](case_studies/README.md) for guidelines.

### Adding Datasets
1. Open [data/datasets/datasets.csv](datasets/README.md#adding-new-datasets)
2. Create entry with dataset name, domain, methods, resolution, and access URL
3. Add preview images (maps, charts) to `data/datasets/previews/`
4. Register DOI with Zenodo for proper citation

See [data/datasets/README.md](datasets/README.md) for guidelines. View all datasets at [datasets.html](../datasets.html).

### Adding Publications
1. Open [data/publications/publications.csv](publications/README.md#adding-publications)
2. Add research article with DOI and publication metadata
3. Tag with relevant keywords for filtering

See [data/publications/README.md](publications/README.md) for format.

### Adding Partners
1. Open [data/partners/partners.csv](partners/README.md#adding-new-partners)
2. Create entry with organization info and focus areas
3. Upload logo to `data/partners/logos/`

See [data/partners/README.md](partners/README.md) for guidelines.

## By The Numbers

### Current Content
| Type | Count | Example |
|------|-------|---------|
| **Team Members** | 16 | Doan Van Giang (Core), Dr. Marco Bianchi (Method Lead) |
| **Case Studies** | 3 | Tokyo, Ho Chi Minh City, Brussels |
| **Datasets** | 12 | Tokyo Dynamical, HCMC PGW, Global Ensemble |
| **Methods** | 6 | Dynamical, PGW, Statistical-Dynamical, LSP, SDS, AI-based |
| **Publications** | 6 | Nature Climate Change, GeoSci Model Dev, others |
| **Partners** | 8 | Universities, max-planck, meteorological institutes |

### Growing Capacity
- **Team Scaling**: Add members to any category (core, method, regional, engineering)
- **Case Study Expansion**: Framework ready for 10+ cities with regional climate data
- **Method Documentation**: Each method can have detailed technical subdirectories
- **Publication Archive**: No practical limit - scalable for hundreds of articles
- **Partner Network**: Interstate/international collaboration ready to add 20+ more institutions

## Data Format Standards

### CSV Best Practices
- **Encoding**: UTF-8 (preserves emoji and international characters)
- **Delimiters**: Commas (,) for columns, no spaces after commas
- **Quoting**: Wrap values with commas in quotes: `"Doe, Jane"`
- **Special Chars**: Use emoji freely, avoid raw newlines in fields
- **Header**: First row must be column names (name, role, affiliation, etc.)

### File Naming Conventions
- **CSVs**: Singular noun (members.csv, cases.csv, methods.csv, publications.csv, partners.csv)
- **Assets**: Kebab-case matching ID (sarah-chen.jpg, tokyo-skyline.jpg)
- **Directories**: Plural nouns (photos/, assets/, logos/)
- **Docs**: Always README.md in each section

### Path References
- **In HTML/JS**: Use relative paths (`data/team/members.csv`)
- **In CSVs**: Use relative paths (`data/team/photos/sarah-chen.jpg`)
- **Absolute paths**: Never use absolute file paths - breaks on deployment

## Page Integration Patterns

Each page loads data dynamically:

```javascript
// Pattern used in team.html and can scale to other pages
async function loadContentData(dataPath) {
  try {
    const response = await fetch(dataPath);
    const text = await response.text();
    const data = parseCSV(text);
    console.log(`✅ Loaded ${data.length} items from ${dataPath}`);
    return data;
  } catch (error) {
    console.warn(`⚠️ Failed to load ${dataPath}`, error.message);
    return getDemoData(); // Fallback
  }
}

// Usage
const team = await loadContentData('data/team/members.csv');
const cases = await loadContentData('data/case_studies/cases.csv');
const publications = await loadContentData('data/publications/publications.csv');
```

## Planned Pages

| Page | Data Source | Status |
|------|-------------|--------|
| `team.html` | data/team/members.csv | ✅ Live |
| `datasets.html` | data/datasets/datasets.csv | ✅ Live |
| `case-studies.html` | data/case_studies/cases.csv | 📋 Planned |
| `methods.html` | data/methods/methods.csv | 📋 Planned |
| `publications.html` | data/publications/publications.csv | 📋 Planned |
| `partnerships.html` | data/partners/partners.csv | 📋 Planned |

## Data Quality Checklist

Before committing changes:

- [ ] All required CSV columns filled (id, name, title, etc.)
- [ ] No trailing whitespace in cells
- [ ] File paths are relative and use forward slashes (/)
- [ ] Photo/asset files exist at referenced paths
- [ ] External URLs (github, orcid, website) are valid HTTP/HTTPS
- [ ] Emoji display correctly (use UTF-8 encoding)
- [ ] Empty fields handled gracefully (renderer skips null/empty)
- [ ] No duplicate IDs across rows

## Troubleshooting

### CSV Not Loading?
- **Check 1**: Server is running (file:// protocol doesn't work with Fetch)
- **Check 2**: Path is correct relative to HTML file location
- **Check 3**: File has .csv extension and UTF-8 encoding
- **Check 4**: No BOM (Byte Order Mark) at file start

### Photos Not Showing?
- **Check 1**: File exists at path in CSV (data/team/photos/name.jpg)
- **Check 2**: File format is JPG, PNG, or WebP
- **Check 3**: Filename matches exactly (case-sensitive on Unix/Mac)
- **Check 4**: Image error handler falls back to emoji ✅

### Styling Issues?
- All styling in [styles.css](../styles.css)
- Uses CSS Grid and Flexbox for responsiveness
- Mobile breakpoints: 900px and 600px
- Animation via Intersection Observer API (scroll-triggered fade-in)

## Contact & Governance

Each data directory has a README with specific guidelines and contact info:
- **Team addition**: See [data/team/README.md](team/README.md)
- **Case study partnership**: See [data/case_studies/README.md](case_studies/README.md)
- **Methods contribution**: See [data/methods/README.md](methods/README.md)
- **Publication archive**: See [data/publications/README.md](publications/README.md)
- **Organization collaboration**: See [data/partners/README.md](partners/README.md)

## Migration Notes

**From Old Structure**:
- Old path: `team/data/members.csv` → New path: `data/team/members.csv`
- Old path: `team/photos/` → New path: `data/team/photos/`
- All references updated in JavaScript loaders
- Old `team/` folder can be removed after verification

**Version Independence**:
- Each CSV is versioned in git (track changes)
- Can maintain `methods-v1.csv`, `methods-v2.csv` if needed
- No database migrations required - just update CSV files

## Future Enhancements

### Planned Features
- [ ] Full-text search across publications
- [ ] Interactive map of team members by institution
- [ ] Case study timeline visualization
- [ ] Method selection wizard (guide researchers to appropriate approach)
- [ ] Publication filtering by tag/topic/year
- [ ] Team member profile pages (individual researcher pages)

### Infrastructure
- [ ] Database migration (PostgreSQL) for larger datasets
- [ ] API endpoints for third-party integrations
- [ ] CMS interface for non-technical content updates
- [ ] Automated publication harvesting from digital repositories
- [ ] Image optimization and CDN delivery

---

**Last Updated**: March 2026  
**Maintained By**: HiClimaX Technical Team  
**Questions?**: See individual README files in each data subdirectory
