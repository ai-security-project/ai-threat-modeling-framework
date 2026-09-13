# The AI Threat Modeling Framework

*Shared values and principles for modeling threats in AI, agentic, and autonomous systems*

> A community-built foundation for understanding what AI systems can influence, what can influence them, what authority they can exercise, what can go wrong, and what evidence is needed to trust their operation.

---

## Introduction

We believe threat modeling is essential for building trustworthy AI-enabled systems. We have written this framework to share our values and principles for how that practice must evolve not to replace existing threat modeling, and not to become another vulnerability list.

We have come to value:

---

## Our Values

**Modeling behavior, authority, and consequences** over documenting architecture alone.

**Evidence from evaluation and operation** over confidence based on intended behavior.

**Deterministic boundaries for critical actions** over relying solely on prompts and model self-restraint.

**Continuous, change-triggered threat modeling** over a one-time pre-release exercise.

**Human accountability and meaningful control** over performative approval checkpoints.

**End-to-end system analysis** over evaluating the model in isolation.

**Explicit trust and delegation boundaries** over assumed trust between agents, tools, data, and users.

**Abuse cases and affected-human perspectives** over developer-intent-only analysis.

**Reversible and observable actions** over autonomy without containment or recovery.

**Open, multidisciplinary collaboration** over security decisions made by a single specialist group.

---

## Our Principles

1. **Model the whole socio-technical system** — Include users, models, prompts, data, retrieval, memory, tools, agents, protocols, infrastructure, people, downstream systems, and affected communities.

2. **Model both directions of influence** — Ask what can influence the AI system, and what the AI system can influence in turn.

3. **Treat authority as a primary asset and attack surface** — Document credentials, scopes, permissions, and the maximum consequence of combined capabilities.

4. **Separate reasoning from enforcement** — Do not depend on a probabilistic model to enforce critical authorization, isolation, or data-access boundaries.

5. **Assume every context channel can carry instructions** — Treat prompts, documents, tool results, memory, and inter-agent messages as potential instruction channels.

6. **Threat model emergence and composition** — Analyze risks created by chaining individually acceptable tools, agents, and data sources.

7. **Earn autonomy with evidence** — Increase autonomy only when evaluation, monitoring, and consequence analysis support it.

8. **Design for observation, interruption, and recovery** — High-impact actions must be attributable, detectable, interruptible, and reversible where feasible.

9. **Model change, drift, and decay** — Refresh the threat model when models, prompts, tools, scopes, data, or consequences change.

10. **Include misuse, failure, and human impact** — Consider malicious use, accidental failure, foreseeable misuse, and harm to people who never directly interact with the system.

11. **State uncertainty honestly** — Record assumptions, evidence gaps, and residual risk. A passing benchmark is evidence for a bounded claim, not proof of universal safety.

12. **Connect analysis to action** — Every material threat should lead to a decision: mitigate, avoid, transfer, accept with an accountable owner, or investigate further.

---

## Patterns We Encourage

- Capability and authority maps alongside architecture diagrams
- Agent-action inventories distinguishing read, write, execute, communicate, transact, and delegate
- Abuse-case workshops with security, privacy, safety, AI/ML, and operations specialists
- Versioned threat models linked to model, prompt, tool, and configuration versions
- Adversarial evaluations derived from threat scenarios
- Independent policy enforcement for high-consequence operations
- Runtime telemetry connecting intent, context, tool invocation, identity, and outcome
- Kill switches, credential revocation, containment, rollback, and incident playbooks
- Post-deployment feedback loops using incidents, near misses, and drift
- Explicit modeling of indirect and downstream harm

## Anti-Patterns We Reject

