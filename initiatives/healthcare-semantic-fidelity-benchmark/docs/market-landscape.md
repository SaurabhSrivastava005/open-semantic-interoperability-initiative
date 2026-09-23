# Market Landscape and Non-Duplication Boundary

## Existing capabilities

The healthcare interoperability market already provides substantial technology.

| Category | Examples | Existing capability |
|---|---|---|
| Integration engines | InterSystems Health Connect, Rhapsody, Mirth Connect, Cloverleaf and Iguana | Message routing, transformation, orchestration and monitoring |
| Interoperability platforms | Redox, InterSystems HealthShare and similar platforms | EHR connectivity, normalisation, FHIR conversion and workflow integration |
| Managed FHIR platforms | Azure Health Data Services, AWS HealthLake and Google Cloud Healthcare API | Managed FHIR storage, APIs, security and scaling |
| Open-source FHIR servers | HAPI FHIR and Microsoft FHIR Server | FHIR persistence, validation, search and APIs |
| Terminology services | Ontoserver and Snowstorm | Code systems, value sets, lookup, subsumption and validation |
| Conformance tools | Inferno, Touchstone, Crucible and HL7 Validator | Structural, profile and API conformance testing |
| Research models | OMOP Common Data Model | Standardised observational health analytics |
| Synthetic data tools | Synthea | Artificial patient and health-record generation |

## Duplication risk

SIEL would duplicate existing work if it attempted to build a generic FHIR server, integration engine, terminology server, validator, API gateway or clinical data platform.

The initiative must reuse these capabilities.

## Under-served evidence problem

Existing products move, transform, validate and store data. The proposed benchmark asks a different question:

> Did the transformation preserve the intended clinical meaning, and can the result be independently reproduced?

The benchmark combines four evidence levels.

| Evidence level | Question |
|---|---|
| Structural conformance | Is the resource technically valid? |
| Terminology conformance | Are codes, units and value sets used correctly? |
| Semantic fidelity | Did clinically material meaning remain intact? |
| Operational portability | Do different implementations interpret the same profile consistently? |

## SIEL contribution

| Existing capability | SIEL contribution |
|---|---|
| Convert HL7 to FHIR | Measure whether meaning was preserved |
| Validate a FHIR resource | Test semantic accuracy and context |
| Suggest terminology mappings | Compare suggestions with reviewed reference mappings |
| Store FHIR resources | Test portability between implementations |
| Provide terminology lookup | Test versioning, ambiguity and mapping behaviour |
| Generate AI mappings | Measure accuracy, risk and reviewer correction |
| Claim standards compliance | Publish reproducible evidence and limitations |
| Publish successful examples | Include negative, ambiguous and adversarial cases |

## Positioning

SIEL should be described as an independent evidence and benchmarking layer.

It should not claim to be the first or only healthcare semantic benchmark until a formal prior-art and competitive review supports that statement.

## Reuse policy

Before incorporating an external asset, record:

- owner and steward;
- canonical source;
- version;
- licence;
- redistribution rights;
- commercial-use conditions;
- terminology restrictions;
- attribution requirements; and
- whether the asset may be included, referenced or only accessed externally.

SNOMED CT and other controlled terminologies require particular care because rights and distribution conditions may vary by jurisdiction.


## Build, reuse and integrate decisions

| Capability | Decision | Reason |
|---|---|---|
| FHIR persistence | Reuse | Mature open-source and managed servers exist |
| FHIR validation | Reuse and extend | Existing validators cover structure; SIEL adds benchmark-specific assertions |
| Terminology service | Reuse | Mature services already manage code systems and value sets |
| HL7 transformation engine | Reuse or use a minimal test adapter | Production-grade engines already exist |
| Synthetic patient generation | Reuse and extend | Synthea and public test data provide a foundation |
| Semantic edge-case library | Build | It is central to the evidence objective |
| Reviewed answer set | Build | The benchmark requires controlled expected meaning |
| Cross-platform execution harness | Build thin adapters | The value is comparable execution, not another platform |
| Evidence schema | Build or profile an open schema | Results require consistent provenance and maturity metadata |
| Vendor dashboard | Defer | Evidence artifacts come before presentation software |

## Evaluation dimensions for existing tools

SIEL should assess tools against declared benchmark needs rather than rank vendors generally.

| Dimension | Evaluation question |
|---|---|
| Standards coverage | Which FHIR versions, resources and operations are supported? |
| Profile support | Can custom profiles and implementation guides be loaded and validated? |
| Terminology | Can the tool validate code systems, value sets and versions? |
| Transformation | Can source values and provenance be retained? |
| Test automation | Can results be reproduced without manual intervention? |
| Portability | Can fixtures run without vendor-specific rewriting? |
| Observability | Are validation and transformation decisions visible? |
| Security | Can synthetic tests run without external data transmission? |
| Licensing | Can the benchmark redistribute required adapters and configurations? |
| Cost | Can an independent contributor reproduce the published test? |

## Formal market-review process

Before claiming that a gap is under-served:

1. define the capability precisely;
2. search standards bodies, open-source projects, vendors and research;
3. record product version and evidence date;
4. distinguish documented capability from demonstrated behaviour;
5. invite maintainers to correct factual errors;
6. run the benchmark where access permits;
7. publish limitations and conflicts of interest; and
8. review the register at least twice each year.

## Vendor participation model

A vendor may:

- run the public benchmark;
- contribute an adapter;
- submit reproducible results;
- explain an implementation-specific deviation;
- challenge an expected result; and
- propose new fixtures.

A vendor may not:

- remove a valid negative result;
- approve its own disputed clinical mapping;
- use participation as proof of certification;
- restrict publication of the test method; or
- require SIEL to rank unrelated product capabilities.

## Neutrality controls

- Publish the same fixture set and measures for every implementation.
- Pin tested versions and configurations.
- Separate sponsored work from evidence approval.
- Declare financial and employment relationships.
- Give maintainers a factual-response period.
- Preserve superseded reports rather than silently replacing them.
- Report missing access or unsupported capabilities without speculation.
