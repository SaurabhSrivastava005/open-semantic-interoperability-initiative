# Banking and Financial Services Standards Landscape

## Scope

This landscape covers financial concepts, payment messages, banking capabilities, contracts, regulatory reporting and governed data exchange.

## Standards and models

| Standard or framework | Primary purpose | Availability and boundary | SIEL treatment |
|---|---|---|---|
| [FIBO](https://spec.edmcouncil.org/fibo/) | Formal ontology for financial concepts and contracts | Open ontology artifacts and community governance | Profile selected concepts rather than importing the complete ontology |
| [BIAN](https://bian.org/) | Banking service domains and capability landscape | Public and membership-based assets | Record asset-level access conditions before reuse |
| [ISO 20022](https://www.iso20022.org/) | Financial business messages and repository | Public repository under ISO governance and terms | Create use-case profiles and mapping tests |
| [ACTUS](https://www.actusfrf.org/) | Algorithmic representation of financial contracts | Open standards and implementations under stated licences | Evaluate for contract cash-flow semantics |
| [FIX](https://www.fixtrading.org/standards/) | Electronic trading messages | Specifications and ecosystem governance | Use for capital-markets exchange profiles |
| [Financial Data Exchange](https://financialdataexchange.org/) | Consumer-permissioned financial data sharing | API specifications and certification ecosystem | Evaluate for open-finance profiles |
| [Open Banking standards](https://www.openbanking.org.uk/) | Regulated account and payment APIs | Jurisdiction-specific specifications and conformance | Implement as jurisdiction overlays |
| [LEI](https://www.gleif.org/) | Legal entity identification | Open identifier data and APIs | Use for organisation reconciliation |

## Priority SIEL profiles

1. Customer-permissioned account data exchange.
2. Payment initiation and status mapping.
3. Legal entity and counterparty reconciliation.
4. Financial contract representation across FIBO and ACTUS.
5. Regulatory reporting lineage.

Profiles must preserve jurisdiction, effective date, consent, permitted purpose and regulatory authority.
