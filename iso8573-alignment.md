# ISO 8573 Alignment — Industrial Compressor Maintenance Documentation System

## Overview

ISO 8573-1 defines purity classes for compressed air contaminants: particulates, water (dewpoint), and oil.

## Purity Classes (per ISO 8573-1:2010)

| Class | Particulates | Water (PDP) | Oil |
|---|---|---|---|
| 0 | As specified; stricter than Class 1 | As specified | As specified |
| 1 | ≤ 20,000 particles (0.1–0.5 µm) per m³ | ≤ -70 °C | ≤ 0.01 mg/m³ |
| 2 | ≤ 400,000 particles (0.1–0.5 µm) per m³ | ≤ -40 °C | ≤ 0.1 mg/m³ |
| 3 | — | ≤ -20 °C | ≤ 1 mg/m³ |
| 4 | — | ≤ +3 °C | ≤ 5 mg/m³ |
| 5 | — | ≤ +7 °C | — |

## Typical Application Classes

| Application | Typical purity class (P/W/O) |
|---|---|
| General industrial air (pneumatic tools) | 4 / 4 / 4 or 3 / 4 / 4 |
| Instrument air | 2 / 3 / 2 |
| Food and beverage | 2 / 2 / 1 |
| Pharmaceutical | 1 / 2 / 1 |
| Electronics / semiconductor | 1 / 1 / 1 |

(P = particulates, W = water, O = oil. The three numbers specify the class for each contaminant.)

## Test Procedure

ISO 8573 testing requires sampling the compressed air at a defined test point after the dryer and filters. Tests are typically performed annually by a specialist contractor using calibrated equipment. The test report should specify:

- The test point location
- The purity class achieved for each contaminant
- The overall purity class achieved (the worst of the three)
- Comparison with the previous year's results
- Recommendations (e.g. filter replacement, dryer service) if classes have degraded

## This Framework's Alignment

The `air-quality-test.csv` template captures:

- `particle_class_achieved`
- `water_class_achieved`
- `oil_class_achieved`
- `overall_class_achieved`

These fields are populated from the test report. The framework does not perform the test; it records the results.