- **The Model-in-a-Box** — Evaluating the model while ignoring tools, data, people, and infrastructure
- **Prompt-as-Policy** — Treating system prompts as enforceable security boundaries
- **Diagram Freeze** — Assuming unchanged architecture means unchanged threat model
- **Human Rubber Stamp** — Approvals reviewers cannot meaningfully assess
- **Single-Agent Blindness** — Reviewing agents individually while ignoring delegation and composition
- **Benchmark Absolutism** — Treating a single score as proof of safety
- **Autonomy by Default** — Granting broad powers first and restricting after deployment
- **Compliance Theatre** — Artifacts that do not change architecture, controls, or operations
- **Happy-Path Intent** — Modeling only the intended user and intended task
- **Unowned Residual Risk** — Documenting risk without a decision-maker or review trigger

---

*This framework is a living document. Full chapters, rationale, examples, and implementation guidance are in the [framework chapters](framework/01-introduction.md).*

## Full chapters

The core framework above distills Chapters 3–6 for quick reference. Read the full chapters in order, or jump to what you need.

| Chapter | Title | Read time |
|---------|-------|-----------|
| [1. Introduction](framework/01-introduction.md) | Purpose, scope, and boundaries | ~3 min |
| [2. Why AI Changes Threat Modeling](framework/02-why-ai-changes-threat-modeling.md) | What is genuinely different | ~4 min |
| [3. Our Values](framework/03-values.md) | What we prioritize when trade-offs arise | ~3 min |
| [4. Our Principles](framework/04-principles.md) | Twelve enduring principles for practice | ~6 min |
| [5. Patterns We Encourage](framework/05-patterns.md) | Recommended practices that work | ~4 min |
| [6. Anti-Patterns We Reject](framework/06-anti-patterns.md) | Common failures to avoid | ~3 min |
| [7. Putting It Into Practice](framework/07-putting-it-into-practice.md) | Refresh triggers, pilots, and next steps | ~4 min |
| [8. Community Consultation](framework/08-community-consultation.md) | Discovery workshops and practitioner input | ~3 min |

---

## Why this exists

Traditional threat modeling still matters. But AI systems are not ordinary software with a model bolted on. Outputs are probabilistic. Behavior shifts when prompts, policies, retrieval sources, or providers change. Natural language acts as both data and instruction. Agents call tools, hold credentials, and delegate work. Authority can expand without an obvious architecture change.

