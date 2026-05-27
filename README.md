# Uganda Administrative Divisions / Uganda



## Overview

| Item | Details |
|------|---------|
| Region | 4 |
| District | 135 |
| County | 203 |
| Sub-county | 1,520 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-05-27 |

## Browse by Region

| # | Region | Districts | Countys | Sub-countys | Link |
|---|----|----|----|----|------|
| 1 | Central | 26 | 47 | 268 | [Browse](divisions/central-ug1/) |
| 2 | Eastern | 37 | 54 | 454 | [Browse](divisions/eastern-ug2/) |
| 3 | Northern | 37 | 48 | 339 | [Browse](divisions/northern-ug3/) |
| 4 | Western | 35 | 54 | 459 | [Browse](divisions/western-ug4/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-region.json](data/all-region.json) | JSON | All 4 region records |
| [all-district.json](data/all-district.json) | JSON | All 135 district records |
| [all-county.json](data/all-county.json) | JSON | All 203 county records |
| [all-subcounty.json](data/all-subcounty.json) | JSON | All 1,520 sub-county records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-3 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-region.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['district']} districts")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-region.json", "utf-8"));
console.log(`Total: ${data.length} regions`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=region, 2=district, 3=county, 4=sub-county |
| `level_name` | object | Level label (local + English) |
| `name.local` | string | Name in local script |
| `name.en` | string | English name |
| `name.slug` | string | URL-safe slug |
| `parent` | object/null | Parent division reference |
| `ancestors` | array | Full ancestor chain |
| `children_count` | object | Count of children per level |
| `zip_codes` | array | Postal codes (where available) |
| `geo.lat` | string | Latitude (WGS84) |
| `geo.lon` | string | Longitude (WGS84) |

Full schema: [data/schema.json](data/schema.json)

## Hierarchy Browse

```
divisions/{region-slug}/
divisions/{region-slug}/{district-slug}/
divisions/{region-slug}/{district-slug}/{county-slug}/
```

Sub-countys are listed inline in each county's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-region links
- [Per-region data](docs/llms-full/) — Full data by region

## Citation

```
Uganda Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/uganda-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [ListBase](https://www.listbase.org) — Structured reference data for every country
- [open-admin-data](https://github.com/open-admin-data) — Open administrative data for ASEAN countries
- [thailand-administrative-divisions](https://github.com/open-admin-data/thailand-administrative-divisions) — Thailand dataset
