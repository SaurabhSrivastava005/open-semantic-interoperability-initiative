# Problem and Scope

## The problem

Hospitals, laboratories, research organisations and digital-health platforms often represent the same laboratory test differently.

Differences can include:

- local test codes;
- test names;
- specimens;
- methods;
- units;
- reference ranges;
- abnormal-result flags;
- result status;
- timestamps;
- patient and organisation identifiers; and
- report structure.

A successful technical conversion does not guarantee that the receiving system understands the result correctly.

## Illustrative example

| Field | Synthetic Laboratory A | Synthetic Laboratory B |
|---|---|---|
| Local code | GLU-F | FBG01 |
| Display name | Fasting Glucose | Fasting Blood Sugar |
| Result | 108 | 6.0 |
| Unit | mg/dL | mmol/L |
| Status | C | Corrected |
| Abnormal flag | H | Above range |

These records may represent the same kind of measurement, but a valid conclusion depends on the code, specimen, method, unit conversion, reference range, effective terminology version and clinical context.

## Operational consequences

Uncontrolled semantic variation can cause:

- repeated point-to-point mapping work;
- inconsistent results between integrations;
- delayed onboarding;
- hidden semantic loss;
- incorrect unit transformations;
- incomplete provenance;
- unreliable research data;
- poor portability between vendors; and
- unsafe input for downstream analytics or AI.

## Primary users

- healthcare integration engineers;
- clinical informaticians;
- laboratory information specialists;
- terminology specialists;
- FHIR profile authors;
- health-data platform teams;
- researchers;
- conformance-tool developers;
- vendors; and
- governance and assurance teams.

## First use case

The first benchmark covers laboratory-result transformation into a bounded FHIR R4 profile.

### In scope

- synthetic laboratory data;
- HL7 Version 2 source messages;
- FHIR R4 target resources;
- local-code-to-LOINC mapping;
- UCUM unit representation and selected conversions;
- result status;
- abnormal flags;
- reference ranges;
- specimen context;
- corrected results;
- provenance;
- structural conformance;
- semantic-fidelity measures;
- cross-platform portability; and
- deterministic and AI-assisted mapping comparison.

### Out of scope

- diagnosis;
- treatment recommendations;
- medical-device control;
- autonomous clinical decisions;
- real-time production deployment;
- patient matching across production organisations;
- complete microbiology workflows;
- genomic interpretation;
- medical imaging;
- billing and claims;
- real patient data in the public repository; and
- certification of clinical safety.

## Success condition

The initiative succeeds when an independent party can:

1. download the benchmark;
2. run the fixtures through an implementation;
3. compare results with reviewed expectations;
4. identify structural and semantic failures;
5. reproduce the reported measures; and
6. understand the limitations of the evidence.

A technically valid FHIR output is not sufficient if clinically material meaning was altered without being recorded.
