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
