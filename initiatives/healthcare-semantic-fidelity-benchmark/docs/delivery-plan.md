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


## Milestones

| Milestone | Outcome | Exit evidence |
|---|---|---|
| M0 Initiative ready | Scope, governance and team are approved | H0 gate completed |
| M1 Profile ready | Minimum FHIR profile and validation rules exist | Profile package and decision records |
| M2 Fixtures ready | Two source models and reviewed cases exist | Fixture register and approvals |
| M3 Runner ready | Tests execute deterministically | Reproducible local test run |
| M4 AI evaluation ready | Fixed protocol and held-out cases exist | Baseline and evaluation manifest |
| M5 Cross-platform ready | Two implementations complete the suite | Platform execution records |
| M6 Release ready | Evidence and limitations are independently reviewed | H3 report and release approval |

## Suggested 12-week schedule

| Weeks | Focus |
|---|---|
| 1 to 2 | Scope, governance, standards register and reviewer recruitment |
| 2 to 4 | FHIR profile, terminology policy and source-model design |
| 3 to 6 | Synthetic fixtures, reviewed answers and mapping records |
| 5 to 8 | Test runner, assertions and deterministic baseline |
| 7 to 9 | AI evaluation and held-out cases |
| 8 to 10 | Cross-platform execution and deviation analysis |
| 10 to 12 | Independent reproduction, evidence review and release |

Work may overlap, but reviewer availability is a critical dependency.

## Definition of ready

A work item is ready when it has:

- a clear problem;
- bounded scope;
- owner;
- required reviewers;
- source standards and licences;
- acceptance criteria;
- dependencies;
- risk classification; and
- expected evidence artifact.

## Definition of done

A work item is done when:

- required artifacts are versioned;
- automated tests pass;
- required reviews are recorded;
- limitations are documented;
- licences and provenance are complete;
- no prohibited data is present;
- change impact is assessed; and
- the roadmap and evidence register are updated.

## Dependency plan

| Dependency | Risk | Response |
|---|---|---|
| Clinical reviewer availability | Release delay | Recruit before fixture authoring |
| Terminology licence | Redistribution restriction | Reference external service or permitted identifiers |
| Managed platform access | Cross-platform delay | Start with HAPI and add a managed platform when access is approved |
| Implementation-guide selection | Rework | Record the decision before profile authoring |
| AI model changes | Non-comparable results | Pin model and evaluation configuration |
| Synthetic realism | Weak generalisation | Use expert review and disclose limitations |
| Volunteer continuity | Maintenance gap | Assign owners and archive unsupported releases |

## Initial issue structure

- Epic 1: Initiative governance
- Epic 2: Standards and terminology registry
- Epic 3: Laboratory profile
- Epic 4: Synthetic source systems
- Epic 5: Fixture and answer-set development
- Epic 6: Test runner and assertions
- Epic 7: AI mapping evaluation
- Epic 8: Cross-platform execution
- Epic 9: Evidence report and release

Each issue should identify its artifact, reviewer, maturity contribution and blocking dependencies.

## Resourcing assumptions

Minimum credible team capacity:

- FHIR engineer: 0.5 to 1.0 full-time equivalent;
- terminology specialist: 0.2 to 0.4;
- laboratory or clinical informatician: 0.2 to 0.4;
- test engineer: 0.5;
- governance, privacy and licence review: part-time at gates; and
- maintainer or product lead: 0.3.

Volunteer delivery may take longer than the indicative schedule.


## Delivery narrative

The proposed schedule begins with governance because fixture development depends on knowing who can approve meaning. Starting with code may appear faster, but it creates rework when terminology, licensing or clinical-review requirements emerge later. The first two weeks should therefore establish the use-case contract, decision rights, standards register and reviewer availability.

Profile design and source-model design can proceed together once the boundary is stable. The profile team identifies the minimum FHIR elements required to preserve the use case. The source-model team creates two intentionally different ways of representing the same events. Regular joint review is necessary because an unrealistic source model will produce an easy benchmark, while an excessively broad profile will become difficult to implement.

Fixture development is expected to be the largest reasoning task. Each case needs a source representation, expected target, assertions, provenance and review. The team should begin with five end-to-end fixtures rather than designing all 100 records at once. Those first cases will expose gaps in the artifact schemas, test runner and review process.

The deterministic baseline should be built before the AI evaluation. Without a stable non-AI transformation and reviewed answer set, the team cannot determine whether AI improves speed or merely introduces variation. The AI work package should use the same mappings and held-out cases, record abstentions and measure reviewer effort.

Cross-platform execution should begin only after local tests are reproducible. Differences found too early may reflect an unstable benchmark rather than meaningful platform behaviour. HAPI FHIR provides a practical open baseline. A managed service can then test portability, provided the account, cost and synthetic-data controls are approved.

The final two weeks focus on evidence rather than cosmetic presentation. The team must reproduce a representative subset independently, review disputed results, confirm licences, state maturity and publish limitations. A release should be delayed if required clinical or terminology review is incomplete. Schedule pressure is not a valid reason to lower the evidence boundary.

The 8 to 12 week estimate assumes contributors with relevant experience and timely reviewer participation. A volunteer project may need a longer calendar period. The delivery plan should report actual effort after the first release so later profiles can be estimated from evidence rather than optimism.
