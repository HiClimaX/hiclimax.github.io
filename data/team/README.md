# Team Members (`data/team/`)

Centralized storage for team member information and photos.

## Structure
```
data/team/
├── members.csv       # Team member data (names, roles, photos, socials)
├── photos/           # Directory for headshot photos
└── README.md         # This file
```

## CSV Columns

| Column | Required | Format | Example |
|--------|----------|--------|---------|
| **name** | Yes | Full name | "Dr. Sarah Chen" |
| **role** | Yes | Job title | "Lead Architect" |
| **affiliation** | Yes | Organization · Institute · Country | "ETH Zurich · Switzerland" |
| **category** | Yes | core, method, regional, engineering | "core" |
| **emoji** | No | Unicode emoji | "👩‍💻" |
| **photo** | No | Path to image | "data/team/photos/sarah-chen.jpg" |
| **github** | No | Full GitHub URL | "https://github.com/username" |
| **email** | No | Email address | "sarah.chen@ethz.ch" |
| **orcid** | No | Full ORCID URL | "https://orcid.org/0000-0000-0000-0000" |

## Valid Categories

- **core**: Principal investigators and core leadership (3-5 people)
- **method**: Lead researchers for each downscaling method (4-6 people)
- **regional**: Regional coordinators for case study cities (3-4 people)
- **engineering**: Software engineers, data managers, community staff (4-5 people)

## Adding Team Members

### Option A: Markdown (new)
1. Open `data/team/members.md` in any text editor
2. Add a member block with key/value fields separated by `---`
3. Required keys: `name`, `role`, `affiliation`, `category`
4. Optional keys: `emoji`, `photo`, `github`, `email`, `orcid`

Example:

```
---
name: Dr. Jane Doe
role: Senior Researcher
affiliation: Climate Research Lab · UC Berkeley · USA
category: core
emoji: 👩‍🔬
photo: data/team/photos/jane-doe.jpg
github: https://github.com/janedoe
email: jane.doe@berkeley.edu
orcid: https://orcid.org/0000-0001-2345-6789
---
```

### Option B: CSV (existing)
1. Open `data/team/members.csv` in any text editor or spreadsheet application
2. Add a new row with required information (name, role, affiliation, category)
3. Optionally:
   - Add an emoji for visual distinction
   - Create/upload a photo to `data/team/photos/` (JPG, PNG, or WebP)
   - Update photo column with relative path: `data/team/photos/firstname-lastname.jpg`
   - Add GitHub, email, and ORCID links

## Adding Photos

1. **Size & Format**: 300-500px square headshots, JPG or PNG
2. **Naming**: Use kebab-case matching member name (e.g., `sarah-chen.jpg`)
3. **Location**: Place in `data/team/photos/` folder
4. **Reference**: Update CSV photo column with exact path: `data/team/photos/sarah-chen.jpg`
5. **Fallback**: If photo missing or broken, displays emoji from CSV

## Example Entry

```csv
Dr. Jane Doe,Senior Researcher,Climate Research Lab · UC Berkeley · USA,core,👩‍🔬,data/team/photos/jane-doe.jpg,https://github.com/janedoe,jane.doe@berkeley.edu,https://orcid.org/0000-0001-2345-6789
```

## Fallback Behavior

- **Missing emoji?** Shows default avatar 👤
- **Missing photo?** Shows emoji instead (graceful degradation)
- **Empty email/github/orcid?** Links won't display (field is hidden)
- **Invalid CSV?** Page shows demo data with 6 sample members

## CSV Tips

- Use commas (,) to separate columns
- Wrap values with commas in quotes: `"Doe, Jane"`
- No spaces after commas between columns
- Keep one member per line
- Use UTF-8 encoding to preserve emoji

See `team.html` source code for rendering logic and demo data fallback.
