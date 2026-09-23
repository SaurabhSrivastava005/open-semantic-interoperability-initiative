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
| [Reference architecture](docs/reference-architecture.md) | Defines components, trust boundaries and deployment modes |
| [Artifact contract](docs/artifact-contract.md) | Defines machine-readable records, lifecycle fields and validation rules |

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


## Operating model

The initiative operates through five linked workstreams.

| Workstream | Responsibility | Primary outputs |
|---|---|---|
| Standards and profile | Select and constrain existing standards | FHIR profiles, value sets and implementation decisions |
| Synthetic data | Create realistic, non-identifiable inputs | Source schemas, messages, FHIR examples and edge cases |
| Semantic assurance | Establish expected meaning | Mapping records, terminology decisions and reviewer approvals |
| Test and evidence | Execute reproducible evaluations | Assertions, test runs, measures, failures and evidence reports |
| Governance and adoption | Control claims and participation | Decision records, risk reviews, release gates and partner model |

No workstream may independently publish a clinical-validity claim. Evidence claims require the approvals defined in the governance document.

## End-to-end lifecycle

1. A use case and risk boundary are approved.
2. Applicable standards and terminology versions are pinned.
3. Synthetic clinical scenarios are designed.
4. Two source representations and one expected target representation are authored.
5. Structural, terminology and semantic assertions are written.
6. Clinical and terminology reviewers approve the expected meaning.
7. Deterministic transformations establish a baseline.
8. AI-assisted methods run against the same held-out cases.
9. Results are executed across the selected platforms.
10. Failures, disagreements and limitations are published.
11. The evidence maturity level is assigned.
12. A change to any dependency triggers impact review and regression testing.

## Planned repository structure

```text
healthcare-semantic-fidelity-benchmark/
├── README.md
├── docs/
├── registry/
│   ├── standards.yaml
│   ├── terminology-releases.yaml
│   └── implementations.yaml
├── profiles/
│   └── laboratory-results/
├── source-models/
│   ├── synthetic-lab-a/
│   └── synthetic-lab-b/
├── mappings/
├── fixtures/
│   ├── valid/
│   ├── invalid/
│   ├── ambiguous/
│   └── held-out/
├── tests/
├── evidence/
├── decisions/
└── tools/
```

Executable folders will be added only when their schemas, licences and review requirements are approved.

## Decision principles

- Reuse before creating.
- Use the minimum semantic scope required by the use case.
- Preserve original values and local codes.
- Record every material transformation.
- Prefer an unresolved mapping over a false exact match.
- Keep synthetic evidence distinct from production evidence.
- Publish negative findings.
- Make every reported result reproducible.


## How the initiative works in practice

The benchmark begins with a deliberately narrow question rather than a broad ambition to standardise healthcare. A laboratory result is selected because it looks simple at first glance, yet it exposes nearly every important semantic-interoperability problem. A result has a test identity, a value, a unit, a specimen, a method, a reference range, a status and a history. If any of these elements is changed or omitted, the receiving system may interpret the record differently even though the resulting FHIR resource passes technical validation.

For each scenario, the team creates two fictional laboratory systems that express the same intended event differently. One system may use a short local code and conventional units, while another uses a descriptive code and SI units. The benchmark does not assume that one source is better. It identifies the meaning each source is trying to communicate and defines a reviewed target representation. This makes it possible to test whether an integration tool, mapping method or AI assistant preserves that meaning.

The benchmark separates the creation of an answer from the testing of a product. Clinical and terminology reviewers approve the expected representation before any platform is scored. Test engineers then execute the same fixture against different implementations. This separation prevents a product-specific output from quietly becoming the definition of correctness.

The initial objective is not to certify a hospital integration. It is to produce an H3 evidence package showing that a published synthetic benchmark can be run across at least two implementations and produce reproducible results. That outcome would demonstrate that the SIEL method is executable. It would not demonstrate that the same mappings are safe for every laboratory or jurisdiction.

The initiative is intentionally open about failure. If two qualified reviewers disagree about a mapping, that disagreement becomes evidence. If a platform accepts an invalid resource, the result is recorded. If an AI system correctly refuses to map an ambiguous code, that abstention is treated as a positive outcome rather than a failure to automate. This approach is central to the initiative because false certainty is more dangerous than an explicitly unresolved case.
