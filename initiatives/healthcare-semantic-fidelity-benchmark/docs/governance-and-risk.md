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
