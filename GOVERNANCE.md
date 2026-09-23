# Governance

## Purpose

OSII governance protects three qualities: industry authority, technical openness and evidence-based decision-making.

## Core Council

The Core Council maintains the semantic kernel, common specifications, compatibility rules and cross-industry quality controls. It cannot unilaterally define industry-specific meaning.

Initial maintainers may act as the interim Core Council until a broader group is appointed. Interim status must be identified publicly.

## Industry Working Groups

Each industry pack is governed by its own working group. A group should include operating organisations, domain experts, data and architecture practitioners, policy or regulatory specialists where appropriate, technology providers and independent reviewers.

No single vendor, consulting organisation or product community may control an industry pack.

## Use-Case Teams

Small use-case teams create contracts and implementation evidence. Each team must define:

- the operational problem;
- current baseline;
- participating producers and consumers;
- minimum semantic scope;
- measures of success;
- known conflicts of interest; and
- publication plan.

## Decision process

Material decisions require an Architecture Decision Record in `decision-records/`. Each record must state the problem, alternatives, evidence, affected parties, conflicts of interest, decision and reconsideration conditions.

Consensus is preferred. Where consensus cannot be reached, maintainers may accept a decision after documenting objections. Affected industry working groups retain authority over their pack, subject to interoperability, licensing and quality requirements.

## Evidence and negative findings

Failed pilots, rejected mappings and evidence against a proposed design are valid outputs. Results must not be withheld because they are unfavourable.

## Releases

Specifications and industry packs use semantic versioning where practical. Breaking semantic changes require migration guidance. Deprecated concepts must remain traceable to their replacements.

## Conflicts of interest

Contributors must disclose commercial, employment or product interests that could reasonably affect a design or evaluation decision.