There is a mature [Threat Modeling Manifesto](https://www.threatmodelingmanifesto.org/), strong responsible AI declarations, and excellent frameworks from OWASP, NIST, and MITRE. What is missing is a **vendor-neutral framework** that states how threat modeling itself must evolve for AI, agentic systems, and Model Context Protocol (MCP) ecosystems.

This project fills that gap.

## Initiative charter

### Purpose

Create an open, vendor-neutral, methodology-agnostic **AI Threat Modeling Framework** that helps practitioners reason about security, privacy, safety, misuse, and operational resilience across AI/ML, generative AI, agentic systems, multi-agent systems, and Model Context Protocol (MCP) ecosystems.

### Scope

The framework states enduring **values, principles, patterns, and anti-patterns**. It does not replace risk assessment, red teaming, safety evaluation, or detailed methodologies.

### Non-goals

- Replace the Threat Modeling Manifesto
- Become a vulnerability list or compliance checklist
- Declare one methodology universally correct
- Serve as a product-specific control catalog
- Claim certification or assurance status

### Expected outputs

| Output | Status |
|--------|--------|
| One-page core framework (this README) | Draft 0.1 |
| Full framework chapters | Draft 0.1 |
| Research landscape and evidence matrix | Draft 0.1 |
| Implementation guide and canvas | Draft 0.1 |
| Pilot examples (5 scenarios) | Draft 0.1 |
| Community consultation process | Planned |

### Decision process

- Rough consensus among maintainers and working-group leads
- Documented dissent for substantive disagreements
- Maintainers resolve time-sensitive deadlocks with public rationale
- Principle changes require community consultation and version increment

## Who this is for

- Security practitioners and threat modelers
- AI/ML and platform engineers
- Developers building agents, RAG systems, and MCP integrations
- Red teamers, privacy specialists, and safety teams
- Governance leaders, auditors, product owners, and affected communities

You do not need to adopt a specific methodology. This framework complements STRIDE, PASTA, LINDDUN, attack trees, misuse cases, [MITRE ATLAS](https://atlas.mitre.org/), and OWASP resources.

## Repository structure

```text
ai-threat-modeling-framework/
├── README.md                    ← Core framework and project home (you are here)
├── framework/                   ← Full chapters, research, and guidance
│   ├── 01-introduction.md
│   ├── 02-why-ai-changes-threat-modeling.md
│   ├── 03-values.md
│   ├── 04-principles.md
│   ├── 05-patterns.md
│   ├── 06-anti-patterns.md
│   ├── 07-putting-it-into-practice.md
│   ├── 08-community-consultation.md
│   ├── RESEARCH.md
│   ├── implementation-guide.md
│   ├── threat-modeling-canvas.md
│   └── crosswalks.md
└── translations/                ← Community translations
```

## Supporting material

| Resource | Description |
|----------|-------------|
| [Research](framework/RESEARCH.md) | Manifestos, frameworks, gap analysis, and evidence matrix |
| [Implementation guide](framework/implementation-guide.md) | How to apply the framework in your organization |
| [Threat modeling canvas](framework/threat-modeling-canvas.md) | Workshop template |
| [Crosswalks](framework/crosswalks.md) | Mapping to NIST AI RMF, MITRE ATLAS, OWASP |

### Pilot examples

Five walkthrough scenarios are in [Chapter 7 — Putting It Into Practice](framework/07-putting-it-into-practice.md#pilot-scenarios):

| Scenario | Section |
|----------|---------|
| Predictive ML for consequential decisions | [Pilot 1](framework/07-putting-it-into-practice.md#pilot-1-predictive-ml) |
| Enterprise RAG assistant | [Pilot 2](framework/07-putting-it-into-practice.md#pilot-2-enterprise-rag-assistant) |
| Customer-service agent with write access | [Pilot 3](framework/07-putting-it-into-practice.md#pilot-3-customer-service-agent) |
| Multi-agent workflow | [Pilot 4](framework/07-putting-it-into-practice.md#pilot-4-multi-agent-workflow) |
| MCP deployment | [Pilot 5](framework/07-putting-it-into-practice.md#pilot-5-mcp-deployment) |

## Relationship to prior work

This initiative extends the spirit of the Threat Modeling Manifesto and complements OWASP, NIST, MITRE ATLAS, and MCP security guidance. We engage with those communities and credit prior work explicitly. It does not replace prior work, duplicate OWASP Top 10 lists, or claim to be a compliance standard. It is a foundation for practice—a shared vocabulary for teams who need to reason about influence, authority, autonomy, consequences, uncertainty, and change over time.

## Contributing

Thank you for helping build a practitioner-led foundation for AI threat modeling.

Contributors are acknowledged in release notes. Substantive contributions may be listed in framework acknowledgments.



### How to contribute

1. **Read** the [framework chapters](framework/01-introduction.md) and the initiative charter above
2. **Open an issue** for bugs, ambiguities, or proposed changes
3. **Submit a pull request** with clear description and rationale
4. **Participate** in consultation sessions and pilot feedback

### What we welcome

- Wording improvements that preserve meaning
- Additional examples and pilot reports
- Translations (native-speaker reviewed)
- Crosswalk updates when external frameworks change
- Evidence and citations for claims
- Accessibility improvements

### What requires consultation

- Adding, removing, or materially changing values or principles
- Changing scope or positioning
- License changes

### Style guidelines

- Plain language accessible to multiple disciplines
- Technology-neutral where possible
- Decision-relevant: every statement should change practice or be clearly labeled as context
- Credit prior work with links
- No vendor product recommendations in core framework text


## License

This work is licensed under [LICENSE)](LICENSE.txt).

## Version

**Draft 0.1** — September 2026. Community consultation in progress.
# ai-threat-modeling-framework
