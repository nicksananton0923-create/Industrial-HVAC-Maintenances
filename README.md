# Industrial Compressor Maintenance Documentation System

## Table of Contents
1. [Project Purpose](#1-project-purpose)
2. [Problem Statement](#2-problem-statement)
3. [Project Objectives](#3-project-objectives)
4. [Current Project Status](#4-current-project-status)
5. [Confirmed Technologies and Components](#5-confirmed-technologies-and-components)
6. [Proposed Components](#6-proposed-components)
7. [System Operation](#7-system-operation)
8. [Architecture or Workflow](#8-architecture-or-workflow)
9. [Installation or Setup Instructions](#9-installation-or-setup-instructions)
10. [Testing Status](#10-testing-status)
11. [Safety Considerations](#11-safety-considerations)
12. [Known Limitations](#12-known-limitations)
13. [Future Improvements](#13-future-improvements)
14. [Repository Structure](#14-repository-structure)
15. [Licence Information](#15-licence-information)
16. [Status Label Convention](#16-status-label-convention)

## 1. Project Purpose

This project provides a vendor-neutral documentation framework for the maintenance of industrial air compressors (rotary screw, reciprocating, and centrifugal). The framework covers asset registration, daily / weekly / monthly / quarterly / annual inspection checklists, oil and filter service records, air quality test records, and corrective action logs. The package includes CSV templates, a fictional sample dataset, and procedural documentation aligned with ISO 8573 (compressed air quality) and OEM-recommended service intervals.

## 2. Problem Statement

Industrial compressed air systems are critical to many manufacturing processes, and compressor downtime can stop production across multiple plant areas. Compressor maintenance requires regular oil and filter changes, valve inspections, intercooler cleaning, and air quality testing. Without a consistent documentation framework, maintenance records end up in paper logbooks that are difficult to search and audit. A vendor-neutral CSV-based framework makes the records searchable, auditable, and portable across CMMS platforms.

## 3. Project Objectives

- Provide vendor-neutral CSV templates for compressor assets and inspections.
- Provide inspection checklists aligned with OEM-recommended intervals.
- Provide oil and filter service record templates.
- Provide air quality test record templates aligned with ISO 8573.
- Provide a fictional sample dataset for demonstration.
- Provide procedural documentation for compressor maintenance.
- Clearly label all data as FICTIONAL.

## 4. Current Project Status

| Item | Status |
|---|---|
| CSV templates | IMPLEMENTED |
| Sample dataset (fictional) | IMPLEMENTED |
| Procedural documentation (ISO 8573 aligned) | IMPLEMENTED |
| Deployment in a real plant | NOT VERIFIED |
| Integration with a CMMS | NOT YET TESTED |

## 5. Confirmed Technologies and Components

CSV data format, Markdown documentation, ISO 8573 reference.

## 6. Proposed Components

| Component | Role | Notes |
|---|---|---|
| CSV editor | Template population | Any |
| CMMS (optional) | Production deployment | e.g. Maximo, SAP PM |
| Air quality test kit | ISO 8573 testing | e.g. compressor air particle/oil/dewpoint test kit |

## 7. System Operation

The framework operates as a set of interlinked CSV files with the compressor asset register at the centre. Each compressor has a unique ID that links to its inspection schedule, service records, air quality test records, and corrective action log. The inspection schedule lists every required inspection with its frequency, last-completed date, and next-due date. The service records capture oil and filter changes. The air quality test records capture ISO 8573 results (particle count, oil content, dewpoint).

## 8. Architecture or Workflow

Star schema with the compressor asset register at the centre, linked by `asset_id`.

```
             [inspection-checklist.csv]
                       |
                       v
  [oil-filter-service.csv] --> [asset-register.csv] <-- [air-quality-test.csv]
                                       ^
                                       |
                            [corrective-action-log.csv]
```


## 9. Installation or Setup Instructions

1. Copy templates from `templates/` to a working directory.
2. Populate `asset-register.csv` with the plant's compressors.
3. For each compressor, populate the inspection schedule.
4. Perform inspections per the schedule and record results.
5. Perform oil and filter changes per the schedule and record in the service record.
6. Perform ISO 8573 air quality tests per the schedule (typically annually) and record results.
7. Log any deficiencies in the corrective action log.

## 10. Testing Status

All tests are currently **NOT YET TESTED** on a real plant. Tests performed on the fictional sample:

1. CSV schema validation — TESTED — passes.
2. Cross-file referential integrity — TESTED — passes.
3. Inspection schedule completeness vs OEM typical intervals — TESTED.
4. Real plant deployment — NOT YET TESTED.

## 11. Safety Considerations

Compressor maintenance involves several safety hazards:

- **Stored pressure.** Compressors and air receivers store compressed air that can cause serious injury if released suddenly. Isolate and vent the system before any maintenance. Verify zero pressure with a gauge before opening any connection.
- **High temperature.** Compressor oil and air can reach 100 °C+. Allow the unit to cool before maintenance. Wear heat-resistant gloves.
- **Electrical hazard.** Compressor motors are typically 3-phase mains. Apply lockout-tagout before any electrical work.
- **Rotating parts.** Compressor airends and cooling fans have rotating parts that can entangle clothing. Ensure guards are in place.
- **Oil hazard.** Compressor oil is slippery and is an environmental hazard if spilled. Use drip trays and dispose of used oil at a designated recycling point.
- **Air receiver inspection** is regulated in most jurisdictions (e.g. Pressure Equipment Directive in EU, ASME Section VIII in US). Inspections must be performed by an authorised inspector at the required intervals (typically 1, 2, or 5 years depending on jurisdiction).

This framework is **not a substitute for the OEM manual**. Always refer to the OEM manual for the specific compressor before any maintenance task.

## 12. Known Limitations

- Documentation only — does not perform inspections.
- No CMMS integration.
- Aligned with ISO 8573; local regulations may require additional record types.
- Does not include air receiver inspection records (jurisdiction-specific).
- Does not include spare parts inventory linkage.
- Does not include energy efficiency analysis (covered separately in Project 17).

## 13. Future Improvements

- Add equipment-class-specific inspection checklists (rotary screw, reciprocating, centrifugal).
- Add air receiver inspection records (per local PED / ASME equivalent).
- Add a CMMS migration guide.
- Add energy efficiency analysis (kW per m³/min, leak detection).
- Add leak detection survey template.

## 14. Repository Structure

```
11-compressor-maintenance-documentation/
├── README.md
├── LICENSE
├── docs/
│   ├── project-overview.md
│   ├── requirements.md
│   ├── system-architecture.md
│   ├── logic-and-operation.md
│   ├── components-and-bill-of-materials.md
│   ├── testing-and-validation.md
│   ├── safety-considerations.md
│   ├── development-roadmap.md
│   └── limitations.md
├── templates/
│   ├── asset-register.csv
│   ├── inspection-checklist.csv
│   ├── oil-filter-service.csv
│   ├── air-quality-test.csv
│   └── corrective-action-log.csv
├── data/
│   ├── sample-asset-register.csv
│   └── sample-service-records.csv
└── procedures/
    ├── iso8573-alignment.md
    └── maintenance-intervals.md
```

## 15. Licence Information

Released under the MIT Licence. See the `LICENSE` file for the full text.

## 16. Status Label Convention

This project uses the following status labels throughout its documentation. Each label has a strict meaning and is not used interchangeably with any other label.

| Label | Meaning |
|---|---|
| **CONFIRMED** | Directly supported by available project information or inspected source code. |
| **PROPOSED** | A suggested design or implementation. Has not been verified against built hardware. |
| **NOT VERIFIED** | Information that has not been confirmed. Requires verification before use. |
| **IMPLEMENTED** | A feature or system that has actually been created and exists in the source code. |
| **TESTED** | A test that has genuinely been performed with recorded results. |
| **NOT YET TESTED** | Code, hardware, or functionality that still requires testing. |

If a section does not carry any status label, the content of that section is informational prose and does not make a claim of verification, testing, or implementation.

## Data and Confidentiality Notice

All sample data in this repository is **FICTIONAL**. Plant names use generic identifiers such as "Plant A", "Building 3", "Line 2", or "Western Plant". No real employer name, real equipment serial number, real employee name, real maintenance record, or any other confidential information is included. Templates are provided as reusable CSV schemas that can be populated with real site data by the adopting organisation. The fictional data is intended solely to demonstrate the template structure and calculation methodology.
