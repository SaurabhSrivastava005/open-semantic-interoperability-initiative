# Synthetic Data Strategy

## Objective

The first three evidence levels will be developed without receiving data from healthcare organisations.

## Permitted sources

### Synthea

Synthea provides realistic but artificial patient and health records. It can supply synthetic patients, encounters, observations, practitioners and organisations.

Official source:

- https://synthea.mitre.org/
- https://github.com/synthetichealth/synthea

### HL7 AU FHIR Test Data

HL7 Australia provides synthetic FHIR instances for implementation-guide testing.

Official source:

- https://github.com/hl7au/au-fhir-test-data

### HL7 FHIR examples

HL7 publishes examples and downloadable packages. These are useful inputs but are not normative clinical ground truth.

Official source:

- https://hl7.org/fhir/
- https://hl7.org/fhir/downloads.html

### Purpose-built fixtures

SIEL will create synthetic laboratory edge cases specifically designed to expose semantic failures.

## Data-generation process

1. Define the clinical scenario.
2. Define the expected meaning.
3. Create two different source representations.
4. Create the expected FHIR representation.
5. Add the terminology and transformation rules.
6. Add a positive test.
7. Add at least one negative or ambiguous variant.
8. Review the expected outcome.
9. record provenance and licences.
10. Publish the fixture and limitations.

## Required fixture metadata

Every fixture should record:

- fixture identifier;
- synthetic-data declaration;
- clinical scenario;
- source model;
- expected result;
- standards and versions;
- terminology releases;
- author;
- clinical reviewer;
- terminology reviewer;
- review date;
- known limitations; and
- licence.

## What synthetic data can prove

Synthetic data can support evidence about:

- profile conformance;
- deterministic transformation behaviour;
- known terminology mappings;
- unit conversions;
- designed edge cases;
- cross-platform portability;
- AI mapping performance against a reviewed answer set; and
- reproducibility.

## What synthetic data cannot prove

Synthetic data cannot fully establish:

- production mapping quality;
- undocumented local-code meaning;
- historical inconsistencies;
- vendor-specific message customisation;
- live message sequencing;
- production patient matching;
- performance at hospital scale;
- privacy-control effectiveness;
- integration with a particular EHR or laboratory system; or
- clinical safety in live use.

## Repository prohibition

Do not commit:

- real patient records;
- identifiable information;
- pseudonymised organisational data;
- production messages;
- screenshots containing patient or staff information;
- access credentials;
- restricted terminology distributions; or
- data whose licence and provenance have not been verified.

## Future privacy-preserving partner models

### Local execution

A partner runs the SIEL benchmark inside its environment and shares only reviewed aggregate results.

### Schema and code-list testing

A partner shares approved schemas, field definitions, synthetic examples and selected local codes without patient records.

### Containerised benchmark

SIEL distributes an offline test container. The partner reviews all output before publication.

### Secure research environment

Approved contributors access data within a governed environment. Source data is not copied into SIEL.

These approaches reduce disclosure risk but still require partner governance, legal review, security review and output checking.
