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
