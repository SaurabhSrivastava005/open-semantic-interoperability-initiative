# Healthcare Semantic Fidelity Benchmark

## Status

**Proposed SIEL initiative**

This initiative creates an open, vendor-neutral benchmark for determining whether healthcare data transformations preserve clinically material meaning.

The first use case is laboratory-result interoperability using synthetic data.

## Problem statement

Healthcare platforms can produce technically valid HL7 FHIR resources while still changing or losing important meaning.

Examples include:

- selecting the wrong LOINC code;
- converting a value into the wrong unit;
- losing specimen context;
- changing a preliminary result into a final result;
- failing to preserve corrected-result history;
- attaching the wrong reference range;
- misinterpreting local abnormal flags; and
- losing transformation provenance.

Structural conformance is necessary, but it is not sufficient evidence of semantic fidelity.

## Initiative hypothesis

> Two independently structured laboratory systems can exchange equivalent results through a minimal FHIR profile with no unrecorded semantic loss.

## What SIEL will build

SIEL will publish:

- two synthetic laboratory source models;
- synthetic HL7 Version 2 and FHIR test fixtures;
- expected FHIR R4 outputs;
- reviewed LOINC and UCUM mappings;
- difficult semantic edge cases;
- deterministic mapping baselines;
- AI-assisted mapping experiments;
- reusable conformance and semantic tests;
- cross-platform evidence; and
- transparent reports of successful, failed and unresolved cases.

## What SIEL will not build

This initiative will not create:

- another FHIR server;
- another generic integration engine;
- another terminology server;
- another electronic health record;
- another laboratory information system;
- a diagnosis or treatment system;
- a production clinical decision-support system; or
- a replacement for HL7, FHIR, LOINC, UCUM, SNOMED CT or OMOP.

## Safety boundary

This initiative evaluates data interoperability. It does not diagnose patients, recommend treatment, determine clinical significance or replace clinical review.

The initial releases will use synthetic data only. No identifiable patient information is permitted in the public repository.

Clinical terminology mappings and expected clinical meaning must be reviewed by appropriately qualified experts before they are described as validated.

## Documentation

| Document | Purpose |
|---|---|
| [Problem and scope](docs/problem-and-scope.md) | Defines the problem, users, outcomes and boundaries |
| [Market landscape](docs/market-landscape.md) | Explains existing solutions and the non-duplication boundary |
| [Benchmark design](docs/benchmark-design.md) | Defines test systems, standards, scenarios and measures |
| [Synthetic data strategy](docs/synthetic-data-strategy.md) | Explains how the initiative operates without organisational data |
| [Evidence maturity model](docs/evidence-maturity.md) | Separates synthetic evidence from production evidence |
| [Delivery plan](docs/delivery-plan.md) | Defines work packages, roles, releases and acceptance criteria |
| [Governance and risk](docs/governance-and-risk.md) | Defines safety, authority, privacy, licensing and publication controls |

## First release target

The initial release should contain:

- 20 common laboratory test types;
- two synthetic source systems;
- 100 to 200 synthetic results;
- at least 20 difficult edge cases;
- FHIR R4 Observation, DiagnosticReport, Specimen and Patient resources;
- LOINC and UCUM terminology;
- deterministic and AI-assisted mapping comparisons;
- HAPI FHIR testing plus one managed FHIR implementation;
- complete transformation provenance; and
- a published evidence report.

## Relationship to SIEL

This initiative is an implementation of the SIEL method:

1. select a bounded industry problem;
2. reuse established standards;
3. define the minimum shared meaning;
4. create reproducible test fixtures;
5. separate AI proposals from accountable approval;
6. test multiple implementations;
7. measure semantic loss; and
8. publish evidence and limitations.
