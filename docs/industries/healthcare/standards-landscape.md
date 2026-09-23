# Healthcare and Life Sciences Standards Landscape

## Scope

This landscape covers clinical exchange, health records, terminology, observational research, laboratory data and academic medical-centre interoperability.

## Standards and models

| Standard or framework | Primary purpose | Availability and boundary | SIEL treatment |
|---|---|---|---|
| [HL7 FHIR](https://hl7.org/fhir/) | Exchange healthcare information through modular resources and APIs | Public specification with implementation guides, profiles and open reference implementations | Use as the primary exchange foundation where suitable |
| HL7 Version 2 | Clinical messaging, especially within hospitals and laboratories | Widely implemented with local variation | Build explicit profiles and test local segments and codes |
| [openEHR](https://specifications.openehr.org/) | Clinically governed health-record models and archetypes | Open specifications, archetypes and implementations | Evaluate for longitudinal clinical models |
| [OMOP Common Data Model](https://ohdsi.github.io/CommonDataModel/) | Observational health analytics and research | Open model, vocabularies and community tooling | Use for research analytics profiles, not transactional exchange |
| [SNOMED CT](https://www.snomed.org/) | Clinical terminology | Licensing conditions vary by territory | Reference through approved distributions and record jurisdiction |
| [LOINC](https://loinc.org/) | Laboratory and clinical observations | Public terminology subject to its licence and usage terms | Use for observation and laboratory coding |
| [DICOM](https://www.dicomstandard.org/) | Medical imaging information and exchange | Public standard with mature implementations | Use for imaging-specific profiles |
| [CDISC](https://www.cdisc.org/standards) | Clinical research data | Governed standards with access and membership considerations | Evaluate for clinical-trial and regulatory research profiles |
| [FAIR Principles](https://www.go-fair.org/fair-principles/) | Research data and metadata quality | Principles rather than a model or protocol | Apply to research datasets and evidence packages |

## Priority SIEL profiles

1. Patient and encounter exchange across two FHIR implementations.
2. Laboratory result exchange across HL7 Version 2 and FHIR.
3. Clinical research extraction from FHIR into OMOP.
4. University clinical-placement evidence with strict consent boundaries.
5. Research dataset publication using FAIR metadata and provenance.

Clinical meaning must be approved by delegated clinical authorities. Technical maintainers alone cannot approve clinical semantics.
