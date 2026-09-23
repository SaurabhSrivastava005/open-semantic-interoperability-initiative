# Semantic Interoperability Evidence Lab

## Founding Charter and Industry Model Blueprint

**Tagline:** Evidence before standards

**Version:** 0.2  
**Status:** Draft for public review  
**Proposed steward:** Open Intelligence Institute  
**Scope:** Cross-industry semantic interoperability  

## 1. Purpose

The Semantic Interoperability Evidence Lab, or SIEL, is an independent, open, industry-focused research and engineering initiative built around a practical question:

> How can organisations share trusted meaning across systems, companies and AI agents without forcing every participant to adopt one common physical data model?

SIEL will evaluate how existing standards, semantic models, data contracts and AI-assisted mappings perform in real implementation scenarios. Where gaps remain, it will develop and test modular, machine-readable components that are measurable through implementation.

The initiative begins without endorsing, comparing with or depending on any existing proprietary model or accelerator.

## 2. Problem Statement

Traditional common and canonical data model programs often attempt to standardise too much at once. They can become difficult to implement because industries differ in regulation, operating processes, terminology, risk and evidence requirements. Even organisations in the same industry frequently use different systems and interpret apparently similar concepts differently.

AI makes semantic interoperability more urgent. AI agents need more than table names and field definitions. They need context about provenance, authority, policy, quality, time, purpose, relationships and permitted use.

AI also creates an opportunity. It can assist with schema discovery, mapping and change analysis. It cannot be allowed to invent authoritative meaning or bypass accountable governance.

SIEL will combine stable shared semantics, industry-owned context, use-case data contracts and governed AI assistance.

## 3. Design Principles

1. **Start with an industry problem, not an enterprise ontology.**
2. **Standardise the minimum meaning required for interoperability.**
3. **Preserve legitimate differences between industries and organisations.**
4. **Separate semantic agreement from physical data storage.**
5. **Make definitions, policies and mappings machine-readable.**
6. **Use AI to propose and explain, not to become the authority.**
7. **Design every module for independent adoption.**
8. **Measure value through working implementations.**
9. **Publish failures and limitations as evidence.**
10. **Prefer evolution and versioning over forced universal consensus.**

## 4. The SIEL Industry Model

SIEL uses a six-layer model.

| Layer | Purpose | Ownership |
|---|---|---|
| 1. Semantic Kernel | Defines a small set of cross-industry concepts and rules | SIEL community |
| 2. Industry Semantic Pack | Captures the language, regulations and value chain of an industry | Industry working group |
| 3. Use-Case Contract | Defines the minimum information needed for a business exchange | Participating producers and consumers |
| 4. Source Mapping | Connects local applications and schemas to the contract | Implementing organisation |
| 5. Agent Context and Policy | Tells AI agents what information means and how it may be used | Data and policy owners |
| 6. Evidence and Conformance | Tests semantic accuracy, interoperability and operational value | Independent reviewers and implementers |

### 4.1 Semantic Kernel

The kernel contains only concepts that are stable enough to be useful across industries. Initial candidates include:

- Party;
- Person;
- Organisation;
- Role;
- Asset;
- Product or Service;
- Agreement;
- Location;
- Event;
- Activity;
- Obligation;
- Evidence;
- Decision;
- Outcome;
- Identifier;
- Classification;
- Time period; and
- Provenance.

The kernel does not attempt to describe every industry process. Its purpose is to provide consistent identity, relationships, provenance and policy anchors.

### 4.2 Industry Semantic Packs

Each pack extends the kernel with industry-specific meaning. A pack must include:

- industry value-chain map;
- priority business capabilities;
- regulated and authoritative concepts;
- core entities and relationships;
- industry events;
- shared classifications and reference data;
- policy and evidence requirements;
- semantic risks and disputed definitions;
- recommended use-case contracts;
- implementation examples; and
- conformance tests.

Industry packs remain independently versioned. A change in one industry must not force changes across the entire framework.

### 4.3 Use-Case Contracts

The primary unit of implementation is the use-case contract, not the complete industry model.

A contract identifies:

- the decision or process being supported;
- participating producers and consumers;
- minimum required concepts and attributes;
- authoritative sources;
- business and validation rules;
- service and quality expectations;
- privacy and security conditions;
- allowed purposes;
- event or API behaviour;
- change-management obligations; and
- measurable business outcomes.

### 4.4 Source Mappings

Each organisation retains control of its local schemas. Mappings record how local structures relate to an approved use-case contract. Mappings must distinguish:

- exact equivalence;
- broader or narrower meaning;
- conditional equivalence;
- derived value;
- transformation;
- local extension;
- unresolved conflict; and
- prohibited use.

### 4.5 Agent Context and Policy

AI agents receive governed context through a machine-readable manifest containing:

- definition and business purpose;
- owner and accountable authority;
- source and provenance;
- effective date and version;
- relationships and constraints;
- quality status;
- sensitivity classification;
- permitted and prohibited uses;
- applicable policy or regulation;
- approved transformations;
- uncertainty and known limitations; and
- escalation requirements.

### 4.6 Evidence and Conformance

Every specification must include tests. Conformance will be assessed at component level, not through an all-or-nothing certification.

## 5. Initial Industry Portfolio

SIEL should establish industry packs progressively. The initial portfolio is designed around sectors with high interoperability cost, strong governance requirements and clear operational use cases.

| Industry | Initial focus | Candidate first use case |
|---|---|---|
| Higher Education and VET | Learner, program, course, enrolment, achievement and evidence | Credit transfer and prior-learning recognition |
| Healthcare and Life Sciences | Patient, provider, encounter, observation, treatment and consent | Governed patient-summary exchange |
| Banking and Financial Services | Customer, account, product, transaction, exposure and obligation | Customer and risk-data reconciliation |
| Energy and Utilities | Customer, premise, meter, asset, usage, tariff and market event | Meter-to-bill traceability |
| Real Estate and Construction | Site, property, asset, project, contract, work package and inspection | Asset lifecycle handover |
| Government and Public Services | Person, entitlement, case, service, payment and evidence | Cross-agency eligibility verification |
| Manufacturing and Supply Chain | Product, material, supplier, order, shipment, asset and quality event | Product and supplier traceability |
| Retail and Consumer | Customer, product, offer, order, fulfilment, return and consent | Product and order interoperability |

This portfolio is not a commitment to build every pack simultaneously. Each pack must begin only when credible industry contributors and a testable use case are available.

## 6. Industry Pack Development Method

Each industry pack will follow the same gated process.

### Gate 1: Problem qualification

- identify a costly interoperability problem;
- confirm that more than one organisation experiences it;
- document the current workaround and baseline cost;
- name the decision or operational outcome affected; and
- confirm access to credible domain experts.

### Gate 2: Minimum semantic scope

- identify the smallest concepts required;
- record conflicting definitions;
- distinguish regulatory meaning from local convention;
- define authoritative ownership; and
- exclude concepts not required by the first use case.

### Gate 3: Contract and prototype

- publish the use-case contract;
- produce machine-readable schemas and context manifests;
- create synthetic test data;
- map at least two structurally different source systems; and
- implement deterministic validation.

### Gate 4: Independent pilot

- test with an organisation not responsible for designing the pack;
- measure implementation and change effort;
- record rejected or disputed mappings;
- compare with the organisation's simplest credible alternative; and
- publish results and limitations.

### Gate 5: Release and maintenance

- approve a versioned release;
- publish conformance fixtures;
- assign maintainers;
- establish compatibility and deprecation rules; and
- monitor operational use.

## 7. Required Open Deliverables

### 7.1 Semantic Context Manifest

A vendor-neutral, machine-readable specification for meaning, ownership, provenance, policy, quality and permitted use.

### 7.2 Mapping Record Specification

A standard for representing equivalence, transformation, conflict, evidence, confidence and human approval.

### 7.3 Use-Case Data Contract Template

A reusable contract covering semantics, schema, rules, service expectations, security, privacy and change management.

### 7.4 Industry Pack Template

A controlled structure ensuring every industry pack includes comparable definitions, governance, implementation guidance and tests.

### 7.5 AI Mapping Workbench

A reference implementation that can:

- profile schemas and metadata;
- propose candidate mappings;
- explain the basis of each proposal;
- detect ambiguity and semantic conflict;
- route material decisions for review;
- store approved mappings as versioned rules; and
- execute deterministic validation before publication.

### 7.6 Conformance and Evaluation Kit

Public fixtures, scoring rubrics, synthetic datasets and reproducible benchmarks.

### 7.7 Implementation Case Studies

Reports covering positive results, failures, rejected mappings, implementation effort, maintenance cost and business outcomes.

## 8. Evaluation Framework

Every industry pack and use-case contract will be assessed across the same dimensions.

| Dimension | Evaluation question |
|---|---|
| Time to value | How quickly did the implementation produce a usable outcome? |
| Adoption effort | What technical and organisational change was required? |
| Semantic accuracy | Was industry meaning preserved correctly? |
| Reuse | Did earlier work reduce the cost of later implementations? |
| Change resilience | What happened when a source schema, regulation or policy changed? |
| Governance overhead | How much review and maintenance was required? |
| Explainability | Could users understand and challenge mapping decisions? |
| Risk | What privacy, security, regulatory or operational exposure arose? |
| Portability | Could the contract work across products and organisations? |
| Business value | Did the implementation improve a measurable outcome? |

Results must be compared with the simplest credible alternative, including direct integration where appropriate.

## 9. Evidence Levels

