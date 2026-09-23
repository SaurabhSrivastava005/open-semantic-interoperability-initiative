# Artifact Contract

## Purpose

The artifact contract defines the minimum metadata and lifecycle requirements for benchmark assets.

## Common metadata

Every normative artifact must include:

| Field | Meaning |
|---|---|
| id | Stable identifier |
| version | Artifact version |
| status | Draft, submitted, disputed, accepted, superseded or withdrawn |
| title | Human-readable name |
| description | Bounded purpose |
| owner | Accountable maintainer |
| authors | Contributors |
| reviewers | Required and completed reviewer roles |
| created_at | Creation timestamp |
| updated_at | Last material update |
| effective_from | Start of validity |
| supersedes | Prior artifact where applicable |
| sources | Authoritative references |
| licences | Applicable reuse conditions |
| dependencies | Standards, terminology, tools and upstream artifacts |
| limitations | Known boundaries |
| checksum | Integrity value for released artifacts |

## Standards-register record

Required fields:

- steward;
- canonical URL;
- standard or implementation-guide version;
- jurisdiction;
- artifact type;
- normative status;
- licence;
- redistribution class;
- terminology dependencies;
- implementation dependencies;
- last verified date; and
- verification evidence.

## Mapping record

Required fields:

- source system and version;
- source concept or path;
- target profile and path;
- mapping relationship;
- transformation;
- terminology release;
- confidence;
- evidence;
- reviewer;
- approval;
- effective period;
- reversibility;
- semantic-loss classification; and
- escalation rule.

Allowed mapping relationships:

- exact;
- equivalent for declared use;
- broader;
- narrower;
- conditional;
- derived;
- transformed;
- unresolved; and
- prohibited.

## Fixture manifest

Required fields:

- fixture identifier;
- scenario;
- data class;
- synthetic declaration;
- source model;
- expected output;
- assertion set;
- generator and seed;
- standards versions;
- terminology versions;
- clinical review;
- terminology review;
- licence;
- known ambiguity; and
- prohibited uses.

## Test assertion

Required fields:

- assertion identifier;
- fixture;
- assertion type;
- severity;
- expression;
- expected result;
- rationale;
- authoritative source;
- reviewer;
- automated status; and
- failure message.

Severity values:

- critical;
- major;
- moderate;
- structural; and
- informational.

## Test-run record

Required fields:

- run identifier;
- benchmark version;
- execution time;
- implementation;
- implementation version;
- environment checksum;
- adapter version;
- fixtures;
- assertions;
- passed, failed and skipped counts;
- semantic measures;
- unresolved cases;
- execution duration;
- cost where recorded;
- logs;
- output checksum; and
- signature where used.

## Evidence record

Required fields:

- evidence identifier;
- maturity level;
- claim;
- applicable scope;
- supporting test runs;
- reviewer decisions;
- conflicts of interest;
- failed and disputed cases;
- reproducibility instructions;
- publication date;
- review date;
- expiry or review trigger;
- limitations; and
- status.

## Semantic decision record

Required fields:

- question;
- context;
- options;
- authoritative sources;
- affected artifacts;
- decision;
- rationale;
- dissent;
- reviewer roles;
- effective date;
- superseded decision; and
- required regression tests.

## Validation rules

A release pipeline should reject an artifact when:

- a required identifier is missing;
- a dependency version is unpinned;
- licence metadata is absent;
- a normative mapping lacks required approval;
- a fixture lacks a synthetic declaration;
- a critical assertion has no authoritative rationale;
- an evidence claim lacks supporting runs;
- a withdrawn artifact is referenced as current;
- prohibited data patterns are detected; or
- the checksum does not match.

## Versioning

Use semantic versioning for released benchmark packages.

- Major: incompatible profile, fixture or scoring change.
- Minor: backward-compatible scenarios, assertions or platform coverage.
- Patch: correction that does not change expected semantic outcomes.

If a correction changes an expected clinical or terminology result, treat it as at least a minor release and invalidate affected evidence.


## How the artifacts work together

The standards register establishes the external authorities and versions used by the benchmark. A profile references these records instead of embedding undocumented assumptions. When a standard or terminology release changes, dependency links identify which mappings, fixtures and evidence may need review.

A mapping record captures one semantic decision. It does not merely state that one field maps to another. It describes the relationship, transformation, evidence, reviewer, effective period and semantic loss. This allows an exact mapping to be distinguished from a use-case-specific equivalence or a derived value.

A fixture combines mapping decisions into a testable scenario. Its manifest identifies the synthetic source, expected target and assertions. Keeping the fixture self-describing makes it possible to run a subset of scenarios, audit its provenance or retire it without searching through prose documentation.

Assertions convert expectations into executable rules. A critical assertion should explain why failure matters and identify its authority. For example, an assertion may require that the original unit remain available after conversion. The rationale explains that future reviewers need to reconstruct the source representation and verify the conversion.

The test-run record describes one execution, while the evidence record describes what can reasonably be concluded from one or more executions. This separation prevents a successful run from automatically becoming a broad claim. Evidence review determines scope, maturity, limitations and review date.

Semantic decision records connect disagreements and changes to the affected artifacts. If reviewers later decide that a mapping was too broad, the decision record identifies the replacement, and dependency links trigger regression testing. The old evidence can then be superseded with a visible explanation.

Machine-readable validation is important because documentation rules are easily forgotten. The release pipeline should reject artifacts with missing licences, unpinned versions or incomplete approvals. Automation cannot determine clinical correctness, but it can ensure that the required human decision is present and traceable.
