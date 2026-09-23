# Healthcare Evidence Maturity Model

## Purpose

The maturity model prevents synthetic testing from being presented as production or clinical evidence.

| Level | Name | Required evidence | Organisational data required |
|---|---|---|---:|
| H0 | Concept | Problem, scope, standards and safety boundaries documented | No |
| H1 | Structural | FHIR profiles, examples and automated structural validation | No |
| H2 | Synthetic semantic | Reviewed synthetic mappings, edge cases and semantic measures | No |
| H3 | Cross-platform | Synthetic benchmark executed against multiple implementations | No |
| H4 | Local-schema | Partner tests using approved local schemas, code lists or synthetic local examples | Limited |
| H5 | Controlled operational | Testing with de-identified operational data in an approved environment | Yes |
| H6 | Production | Monitored production implementation with clinical, privacy, security and operational evidence | Yes |

## Claim rules

### H0

Permitted claim:

> The initiative has defined a healthcare interoperability problem and proposed a testable benchmark.

### H1

Permitted claim:

> The profile and fixtures pass the stated structural validation rules.

### H2

Permitted claim:

> The benchmark preserves the reviewed meaning of its published synthetic scenarios.

### H3

Permitted claim:

> The published synthetic profile has been tested across the named implementations under the recorded conditions.

### H4

Permitted claim:

> The benchmark has been tested against approved local structures or code lists from participating organisations.

### H5

Permitted claim:

> The benchmark has been evaluated using controlled operational data under the stated governance conditions.

### H6

Permitted claim:

> The profile has published production evidence for the named implementation, workflow, period and limitations.

## Prohibited claims before H6

Do not describe an earlier maturity level as:

- clinically safe;
- production certified;
- universally interoperable;
- suitable for diagnosis;
- suitable for autonomous clinical use;
- proven across hospitals;
- compliant with every jurisdiction; or
- free from semantic risk.

## Evidence package

Every release should include:

- maturity level;
- profile version;
- standards and terminology versions;
- test-run identifier;
- implementation versions;
- fixture identifiers;
- measures and thresholds;
- failed and unresolved cases;
- reviewer roles;
- conflicts of interest;
- reproducibility instructions;
- licence information; and
- explicit limitations.

Evidence applies only to the versions and conditions tested.


## Advancement gates

### H0 to H1

Required:

- approved scope and exclusions;
- selected FHIR version;
- initial profile;
- validation rules;
- synthetic-only policy; and
- named technical reviewers.

### H1 to H2

Required:

- approved scenario schema;
- reviewed reference answers;
- terminology versions;
- minimum edge-case set;
- semantic assertions;
- deterministic baseline; and
- published limitations.

### H2 to H3

Required:

- at least two implementations;
- pinned environments;
- portable fixtures;
- execution records;
- deviation analysis;
- reproducibility instructions; and
- independent rerun of a representative subset.

### H3 to H4

Required:

- approved partner;
- local-data boundary;
- partner-specific schema or code-list approval;
- information-security review;
- output disclosure controls;
- local test-run evidence; and
- public report reviewed by the partner.

### H4 to H5

Required:

- approved secure environment;
- data-use authority;
- privacy and ethics review where applicable;
- operational-data quality assessment;
- controlled access;
- disclosure review; and
- evidence that published results cannot identify individuals.

### H5 to H6

Required:

- production change control;
- safety and clinical governance;
- security accreditation;
- monitoring;
- incident and rollback procedures;
- operational support;
- defined success thresholds;
- observation period; and
- approval to publish bounded production evidence.

## Evidence status

Each result must use one status:

| Status | Meaning |
|---|---|
| Draft | Incomplete and not reviewable |
| Submitted | Ready for required review |
| Disputed | Material disagreement remains |
| Accepted | Required reviewers approved the evidence |
| Superseded | A later version replaces the result |
| Withdrawn | Evidence was invalidated or should no longer support claims |

Withdrawn evidence remains discoverable unless removal is required for privacy, security or legal reasons.

## Evidence strength

Maturity and strength are different. An H3 result may be strongly reproduced within synthetic scope while remaining irrelevant to production.

Evidence strength should record:

- number of scenarios;
- scenario diversity;
- reviewer independence;
- number of implementations;
- independent reproduction;
- unresolved-case rate;
- dependency coverage;
- recency; and
- known conflicts of interest.

## Expiry and review

Evidence requires review when:

- a normative standard changes;
- a terminology release changes;
- the tested platform changes materially;
- a critical fixture is corrected;
- a serious defect is discovered;
- the evidence is older than the review period; or
- the use case expands.

The release should declare its review period. Expired evidence is not automatically false, but it must not be represented as current without review.


## How to interpret maturity

The maturity model describes the context in which evidence was produced. It is not a quality score. An H2 benchmark may be exceptionally well designed and reproducible, but it remains synthetic. An H5 result may involve operational data, yet still be weak if the study is poorly controlled or inadequately reviewed. Users must consider both maturity and evidence strength.

H0 establishes that the problem is coherent and bounded. At this level, the initiative may publish a hypothesis, architecture and safety boundary, but it has not demonstrated that the proposed artifacts work. H1 adds executable structural validation. This proves that profiles and examples can be processed by the selected tools, but it still says little about preserved clinical meaning.

H2 is the first semantic evidence level. Reference answers have been reviewed, difficult synthetic cases exist and the benchmark can measure whether transformations preserve the intended meaning. H3 adds portability by executing the same benchmark across more than one implementation. This is the target for the first public release because it demonstrates that the work is more than a single-platform demonstration.

H4 introduces approved local structures or code lists from a partner. This is valuable because it tests assumptions against real organisational variation without necessarily using patient data. H5 adds controlled operational data inside an approved environment. At this level, privacy, ethics, data quality and disclosure controls become material parts of the evidence.

H6 represents bounded production evidence. It requires more than a technically successful deployment. The implementation must have change control, monitoring, incident response, accountable clinical governance and an observation period. Even then, the claim applies only to the named workflow, versions, organisation and period.

Advancement should never occur simply because time has passed or a document has been completed. Each gate requires evidence artifacts and approval. If a critical expected answer is later found to be wrong, affected results may need to be withdrawn or superseded. Maintaining that history is part of scientific and engineering integrity.
