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


## Stakeholder problems

| Stakeholder | Current problem | Evidence needed |
|---|---|---|
| Laboratory | Local codes and workflows are difficult to expose consistently | Mappings preserve test, specimen, method, value and status |
| Hospital integration team | Interfaces pass messages but local meaning remains undocumented | Reproducible semantic assertions and traceable transformations |
| EHR vendor | Profiles vary across customers and jurisdictions | Clear minimum profile and deviation register |
| Research team | Operational data may lose context during extraction | Provenance, source values and documented semantic loss |
| AI product team | Valid FHIR is treated as trustworthy input | Measured mapping accuracy, abstention and dangerous-error rates |
| Governance team | Compliance claims exceed available evidence | Versioned evidence levels and claim controls |
| Regulator or auditor | Transformation decisions are difficult to reconstruct | Immutable test runs, reviewer decisions and dependency versions |

## Decisions the benchmark must make

The benchmark must explicitly decide:

- which clinical scenarios are represented;
- which FHIR version and implementation guides apply;
- which elements are mandatory, optional or prohibited;
- which terminology release is authoritative;
- when two local concepts are equivalent;
- when unit conversion is allowed;
- when a result must remain unresolved;
- which changes are clinically material;
- what a platform must preserve;
- who may approve expected meaning; and
- what evidence supports each published claim.

## Semantic fidelity definition

For this initiative, semantic fidelity means that the target representation retains all information required to interpret the test result correctly within the declared use case.

It includes:

- identity of the test;
- specimen and method where material;
- result value and data type;
- unit and conversion history;
- reference range and applicable population;
- result status and amendment history;
- relevant timestamps;
- ordering and performing organisations;
- source-system identifiers; and
- provenance of every transformation.

A transformation may be conformant but not faithful. A transformation may also be faithful for one declared purpose and insufficient for another.

## Non-functional scope

The benchmark will also record:

- reproducibility;
- deterministic execution;
- test isolation;
- dependency pinning;
- auditability;
- portability;
- accessibility of documentation;
- execution cost;
- runtime;
- error transparency; and
- change resilience.

Performance testing is limited to benchmark execution. It is not a hospital-scale capacity certification.

## Assumptions

- All public fixtures are synthetic.
- Clinical expected results are reviewed before release.
- Local synthetic code systems are intentionally fictional.
- FHIR R4 is the initial exchange baseline.
- Terminology content is included only where licensing permits.
- The benchmark tests named implementations and versions, not entire vendors.
- An unresolved result is an acceptable outcome when equivalence cannot be supported.

## Exclusions rationale

Diagnosis and treatment are excluded because they introduce a different risk class, require broader clinical evidence and would distract from the initial interoperability hypothesis.

Production patient matching is excluded because it requires organisational identity rules, operational data and privacy controls that synthetic semantic testing cannot establish.

Complete microbiology and genomics are deferred because their result structures, temporal behaviour and interpretation require specialised profiles and reviewers.
