# System Architecture — Industrial Compressor Maintenance Documentation System

## Data Model

Star schema with the compressor asset register at the centre.

### Master file
- `asset-register.csv`

### Transaction files
- `inspection-checklist.csv`
- `oil-filter-service.csv`
- `air-quality-test.csv`
- `corrective-action-log.csv`

## Standards Alignment

- ISO 8573-1 (compressed air — contaminants and purity classes)
- OEM service manuals (vendor-specific)
