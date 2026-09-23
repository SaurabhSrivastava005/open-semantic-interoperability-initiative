# Standards and Open Initiatives Landscape

## Purpose

This document records major initiatives relevant to the Semantic Interoperability Evidence Lab, or SIEL. It explains what is available, how it can be used and where SIEL adds value.

The landscape is broad and changes continuously. This is a curated register of material initiatives, not a claim that every local, commercial or unpublished model has been captured.

## Classification of availability

The word "open" can describe different things. SIEL distinguishes them explicitly.

| Classification | Meaning |
|---|---|
| Open specification | The specification can be viewed and implemented publicly |
| Open model | The vocabulary, ontology or schema can be downloaded and reused under stated terms |
| Open-source implementation | Executable code is available under an open-source licence |
| Public reference model | The model is viewable, but use may be limited by licence or membership conditions |
| Conformance program | Tests or certification are available, sometimes only to members |
| Regulatory specification | A government-defined collection or exchange requirement, not necessarily an open-source model |

Availability must be verified for every profile. Public access does not automatically grant unrestricted reuse.

## Priority education, research and health frameworks

| Standard or framework | Domain or scope | Primary purpose | SIEL treatment |
|---|---|---|---|
| CEDS, Common Education Data Standards | Early learning, K-12, postsecondary, adult education and workforce | Unified vocabulary, common definitions and reference models for reporting, integration and exchange | Reuse definitions where terms permit, map sector transitions and avoid recreating an education-wide dictionary |
| Project Unicorn | Primarily K-12 interoperability adoption | Improve secure data interoperability through an ecosystem pledge, rubrics, certification resources and procurement guidance | Reuse adoption and vendor-engagement practices; do not present it as a schema, API or event model |
| Ed-Fi | Primarily K-12 data integration | Open data standard, REST API specifications and technology suite for operational and analytical interoperability | Evaluate its CEDS-aligned model and APIs for school-to-tertiary transition use cases |
| FAIR Principles | Research, laboratories and digital research assets | Make data and metadata findable, accessible, interoperable and reusable by people and machines | Use as evidence and metadata quality principles; do not treat FAIR as a data model or API |
| HL7 and FHIR | Healthcare, EHR, academic medical centres, university health services and clinical research | Exchange clinical and administrative healthcare information using governed standards, modular resources and APIs | Use FHIR as an optional clinical overlay and retain relevant HL7 governance and implementation guides |

Project Unicorn and Ed-Fi are listed separately because they solve different parts of the problem. Project Unicorn advances ecosystem adoption and vendor accountability. Ed-Fi supplies a technical data standard, APIs and an implementation suite.

## 1. Cross-industry foundations

