# Equatorial Guinea Administrative Divisions / Guinea Ecuatorial



## Overview

| Item | Details |
|------|---------|
| Province | 7 |
| District | 32 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-06-01 |
| Website | [openadmindata.org/gq](https://openadmindata.org/gq/) |
| API | [openadmindata.org/api/gq](https://openadmindata.org/api/gq/) |

## Browse by Province

| # | Province | Districts | Link |
|---|----|----|------|
| 1 | Annobón | 2 | [Browse](divisions/annobn-gq198/) |
| 2 | Bioko Norte | 3 | [Browse](divisions/bioko-norte-gq199/) |
| 3 | Bioko Sur | 2 | [Browse](divisions/bioko-sur-gq200/) |
| 4 | Centro Sur | 5 | [Browse](divisions/centro-sur-gq201/) |
| 5 | Kié-Ntem | 6 | [Browse](divisions/ki-ntem-gq202/) |
| 6 | Litoral | 7 | [Browse](divisions/litoral-gq203/) |
| 7 | Wele-Nzas | 7 | [Browse](divisions/wele-nzas-gq204/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-province.json](data/all-province.json) | JSON | All 7 province records |
| [all-district.json](data/all-district.json) | JSON | All 32 district records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-1 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-province.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['district']} districts")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-province.json", "utf-8"));
console.log(`Total: ${data.length} provinces`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=province, 2=district |
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
divisions/{province-slug}/
```

Districts are listed inline in each province's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-province links
- [Per-province data](docs/llms-full/) — Full data by province

## Citation

```
Equatorial Guinea Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/equatorial-guinea-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [Open Admin Data](https://openadmindata.org) — Browse, search and explore administrative divisions for every country
- [open-admin-data](https://github.com/open-admin-data) — GitHub organization with all country repos
- [ListBase](https://www.listbase.org) — Structured reference data for every country
