# Implementation Guide

*How to apply the AI Threat Modeling Framework in your organization — Draft 0.1*

## Who should use this

Security champions, threat modelers, AI platform teams, and engineering leads adopting the framework without mandating a specific methodology.

## Step 1: Adopt the vocabulary

Share the [core framework](../README.md) with cross-functional stakeholders. Run a 30-minute read-and-react session:

- Which value resonates most?
- Which anti-pattern do we currently exhibit?
- Which principle would have changed our last major decision?

## Step 2: Select a pilot system

Choose one system with real authority (see [pilot scenarios in Chapter 7](07-putting-it-into-practice.md#pilot-scenarios)). Avoid pilots that are "just a chatbot with no tools" unless that accurately describes production.

## Step 3: Run a framework-aligned workshop

Use the [threat modeling canvas](threat-modeling-canvas.md). Required outputs:

1. Influence diagram (both directions)
2. Capability and authority map
3. Ranked threats with owners and dispositions
4. Refresh triggers documented

## Step 4: Close the loop

| Threat disposition | Required follow-up |
|--------------------|-------------------|
| Mitigate | Control + test + monitor |
| Avoid | Design change or scope reduction |
| Transfer | Insurance, contract, third-party assumption documented |
| Accept | Named owner, review date, rationale |
| Investigate | Spike with deadline |

## Step 5: Institutionalize refresh triggers

Embed [refresh-triggers.md](refresh-triggers.md) in change management. Link threat model versions to model IDs, prompt versions, tool manifests, and MCP configs.

## Step 6: Measure

Track pilot metrics from [Chapter 7](07-putting-it-into-practice.md):

- Threats missed by prior process
- Decisions changed
- Cross-team clarity rating
- Control testability

## Integration with existing methods

| Your method | Framework addition |
|-------------|-------------------|
| STRIDE | Add authority, context-injection, composition strands |
| PASTA | Add abuse cases for AI-specific attack paths |
| Attack trees | Include tool chains and delegation paths |
| OWASP ASVS / testing | Map controls to framework principles |

See [crosswalks.md](crosswalks.md) for framework mappings.

## Common organizational blockers

| Blocker | Response |
|---------|----------|
| "We already threat model" | Show diagram freeze or model-in-a-box anti-pattern |
| "AI team owns safety" | Security + safety + privacy in same session |
| "No time for another process" | 90-minute workshop + refresh triggers, not new bureaucracy |
| "Vendor says it's safe" | Principle 11: state uncertainty; request eval scope |

## Maturity model (informal)

| Level | Characteristics |
|-------|-----------------|
| 0 — Absent | No AI-specific threat modeling |
| 1 — Aware | Team has read framework; informal discussions |
| 2 — Practicing | Workshops, authority maps, documented triggers |
| 3 — Integrated | Triggers in change management; adversarial evals from threats |
| 4 — Optimizing | Feedback loops, measured outcomes, multidisciplinary by default |
