# OpenPlanning

OpenPlanning is an open data standard for municipal planning records: meetings, applications, zoning districts, governing documents, and the references between them.

This repository holds two things:

- `specs/`: JSON Schema definitions, one per entity, versioned as `<entity>/v1.json`.
- `data/`: example records that conform to the specs, organized as `data/<country>/<state>/<county>/<municipality>/`.

## Specs

| Spec | Describes |
|------|-----------|
| `municipality` | The town or county that owns the records |
| `jurisdiction` | A review body, such as a planning commission or state agency |
| `meeting` | A public meeting and its agenda items |
| `document` | A source document, such as an agenda, staff report, or minutes |
| `document_references` | Links from a document to the entities it mentions |
| `application` | A land use application under review |
| `project` | A development that spans one or more applications |
| `parcel` | A tax parcel |
| `zoning_district` | A zoning district and its code |
| `legal_document` | A governing document, such as a zoning code, as a section tree |
| `governing_documents` | The set of governing documents for a jurisdiction |
| `review_process` | The steps an application moves through |
| `resolution` | An adopted resolution |
| `staff_report` | A staff report and its recommendation |
| `entity` | A person or organization that appears in the records |
| `manifest` | The load order for a directory of records |

## Example data: Sykesville, Maryland

`data/usa/maryland/carrollcounty/sykesville/` holds Planning Commission records for the Town of Sykesville from 2023 to 2026. The records come from public documents on the town website. Each record links to its source with a `source_url`.

`manifest.json` lists the load order. `manifest_late.json` lists files that depend on the first pass.

## Not included

- **The full parcel layer.** The Sykesville parcel geometry and ownership data come from a licensed provider and cannot be redistributed. `parcels_supplementary.json` holds the parcels the planning records name directly.

## License

Apache License 2.0. See `LICENSE`.
