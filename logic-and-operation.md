# Logic and Operation — Industrial Compressor Maintenance Documentation System

## Inspection Intervals (OEM-Typical)

| Inspection / test | Frequency |
|---|---|
| Visual inspection (oil level, leaks, unusual noise) | Daily |
| Air filter inspection | Weekly |
| Oil level check | Weekly |
| Cooler cleaning | Monthly |
| Oil sample | Quarterly |
| Oil and filter change | 4000–8000 running hours |
| Air quality test (ISO 8573) | Annually |
| Valve inspection | Annually |
| Major overhaul | Per OEM (typically 24,000–48,000 hours) |

(These are typical OEM intervals; verify against the specific compressor's OEM manual.)

## ISO 8573 Air Quality Test

ISO 8573-1 defines purity classes for three contaminant types:

- **Particulates** (size and count per m³)
- **Water / dewpoint** (pressure dewpoint temperature)
- **Oil** (total oil content per m³)

Common purity classes used in industry:

| Class | Particulates (per m³) | Water (PDP °C) | Oil (mg/m³) |
|---|---|---|---|
| 1 | ≤ 20,000 (0.1–0.5 µm) | ≤ -70 | ≤ 0.01 |
| 2 | ≤ 400,000 (0.1–0.5 µm) | ≤ -40 | ≤ 0.1 |
| 3 | — | ≤ -20 | ≤ 1 |
| 4 | — | ≤ +3 | ≤ 5 |

Typical industrial applications require Class 2 or 3; food, pharmaceutical, and electronics applications require Class 1.

## Service Record Logic

Each oil and filter service record captures:
- Service date and run-hours at service
- Oil type and quantity
- Filter part numbers changed (air filter, oil filter, separator)
- Service technician
- Next due run-hours
- Notes (oil sample result, unusual wear, etc.)
