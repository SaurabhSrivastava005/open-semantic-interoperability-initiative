# Laboratory Results Benchmark Design

## Benchmark question

Can two independently structured laboratory systems produce semantically equivalent FHIR results without unrecorded information loss?

## Synthetic source systems

### Synthetic Laboratory A

Represents a hospital laboratory using:

- compact local test codes;
- HL7 Version 2 messages;
- mg/dL units for selected tests;
- single-character status and abnormal flags;
- panel-based result grouping; and
- local specimen identifiers.

### Synthetic Laboratory B

Represents an independent laboratory using:

- different local codes;
- alternative display names;
- mmol/L or other SI units where appropriate;
- descriptive status values;
- separate order and result structures; and
- different reference-range conventions.

## Target FHIR R4 resources

- Patient
- Organization
- Practitioner
- ServiceRequest
- Specimen
- Observation
- DiagnosticReport
- Provenance
- Consent, when a permitted-use scenario requires it

The first release may use only the minimum subset needed for the selected scenarios.

## Terminology

| Source | Purpose |
|---|---|
| LOINC | Identification of laboratory tests and observations |
| UCUM | Units of measure |
| SNOMED CT | Selected clinical and specimen concepts where permitted |
| FHIR code systems | Resource status and administrative concepts |
| Local synthetic code systems | Source-system variation |

## Scenario classes

### Standard cases

- single numeric result;
- qualitative result;
- laboratory panel;
- normal result;
- abnormal result; and
- result with a reference range.

### Transformation cases

- mg/dL to mmol/L conversion;
- local code to LOINC mapping;
- local unit label to UCUM representation;
- panel-to-atomic-result decomposition; and
- local status to FHIR status mapping.

### Difficult cases

- corrected result that supersedes an earlier result;
- preliminary microbiology result;
- same test name with different specimen;
- same test code with changed method;
- age-specific reference range;
- sex-specific reference range;
- incompatible unit;
- missing collection time;
- result value with excessive precision;
- qualitative result represented in a numeric field;
- ambiguous local test label;
- duplicate message;
- conflicting abnormal flag and reference range;
- terminology-version change;
- missing provenance;
- unsupported source field;
- result received out of sequence;
- cancelled order with a reported result;
- amended report with unchanged observation; and
- deliberately incorrect LOINC mapping.

## Mapping record

Every mapping should record:

- source system;
- source field or code;
- target element or concept;
- mapping type;
- transformation expression;
- terminology version;
- confidence;
- evidence;
- reviewer;
- approval status;
- effective date;
- limitations; and
- reversibility.

## Measures

### Structural measures

- profile validation pass rate;
- required-element completeness;
- resolvable-reference rate; and
- terminology-binding conformance.

### Semantic measures

- exact mapping accuracy;
- clinically material error rate;
- unit-conversion accuracy;
- status-preservation rate;
- reference-range preservation;
- specimen-context preservation;
- provenance completeness; and
- unrecorded semantic-loss rate.

### AI measures

- top-one accuracy;
- top-three candidate accuracy;
- dangerous false-equivalence rate;
- reviewer correction rate;
- confidence calibration;
- unresolved-case recognition; and
- review time compared with the deterministic baseline.

### Portability measures

- acceptance by each FHIR implementation;
- consistent search results;
- consistent validation outcomes;
- retained round-trip meaning; and
- implementation-specific deviations.

## Minimum acceptance criteria

The first release must:

- reject known dangerous mappings;
- preserve original values and local codes;
- record every non-trivial transformation;
- distinguish preliminary, final, amended and corrected results;
- identify unresolved mappings instead of forcing equivalence;
- contain no real patient data; and
- publish failures and limitations with successful results.

Numerical safety thresholds must be approved by the initiative's clinical and terminology reviewers before they are treated as release gates.


## Artifact model

Each scenario is a versioned package.

```text
scenario/
├── scenario.yaml
├── source-a/
│   └── message.hl7
├── source-b/
│   └── record.json
├── expected/
│   ├── bundle.json
│   └── assertions.yaml
├── mappings/
│   └── mapping-records.yaml
├── reviews/
│   ├── terminology-review.yaml
│   └── clinical-review.yaml
└── README.md
```

### Scenario manifest

The manifest should include:

- identifier and title;
- clinical intent;
- difficulty class;
- applicable standards;
- source and target versions;
- terminology releases;
- preconditions;
- expected transformations;
- known ambiguity;
- privacy classification;
- licence;
- reviewer requirements; and
- evidence maturity.

## Assertion taxonomy

| Assertion type | Example |
|---|---|
| Presence | Observation must include status and code |
| Cardinality | DiagnosticReport must reference at least one result |
| Terminology | Observation code must belong to the approved value set |
| Equality | Original source value must be retained |
| Conversion | Converted value must satisfy the approved formula and tolerance |
| Relationship | DiagnosticReport result must reference the intended Observation |
| Temporal | Effective time must not be replaced by ingestion time |
| Status | Corrected source result must not become final without amendment context |
| Provenance | Transformation agent and source entity must be recorded |
| Prohibition | Ambiguous mapping must not be emitted as an exact match |
| Round trip | Required meaning must survive target-to-neutral reconstruction |

## Ground-truth process

1. A scenario author proposes the source and expected target.
2. A terminology reviewer evaluates codes, value sets and versions.
3. A laboratory reviewer evaluates test, specimen, method, value and reference range.
4. A technical reviewer evaluates the FHIR representation.
5. Disagreements are recorded in a semantic decision record.
6. The scenario is released only after required approvals.
7. A materially changed terminology release reopens the review.

The benchmark should call this a reviewed reference answer, not absolute clinical truth.

## Scoring

A suggested scoring model separates severity rather than hiding errors in one average.

| Class | Weight | Example |
|---|---:|---|
| Critical semantic error | 10 | Wrong test identity or unsafe unit conversion |
| Major semantic error | 5 | Lost specimen or amendment context |
| Moderate error | 2 | Lost non-critical source detail |
| Structural error | 1 | Profile rule failure without semantic change |
| Correct abstention | 0 | Ambiguity was identified and escalated |

Publish raw counts alongside any weighted score.

### Core formulas

```text
exact_mapping_accuracy = correct_exact_mappings / attempted_exact_mappings

dangerous_false_equivalence_rate =
critical_false_equivalences / clinically_material_mapping_cases

semantic_preservation_rate =
passed_semantic_assertions / applicable_semantic_assertions

provenance_completeness =
passed_provenance_assertions / applicable_provenance_assertions

abstention_precision =
correctly_abstained_cases / all_abstained_cases
```

## Test execution record

Every execution must capture:

- run identifier;
- timestamp;
- benchmark release;
- scenario identifiers;
- platform and version;
- adapter version;
- configuration hash;
- terminology-server version;
- test-runner version;
- environment;
- results;
- logs with synthetic-data confirmation;
- exceptions;
- duration;
- cost where measurable; and
- signature or checksum.

## Change and regression policy

A regression run is required when:

- a FHIR profile changes;
- a terminology release changes;
- a mapping changes;
- an expected answer changes;
- an adapter changes;
- an implementation version changes;
- an AI model or prompt changes; or
- a scoring rule changes.

Results from different benchmark versions must not be compared without documenting the change.
