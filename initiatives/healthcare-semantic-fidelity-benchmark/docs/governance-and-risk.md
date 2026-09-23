# Governance and Risk

## Governance principle

Technical validity, terminology validity and clinical meaning require different authorities.

## Required authorities

| Decision | Required authority |
|---|---|
| Repository structure and automation | Technical maintainer |
| FHIR profile design | FHIR specialist and technical reviewer |
| LOINC mapping | Terminology specialist with laboratory review |
| Clinically material expected result | Qualified clinical or laboratory reviewer |
| Privacy classification | Privacy reviewer |
| Security control | Security reviewer |
| Licence and redistribution decision | Licence reviewer or legal adviser |
| Evidence claim | Evidence reviewer and initiative maintainer |

## AI governance

AI may:

- propose candidate mappings;
- explain differences;
- identify missing fields;
- generate test variants; and
- assist with documentation.

AI may not:

- approve clinical mappings;
- determine clinical significance;
- override a qualified reviewer;
- silently convert an unresolved mapping into an exact match; or
- generate evidence without recording the model, prompt context and review outcome.

## Primary risks

| Risk | Consequence | Control |
|---|---|---|
| Incorrect reference mapping | Benchmark rewards unsafe output | Independent terminology and laboratory review |
| Unrealistic synthetic data | Results do not generalise | Publish limitations and add partner validation later |
| Structural success mistaken for semantic success | False assurance | Report structural and semantic measures separately |
| Restricted terminology redistribution | Licence breach | Store permitted identifiers only and use external services where required |
| AI false equivalence | Clinically material error | Require abstention, review and dangerous-error measures |
| Test leakage | Inflated AI performance | Maintain held-out fixtures and versioned evaluation sets |
| Vendor bias | Unfair comparison | Declare funding, conflicts and test conditions |
| Version drift | Non-reproducible results | Pin standards, terminology, tools and environment versions |
| Accidental real data | Privacy incident | Synthetic-only checks, contribution policy and review |
| Overstated claims | Reputational and safety harm | Apply evidence-maturity claim rules |

## Contribution requirements

Every contribution containing a fixture or mapping must include:

- source and licence;
- synthetic-data declaration;
- standards and versions;
- expected outcome;
- author;
- required reviewer roles;
- limitations; and
- confirmation that it contains no real patient data.

## Publication rules

Publish:

- methods;
- versions;
- fixtures where licences permit;
- measures;
- failures;
- unresolved cases;
- reviewer roles;
- conflicts of interest; and
- limitations.

Do not publish:

- patient information;
- confidential partner information;
- restricted terminology content;
- credentials;
- unreviewed clinical claims; or
- vendor rankings unsupported by reproducible evidence.

## Incident response

If real or suspected patient data is committed:

1. stop distribution and testing;
2. notify repository maintainers;
3. restrict access where possible;
4. preserve necessary audit evidence without further disclosure;
5. follow the applicable incident process;
6. remove exposed material using an approved repository-history procedure;
7. notify affected parties where required; and
8. document corrective actions.

Do not treat ordinary file deletion as sufficient removal from Git history.


## Decision bodies

### Initiative maintainers

Responsible for scope, backlog, releases, repository quality and coordination.

### Semantic Review Group

Responsible for disputed mappings, terminology decisions, semantic-loss classification and reference answers.

Membership should include FHIR, terminology and laboratory expertise. A decision involving clinically material meaning requires a qualified clinical or laboratory reviewer.

### Evidence Review Group

Responsible for test methods, measures, reproducibility, platform comparisons and maturity claims.

### Safety, Privacy and Licence Review

Responsible for data classification, disclosure controls, security issues, external-content reuse and incident escalation.

Small initial teams may combine groups, but decision roles and conflicts must remain visible.

## Decision types

| Type | Example | Approval |
|---|---|---|
| Technical | Repository layout or test-runner change | Technical maintainer and reviewer |
| Profile | Required FHIR element | FHIR reviewer and semantic reviewer |
| Terminology | LOINC mapping or value-set change | Terminology reviewer and laboratory reviewer |
| Clinical meaning | Reference range interpretation | Qualified clinical or laboratory reviewer |
| Evidence | Measure or maturity claim | Evidence reviewer |
| Safety | Expansion into decision support | Safety review and initiative approval |
| Licence | Inclusion of external terminology content | Licence review |
| Release | H2 or H3 publication | Maintainer plus required reviewers |

## Semantic decision record

A material decision should record:

- decision identifier;
- question;
- context;
- affected scenarios;
- options considered;
- authoritative sources;
- reviewer roles;
- conflicts of interest;
- decision;
- rationale;
- limitations;
- effective date;
- superseded decision; and
- required regression tests.

## Risk scoring

Score each risk on:

- likelihood from 1 to 5;
- impact from 1 to 5;
- detectability from 1 to 5, where 5 is difficult to detect.

```text
risk_priority = likelihood * impact * detectability
```

The score supports prioritisation but does not replace clinical judgement. Any plausible patient-safety risk may require escalation regardless of total score.

## Release gates

A public release requires:

- synthetic-data confirmation;
- automated validation;
- approved reference answers;
- complete licences and provenance;
- risk review;
- reproducibility instructions;
- independent review of a representative sample;
- published failures and unresolved cases;
- evidence-maturity statement; and
- maintainer approval.

## Dispute process

1. Open a documented challenge.
2. Identify the exact fixture, assertion or claim.
3. Provide authoritative sources or reproducible evidence.
4. Record conflicts of interest.
5. Assign reviewers who did not author the disputed item.
6. Decide to accept, revise, reject or leave unresolved.
7. Record the rationale.
8. Rerun affected tests.
9. Publish the outcome and affected releases.

An unresolved dispute must remain visible and must not be converted into consensus by majority vote alone.

## Vulnerability and safety reporting

Security vulnerabilities should follow the repository security policy and should not be disclosed in a public issue before coordinated review.

Potential clinical-safety defects should be marked clearly, assigned urgent review and linked to affected fixtures, mappings, releases and evidence claims.

## Sustainability

Before an H3 release, define:

- maintainer ownership;
- supported benchmark versions;
- dependency-update cadence;
- terminology-update cadence;
- archive policy;
- funding disclosures;
- reviewer succession;
- deprecation process; and
- response expectations for critical defects.