| Initiative | Steward | Primary focus | What is available | How SIEL uses it |
|---|---|---|---|---|
| [Open Semantic Interchange](https://open-semantic-interchange.github.io/osi-website/) | Open Semantic Interchange community | Exchange of semantic models across analytics, BI and AI platforms | Public specification work and GitHub repositories | Treat as a semantic model interchange candidate, not a competing initiative |
| [FIWARE Smart Data Models](https://smartdatamodels.org/) | FIWARE, IUDX, TM Forum, OASC and contributors | Harmonised models across smart domains | Open repositories, schemas, examples and JSON-LD contexts | Reuse suitable domain models and test portability |
| [Schema.org](https://schema.org/) | Schema.org community | Cross-domain vocabulary for entities, relationships and actions | Public vocabulary, extension process and machine-readable definitions | Source selected kernel concepts and web-facing mappings |
| [Open Data Contract Standard](https://bitol-io.github.io/open-data-contract-standard/) | Bitol community | Machine-readable data contracts | Apache 2.0 YAML specification, examples and supporting libraries | Adopt or profile instead of creating another generic contract format |
| [W3C Semantic Web standards](https://www.w3.org/2001/sw/wiki/Main_Page) | W3C | Semantic representation, linked data, vocabularies and queries | RDF, OWL, JSON-LD, SKOS, SPARQL and related recommendations | Use as the semantic foundation where appropriate |
| [SHACL](https://www.w3.org/TR/shacl/) | W3C | Validation of RDF graphs | Public recommendation and implementations | Express deterministic semantic conformance rules |
| [DCAT 3](https://www.w3.org/TR/vocab-dcat-3/) | W3C | Interoperable data catalogues | Public RDF vocabulary | Describe datasets, services and profile assets |
| [PROV-O](https://www.w3.org/TR/prov-o/) | W3C | Provenance | Public ontology and supporting specifications | Record the origin and transformation history of mappings and evidence |
| [ODRL](https://www.w3.org/TR/odrl-model/) | W3C | Permissions, prohibitions and duties | Public information model and vocabulary | Represent machine-readable usage policies where suitable |
| [FAIR Principles](https://www.go-fair.org/fair-principles/) | FAIR community | Findability, accessibility, interoperability and reuse of digital research assets | Guiding principles and implementation guidance, not a data model or exchange API | Apply to SIEL datasets, metadata, profiles and evidence packages, especially in research contexts |
| [Eclipse Semantic Modeling Framework](https://projects.eclipse.org/projects/dt.esmf) | Eclipse Foundation | Semantic aspect models and digital twins using SAMM | Open-source SDK, modelling language, validation and generation tools | Evaluate for asset-intensive industry profiles |
| [Eclipse Dataspace Components](https://projects.eclipse.org/projects/technology.edc) | Eclipse Foundation | Sovereign inter-organisational data sharing | Open-source components, architecture and protocol implementation | Provide exchange and policy-enforcement infrastructure beneath profiles |
| [Eclipse Dataspace Protocol](https://projects.eclipse.org/proposals/eclipse-dataspace-protocol) | Eclipse Foundation | Interoperable data-space interactions | Public specification project | Test contract negotiation and data-sharing interoperability |
| [Gaia-X](https://gaia-x.eu/) | Gaia-X European Association for Data and Cloud | Federated data ecosystems, trust and sovereignty | Architecture, trust framework and open implementations across projects | Reuse trust and federation patterns without duplicating them |
| [International Data Spaces](https://internationaldataspaces.org/) | IDSA | Sovereign data sharing and data spaces | Reference architecture, specifications and ecosystem assets | Evaluate policy and connector patterns |

## 2. Higher education and learning

Higher education has several partially overlapping layers. No single initiative covers institutional architecture, operational data, teaching and learning, mobility, credentials, research, regulatory reporting and AI context.

### 2.1 Enterprise and sector reference models

| Initiative | Geography | Primary focus | What is available | Key limitation or boundary |
|---|---|---|---|---|
| [CAUDIT Higher Education Reference Models](https://www.caudit.edu.au/communities/caudit-higher-education-reference-models) | Australia and international collaboration | Business, data, application and technology reference models | Versioned catalogues, diagrams and ArchiMate assets under CC BY-NC-SA 4.0 conditions and additional stated distribution restrictions | Useful as an external reference architecture, but it must not become a copied, bundled or mandatory dependency of SIEL |
| [UCISA capability work and CAUDIT collaboration](https://www.caudit.edu.au/resources/caudit-ucisa-joint-statement-reference-models/) | United Kingdom and Australasia | Harmonisation of higher education capability and data models | Public collaboration statements and sector models subject to their terms | Primarily architecture and capability planning |
| [European Higher Education Interoperability Framework](https://education.ec.europa.eu/focus-topics/digital-education/hub/workshops-and-working-groups/interoperability-framework) | European Union | Organisational, semantic and technical interoperability across institutions | Public framework and policy work | Framework-level guidance with implementation distributed across other initiatives |

#### CAUDIT HERM reuse boundary

CAUDIT HERM can inform SIEL, but its current terms can create future constraints for an openly licensed platform and for commercial adopters. The CAUDIT page states that the models are available under CC BY-NC-SA 4.0 and also states restrictions concerning commercial use, bundling, sublicensing and passing the models to other organisations.

| Proposed action | Risk | SIEL policy |
|---|---|---|
| Link to a named HERM version and describe its scope | Low | Permitted with accurate attribution and no claim of endorsement |
| Use HERM as a non-normative architectural reference | Low to moderate | Permitted when SIEL remains usable without HERM assets |
| Copy definitions, diagrams, catalogues or ArchiMate files into SIEL | High | Do not include without explicit written permission and licence review |
| Adapt, translate or redistribute HERM content in a SIEL profile | High | Treat as potential derivative work and require written permission and legal review |
| Bundle HERM assets into a hosted, vendor or commercial product | High | Do not do this under the currently stated terms without a separate agreement |
| Publish an independently authored mapping to HERM concepts | Moderate | Keep it optional, record provenance, avoid copied expression and review before release |

SIEL profiles must be independently authored, openly licensed and implementable without access to restricted HERM assets. A future partnership or written permission from CAUDIT may enable deeper integration. This section is project risk guidance, not legal advice.

### 2.2 Academic administration and data exchange

| Initiative | Primary focus | What is available | SIEL relevance |
|---|---|---|---|
| [1EdTech Edu-API](https://www.1edtech.org/standards/edu-api) | Exchange of core higher education enterprise data between SIS, LMS and other systems | Candidate specification, models and community work | Candidate source for enrolment, course and academic enterprise contracts |
| [PESC Approved Standards](https://pesc.org/approved-standards/) | Transcripts, admissions, test scores and education records | EDI, XML, JSON and document standards with governance through PESC | Candidate exchange formats and mappings for admissions and records |
| [Common Education Data Standards](https://ceds.ed.gov/) | Early learning, K-12, postsecondary, adult education and workforce vocabulary, data models and integration structures | Common definitions, vocabulary, integrated data store, warehouse model, tools and open-source community | Broad education dictionary and cross-sector reference source for reporting and exchange |
| [Project Unicorn](https://www.projectunicorn.org/) | K-12 education data interoperability and ecosystem adoption | Interoperability pledge, rubrics, certification resources, guidance and community programs | Adoption and procurement model; it is an initiative, not an API or data standard |
| [Ed-Fi Data Standard](https://docs.ed-fi.org/reference/data-exchange/data-standard/) | Primarily K-12 operational and analytical interoperability | CEDS-aligned open-source data standard, API specifications and technology suite | Useful for vendor integration, event and API patterns, and school-to-tertiary transitions |
| [Schools Interoperability Framework](https://www.a4l.org/page/SIFSpecifications) | School administration and data exchange | Specifications and ecosystem resources | Relevant at the school and transition boundary |

### 2.3 Teaching, learning and curriculum

| Initiative | Primary focus | What is available | SIEL relevance |
|---|---|---|---|
| [1EdTech LTI](https://www.1edtech.org/standards/lti) | Secure integration of learning tools with LMS and platforms | Specification, APIs, implementation guidance and certification | Tool interoperability and delegated launch context |
| [1EdTech CASE](https://www.1edtech.org/standards/case) | Competencies, standards, skills and learning outcomes | REST-based exchange specification and conformance resources | Curriculum, skills and outcome semantics |
| [1EdTech Caliper Analytics](https://www.1edtech.org/standards/caliper) | Learning activity and analytics events | Public specification and metric profiles | Learning-event evidence and analytics profiles |
| [1EdTech OneRoster](https://www.1edtech.org/standards/oneroster) | Rostering, courses, enrolments and grades | CSV and REST specifications with certification | School and learning-platform exchange |
| [1EdTech QTI](https://www.1edtech.org/standards/qti) | Assessment items, tests and results | Specification and implementation ecosystem | Assessment exchange and validation |
| [1EdTech Common Cartridge](https://www.1edtech.org/standards/cc) | Portable learning content | Open standard for learning resources and packages | Content portability |

### 2.4 Credentials, achievements and skills

| Initiative | Primary focus | What is available | SIEL relevance |
|---|---|---|---|
| [1EdTech Open Badges](https://www.1edtech.org/standards/open-badges) | Verifiable achievements and badges | Specification, certification and implementation ecosystem | Micro-credentials and portable achievement evidence |
| [1EdTech Comprehensive Learner Record](https://www.1edtech.org/standards/clr) | Portable learner achievements, competencies and experiences | Standard and certification ecosystem | Learner-owned and competency-rich records |
| [European Learning Model](https://esco.ec.europa.eu/en/about-esco/escopedia/escopedia/european-learning-model) | Learning opportunities, qualifications, accreditation and credentials | Multilingual model based on open standards and used by Europass | Strong semantic source for qualifications and credentials |
| [European Digital Credentials for Learning](https://europass.europa.eu/en/european-digital-credentials) | Tamper-evident digital learning credentials | Free issuer tools, credential infrastructure and ELM alignment | Credential trust, verification and mobility |
| [W3C Verifiable Credentials](https://www.w3.org/TR/vc-data-model-2.0/) | Cryptographically verifiable claims | Public W3C data model | Technical foundation for portable credentials |
| [Credential Transparency Description Language](https://credreg.net/ctdl) | Credentials, skills, pathways and quality information | Open vocabulary and registry ecosystem | Skills and credential discovery, especially in North America |

### 2.5 Mobility and academic results

| Initiative | Primary focus | What is available | SIEL relevance |
|---|---|---|---|
| [Erasmus Without Paper](https://erasmus-plus.ec.europa.eu/european-student-card-initiative/ewp/how-it-works) | Digital exchange for European student mobility | Network, API specifications and registry services | Cross-institutional mobility workflows |
| [EMREX](https://emrex.eu/) | Learner-controlled exchange of academic results | Open-source initiative, ELMO schemas and participating network | Transcript exchange and learner-controlled portability |
| [European Student Identifier](https://erasmus-plus.ec.europa.eu/european-student-card-initiative/card/esi) | Cross-border student identification | European identifier specification and ecosystem integration | Identity mapping across mobility systems |

### 2.6 Research and scholarly information

| Initiative | Primary focus | What is available | SIEL relevance |
|---|---|---|---|
| [CERIF](https://eurocris.org/services/main-features-cerif) | Research information systems | Formal model maintained by euroCRIS | Research entities, projects, outputs and organisational relationships |
| [VIVO](https://vivoweb.org/) | Researcher and scholarly activity ontology | Open-source platform and ontology | Research knowledge graphs and discovery |
| [ORCID](https://info.orcid.org/documentation/integration-guide/) | Persistent researcher identifiers | Public APIs and integration guidance under stated terms | Person identity reconciliation |
| [ROR](https://ror.org/) | Open organisation identifiers | Open registry, API and data dump | Institution identity reconciliation |
| [Crossref](https://www.crossref.org/documentation/retrieve-metadata/rest-api/) | Publication metadata and persistent identifiers | REST APIs and public metadata services | Publication and relationship evidence |
| [DataCite](https://support.datacite.org/docs/api) | Research dataset and output identifiers | APIs, metadata schema and public services | Dataset and research-output identity |
| [FAIR Principles](https://www.go-fair.org/fair-principles/) | Research data and digital research assets | Principles for making data and metadata findable, accessible, interoperable and reusable | Quality criteria for research metadata, provenance and machine-actionable evidence; not a schema or API |

### 2.7 Australian reporting and regulatory semantics

These are authoritative reporting specifications. They are not automatically reusable open-source semantic models.

| Initiative | Primary focus | What is available | SIEL relevance |
|---|---|---|---|
| [TCSI](https://www.tcsisupport.gov.au/) | Australian higher education, VET Student Loans, staff, applications and related reporting | Data element dictionary, reporting requirements, validations, file and system guidance | Authoritative Australian reporting semantics and validation rules |
| [Higher Education Data Collections](https://www.education.gov.au/higher-education-statistics/student-data) | National student, load and completion statistics | Reporting requirements and published statistical outputs | Reporting lineage and regulatory-use profiles |
| [AVETMISS](https://www.ncver.edu.au/rto-hub/what-is-avetmiss) | National VET data collections | Collection specifications, data definitions and validation support | Authoritative VET reporting profile |
| [USI](https://www.usi.gov.au/) | National learner identifier and transcript services | Government services, requirements and integration information | Identity and achievement reconciliation subject to legal controls |
| [CRICOS and PRISMS](https://www.education.gov.au/esos-framework) | International education provider, course and student-visa reporting | Regulatory requirements and government systems | International student compliance profiles |
| [TEQSA provider obligations](https://www.teqsa.gov.au/provider-registration/registered-providers/requirements-and-responsibilities-registered-providers-including-material-changes/annual-information-collection) | Higher education regulation and provider reporting | Guidance, collection requirements and regulatory material | Governance, evidence and compliance mappings |

## 3. Other industry initiatives

### 3.1 Healthcare and life sciences

| Initiative | Focus | Availability and use |
|---|---|---|
| [HL7 FHIR](https://hl7.org/fhir/) | Clinical and administrative data exchange for academic medical centres, university health services, EHR systems and clinical research | Public specification, modular resources, REST APIs, implementation guides and jurisdictional profiles; use as an optional clinical overlay rather than a general education model |
| [openEHR](https://specifications.openehr.org/) | Clinically governed health-record models and archetypes | Open specifications, archetypes and open-source implementations |
| [OMOP Common Data Model](https://ohdsi.github.io/CommonDataModel/) | Observational health analytics and research | Open model, vocabularies, tools and community through OHDSI |
| [SNOMED CT](https://www.snomed.org/) | Clinical terminology | International terminology with licensing conditions that vary by territory |

### 3.2 Financial services

| Initiative | Focus | Availability and use |
|---|---|---|
| [FIBO](https://spec.edmcouncil.org/fibo/) | Formal ontology for financial business concepts and contracts | Open GitHub repository, OWL artefacts and community process |
| [BIAN](https://bian.org/) | Banking service landscape and service domains | Public materials with additional membership-based assets and implementation ecosystem |
| [ACTUS](https://www.actusfrf.org/) | Algorithmic representation of financial contracts | Open standards and implementations under stated licences |
| [ISO 20022](https://www.iso20022.org/) | Financial message definitions and repository | Public repository access with ISO governance and terms |

### 3.3 Energy and utilities

| Initiative | Focus | Availability and use |
|---|---|---|
| [OSDU Data Platform](https://osduforum.org/) | Open energy data platform and definitions | Open-source platform with forum governance and industry implementations |
| [IEC Common Information Model](https://www.iec.ch/) | Electricity network and market information models | International standards, commonly subject to IEC licensing |
| [OpenADR](https://www.openadr.org/) | Automated demand response | Specifications, certification and open-source implementations |
| [Green Button](https://www.greenbuttonalliance.org/) | Customer energy usage data exchange | Standard and certification ecosystem |

### 3.4 Real estate, buildings and construction

| Initiative | Focus | Availability and use |
|---|---|---|
| [Industry Foundation Classes](https://www.buildingsmart.org/standards/bsi-standards/industry-foundation-classes/) | Built-environment and BIM information exchange | Open international standard with implementation ecosystem |
| [Brick Schema](https://brickschema.org/) | Building assets, systems, points and relationships | Open-source ontology and tooling |
| [RealEstateCore](https://www.realestatecore.io/) | Real-estate and building ontology | Open ontology, examples and tooling |
| [Project Haystack](https://project-haystack.org/) | Semantic tagging for building and IoT data | Open community specifications and tools |
| [Google Digital Buildings](https://google.github.io/digitalbuildings/) | Building and installed-equipment ontology | Apache-licensed ontology and toolset |

### 3.5 Manufacturing, automotive and supply chain

| Initiative | Focus | Availability and use |
|---|---|---|
| [Asset Administration Shell](https://industrialdigitaltwin.org/en/content-hub/aasspecifications) | Standardised digital representation of industrial assets | Public specifications and open implementations |
| [Catena-X](https://catena-x.net/) | Automotive data ecosystem, shared models and use-case standards | Open standards, semantic models and reference components |
| [Eclipse Tractus-X](https://projects.eclipse.org/projects/automotive.tractusx) | Open-source implementation foundation for Catena-X | Open-source components and reference implementations |
| [OPC UA](https://opcfoundation.org/about/opc-technologies/opc-ua/) | Industrial communication and companion information models | Specifications and certification subject to foundation terms |
| [GS1 EPCIS and CBV](https://www.gs1.org/standards/epcis) | Supply-chain visibility events and vocabularies | Public standards with GS1 governance |
| [UN/CEFACT](https://unece.org/trade/uncefact) | Global trade facilitation and semantic standards | Public recommendations, models and artefacts |

### 3.6 Government and public data

| Initiative | Focus | Availability and use |
|---|---|---|
| [NIEM](https://www.niem.gov/) | Cross-agency information exchange | Public model, tools and governance ecosystem |
| [DCAT-AP](https://interoperable-europe.ec.europa.eu/collection/semic-support-centre/solution/dcat-application-profile-data-portals-europe) | European data-catalogue application profile | Public specification and controlled vocabularies |
| [Interoperable Europe](https://interoperable-europe.ec.europa.eu/) | Public-sector interoperability | Frameworks, reusable solutions and community assets |
| [X-Road](https://x-road.global/) | Secure distributed data exchange | Open-source platform and governance model |

## 4. What the landscape reveals

The problem is not a lack of standards. The problem is fragmentation across six boundaries:

1. **Standards are organised by different units.** Some describe entities, others events, messages, APIs, credentials, architecture or regulatory collections.
2. **Availability differs.** A public webpage, open specification, reusable model and open-source implementation are not equivalent.
3. **The same concept has multiple authoritative representations.** Student, customer, asset, credential, organisation and location are defined differently across contexts.
4. **Implementation evidence is inconsistent.** Many initiatives publish specifications but not comparable time, cost, mapping accuracy or maintenance results.
5. **AI use is usually an extension, not the original design centre.** Existing standards rarely package the complete context, policy, provenance and uncertainty an AI agent needs.
6. **Cross-standard mappings are scattered.** Mappings are often local, undocumented, vendor-controlled or difficult to test.

## 5. How SIEL is different

SIEL is not another universal ontology, canonical data model, message standard or data-space protocol.

SIEL provides a unified implementation and evidence layer that:

- discovers and classifies existing standards;
- records licensing, governance, maturity and availability;
- selects authoritative sources for a defined use case;
- creates minimal Industry Interoperability Profiles;
- maps across existing models without replacing them;
- generates machine-readable contracts, context and validation;
- separates AI-proposed mappings from human-approved rules;
- tests profiles against multiple source structures;
- records failures, disputes and limitations;
- measures implementation and maintenance outcomes; and
- publishes comparable evidence before describing an approach as proven.

## 6. Relationship model

| Existing asset | SIEL action | SIEL does not do |
|---|---|---|
| Ontology or vocabulary | Reference, profile, map and test | Fork without need or claim ownership |
| API or message standard | Create use-case conformance profile and fixtures | Replace a mature exchange protocol |
| Data contract standard | Adopt and extend through a declared profile | Invent another generic contract syntax |
| Regulatory collection | Represent authoritative definitions and validation lineage | Reinterpret legal obligations without authority |
| Reference architecture | Connect capabilities and data concepts to executable profiles | Present architecture diagrams as implementation evidence |
| Dataspace connector | Attach semantic, policy and evidence profiles | Rebuild transport and connector infrastructure |
| AI mapping tool | Benchmark proposals and preserve human approvals | Treat probabilistic output as semantic truth |

## 7. Registry requirements

Every initiative record should eventually include:

- canonical name and steward;
- official source URL;
- scope and jurisdiction;
- artifact types;
- access and licensing classification;
- current version and release date;
- governance and contribution process;
- conformance or certification availability;
- implementation references;
- known overlaps and mappings;
- semantic authority level;
- evidence maturity level;
- AI suitability and limitations; and
- last verification date.

This register should become machine-readable and be updated through reviewed pull requests.