| Level | Meaning |
|---|---|
| E0: Concept | Proposed but not implemented |
| E1: Prototype | Demonstrated using synthetic data |
| E2: Controlled pilot | Tested under representative industry conditions |
| E3: Independent implementation | Implemented by an organisation not responsible for its design |
| E4: Replicated result | Similar results observed across multiple organisations |
| E5: Operationally sustained | Used and maintained in production over a meaningful period |

An industry pack must not be described as an industry standard based only on conceptual work, prototypes or internally controlled pilots.

## 10. Governance Model

### 10.1 Core Council

The Core Council maintains the semantic kernel, common specifications, compatibility policy and cross-industry quality controls. It cannot unilaterally define industry-specific meaning.

### 10.2 Industry Working Groups

Each working group should include representatives from operating organisations, domain experts, architects, data practitioners, regulators or policy specialists where appropriate, technology providers and independent reviewers.

No single vendor or consulting organisation should control an industry pack.

### 10.3 Use-Case Teams

Small implementation teams develop and test individual contracts. Their work must be traceable to a real operational problem and explicit measures.

### 10.4 Transparent decisions

Material design decisions must record:

- the problem;
- alternatives considered;
- available evidence;
- affected industries and stakeholders;
- conflicts of interest;
- the decision; and
- conditions for reconsideration.

### 10.5 Right to publish negative results

Failed pilots and evidence against a proposed design are valid outputs. Publication must not depend on favourable findings.

## 11. Intellectual Property Boundary

### Open SIEL assets

- cross-industry specifications;
- approved industry semantic packs;
- templates and machine-readable schemas;
- synthetic datasets;
- generic reference implementations;
- validation and conformance utilities;
- public decision records;
- evaluation methods; and
- research findings.

### Contributor-controlled assets

- proprietary product schemas;
- confidential regulatory interpretations;
- client-specific mappings;
- deployment accelerators not explicitly contributed;
- commercial implementation playbooks; and
- restricted third-party standards content.

### Organisation-controlled assets

- operational data;
- local business rules and policies;
- security configuration;
- institution-specific mappings;
- sensitive metadata; and
- identifiable information.

## 12. Licensing Proposal

Subject to formal legal review:

- documentation, diagrams, templates and research publications: CC BY 4.0;
- generic software, schemas and validation tools: Apache License 2.0;
- third-party standards and externally owned content: excluded unless redistribution is explicitly permitted;
- initiative and industry-pack names and marks: governed through a separate trademark policy; and
- contributed material: accepted only where the contributor has authority to license it.

## 13. Repository Structure

```text
/
├── CHARTER.md
├── GOVERNANCE.md
├── CONTRIBUTING.md
├── CODE_OF_CONDUCT.md
├── LICENSES/
├── kernel/
├── specifications/
│   ├── semantic-context-manifest/
│   ├── mapping-record/
│   ├── use-case-contract/
│   └── industry-pack-template/
├── industries/
│   ├── higher-education-and-vet/
│   ├── healthcare-and-life-sciences/
│   ├── banking-and-financial-services/
│   ├── energy-and-utilities/
│   ├── real-estate-and-construction/
│   ├── government-and-public-services/
│   ├── manufacturing-and-supply-chain/
│   └── retail-and-consumer/
├── reference-implementation/
├── evaluation/
│   ├── fixtures/
│   ├── rubrics/
│   └── results/
├── decision-records/
└── docs/
```

## 14. First 90 Days

### Days 1 to 30: Establish the foundation

- publish the charter for public review;
- appoint the initial Core Council;
- publish the kernel selection criteria;
- complete the industry-pack and use-case-contract templates;
- establish contribution, intellectual-property and decision controls; and
- select no more than two initial industry pilots.

### Days 31 to 60: Build the first industry contracts

- qualify one use case in each selected industry;
- document existing approaches and baseline cost;
- define the minimum semantic scope;
- produce context manifests, mappings and synthetic fixtures;
- map two different source structures per use case; and
- implement conformance tests.

### Days 61 to 90: Test and publish

- execute comparative pilots;
- publish evidence, limitations and unresolved conflicts;
- revise or reject unsupported design assumptions;
- invite independent implementations;
- approve only components that satisfy release criteria; and
- publish the roadmap for additional industry packs.

## 15. Initial Success Criteria

SIEL will be considered successful in its first phase if it:

- publishes machine-readable specifications, not only conceptual material;
- creates one stable semantic kernel without expanding it into a universal ontology;
- delivers at least two industry-specific use-case contracts;
- maps structurally different source systems;
- completes at least one reproducible comparative experiment;
- attracts reviewers independent of the founding group;
- reports negative and positive findings transparently;
- demonstrates measurable implementation or maintenance improvement; and
- produces evidence strong enough to change an architectural decision.

## 16. Founding Principle

> Shared meaning should be precise enough to support trust, small enough to implement and flexible enough to respect industry context.
