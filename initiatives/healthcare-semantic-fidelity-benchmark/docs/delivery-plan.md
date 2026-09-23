# Delivery Plan

## Delivery objective

Produce an H3 synthetic cross-platform evidence release for laboratory-result semantic fidelity.

## Indicative duration

A small qualified team could target an initial release in approximately 8 to 12 weeks. This is an estimate, not a delivery commitment.

## Work packages

### WP1: Scope and governance

Outputs:

- approved problem statement;
- use-case contract;
- safety boundary;
- clinical and terminology authority model;
- licence register; and
- evidence measures.

Indicative effort: 1 to 2 weeks.

### WP2: Standards and profile

Outputs:

- selected FHIR R4 resources;
- minimum profile;
- value sets;
- terminology versions;
- mapping-record format; and
- validation rules.

Indicative effort: 2 to 3 weeks.

### WP3: Synthetic source systems

Outputs:

- Synthetic Laboratory A schema;
- Synthetic Laboratory B schema;
- synthetic patients and orders;
- synthetic HL7 Version 2 messages; and
- expected FHIR outputs.

Indicative effort: 1 to 2 weeks.

### WP4: Terminology and transformations

Outputs:

- local-to-LOINC mappings;
- UCUM units;
- selected conversion rules;
- status mappings;
- abnormal-flag mappings;
- specimen mappings; and
- reviewer decisions.

Indicative effort: 2 to 4 weeks.

### WP5: Test suite

Outputs:

- valid fixtures;
- invalid fixtures;
- ambiguous fixtures;
- semantic assertions;
- negative tests;
- round-trip tests; and
- automated test runner.

Indicative effort: 2 to 3 weeks.

### WP6: AI mapping evaluation

Outputs:

- fixed evaluation dataset;
- deterministic baseline;
- AI candidate-generation protocol;
- confidence and abstention measures;
- reviewer corrections; and
- comparative results.

Indicative effort: 1 to 2 weeks.

### WP7: Cross-platform evaluation

Outputs:

- HAPI FHIR execution;
- one managed FHIR-platform execution;
- environment manifests;
- reproducible results; and
- deviation register.

### WP8: Evidence publication

Outputs:

- evidence report;
- failed and unresolved case register;
- maturity declaration;
- limitations;
- reproducibility guide; and
- release notes.

## Required roles

- FHIR or healthcare integration engineer;
- clinical informatician or laboratory domain expert;
- terminology specialist;
- test and evidence engineer;
- privacy and security reviewer; and
- licence reviewer.

One person may perform several technical roles, but the same person should not author and independently approve clinically material mappings.

## Release acceptance criteria

Release 0.1 should include:

- 20 test types;
- two synthetic source models;
- 100 to 200 results;
- at least 20 difficult cases;
- FHIR R4 outputs;
- LOINC and UCUM mappings;
- automated structural tests;
- automated semantic assertions;
- deterministic and AI mapping results;
- two FHIR implementations;
- no real patient data;
- complete fixture provenance; and
- a published limitations section.

## Immediate backlog

1. Approve the initiative charter and safety boundary.
2. Define the laboratory-results use-case contract.
3. Select 20 laboratory test types.
4. Define the two source schemas.
5. Select FHIR implementation-guide dependencies.
6. Define the mapping-record schema.
7. Define evidence measures.
8. Recruit clinical and terminology reviewers.
9. Create the first five fixtures.
10. Run the first end-to-end test using HAPI FHIR.
