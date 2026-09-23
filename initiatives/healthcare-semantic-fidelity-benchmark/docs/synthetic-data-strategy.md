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
9. Record provenance and licences.
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


## Synthetic-data quality dimensions

Synthetic data should be evaluated across:

| Dimension | Question |
|---|---|
| Structural validity | Does the record satisfy the declared source schema? |
| Clinical plausibility | Are values, units, specimens and ranges plausible together? |
| Workflow plausibility | Do order, collection, result and correction events occur in a credible sequence? |
| Diversity | Are common and uncommon representations included? |
| Boundary coverage | Are minimum, maximum, missing and incompatible cases represented? |
| Bias | Does the dataset exclude relevant populations or workflows? |
| Privacy | Can the data be confidently identified as artificial? |
| Traceability | Can every generated value be traced to a rule or seed? |
| Reproducibility | Can the same fixture be regenerated? |
| Challenge value | Does the case expose a meaningful interoperability risk? |

## Generation controls

- Use fixed random seeds for released generated datasets.
- Separate generated background records from curated edge cases.
- Store generator configuration and version.
- Never train a generator on restricted organisational data for a public release.
- Use obviously synthetic identifiers and organisations.
- Prevent accidental use of real addresses, phone numbers and identifiers.
- Scan fixtures for secrets and patterns resembling protected identifiers.
- Review free-text fields because they create higher disclosure risk.
- Record whether a value was generated, curated or transformed.

## Data classes

| Class | Description | Public repository |
|---|---|---:|
| S0 | Purpose-built fictional fixture | Allowed |
| S1 | Open synthetic dataset under compatible terms | Allowed with provenance |
| S2 | Heavily de-identified public test data | Review required |
| S3 | Partner synthetic data based on local structures | Only with written approval |
| S4 | De-identified operational data | Not in the public repository |
| S5 | Identifiable or re-identifiable health data | Prohibited |

## Quality-review workflow

1. Validate the source schema.
2. Validate the expected FHIR output.
3. Check terminology and unit combinations.
4. Check temporal and workflow consistency.
5. Check diversity and boundary coverage.
6. Confirm synthetic identifiers and organisations.
7. Scan for secrets and sensitive patterns.
8. Review licence and attribution.
9. Obtain required clinical and terminology approvals.
10. Assign the data class and release status.

## Partner output controls

Local execution may still disclose information through logs, counts or rare error messages.

Before a partner shares output:

- remove source payloads;
- suppress rare-value detail;
- aggregate counts where appropriate;
- review free text;
- verify that local codes are approved for disclosure;
- review stack traces and file paths;
- inspect screenshots;
- confirm that no patient or workforce identifier is present; and
- obtain organisational approval.

## Synthetic-to-production transition criteria

A move from H3 to H4 requires:

- an approved partner agreement;
- a documented local-execution design;
- information classification;
- threat assessment;
- output-review procedure;
- incident process;
- named partner authority;
- licence review for local code lists;
- no default external telemetry; and
- evidence that the public benchmark remains independent of partner data.


## Detailed synthetic-data approach

Synthetic data is not merely a privacy substitute. In this benchmark it is also an experimental control. Because the initiative defines the scenario and expected meaning, it can introduce one variation at a time and observe whether an implementation handles that variation correctly. Real operational data is often richer, but its ambiguity makes it harder to determine whether a failed result came from the platform, the mapping or an undocumented source convention.

Generated patient records provide useful background context, but generated realism should not be confused with clinical authority. Synthea can create coherent fictional histories and FHIR resources, yet it may not generate the specialised laboratory edge cases required by the benchmark. The initiative should therefore combine generated background records with manually designed challenge cases.

A curated fixture should explain why each value exists. If a potassium result uses a particular specimen and unit, the fixture should identify the rule supporting that combination. If a reference range changes by age or sex, the scenario should explain which patient characteristic activates the range. This makes review more efficient and helps future contributors distinguish a deliberate edge case from a data-quality mistake.

The use of obviously fictional organisations and identifiers reduces the chance that synthetic records will be mistaken for real data. Names, addresses and identifiers should come from controlled generators rather than copied examples. Free text deserves special scrutiny because it is easy to paste content from a real report accidentally. Automated scanning should complement, not replace, human review.

Synthetic data also has limitations that must remain visible. It will not reproduce every local code, historical anomaly, interface workaround or workflow exception found in a hospital. An H3 result can show that the benchmark works across synthetic scenarios and named platforms. It cannot show how much effort a specific organisation will require to map decades of local practice.

The partner-local model provides a path forward without centralising patient data. A healthcare organisation can run the same test framework against approved local structures within its environment. The organisation can share aggregate evidence after disclosure review. This approach keeps source records under organisational control while allowing SIEL to learn whether its synthetic cases reflect real implementation problems.
