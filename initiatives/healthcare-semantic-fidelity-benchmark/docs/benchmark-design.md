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
