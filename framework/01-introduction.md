# Chapter 1: Introduction

*The AI Threat Modeling Framework*

---

## A Tuesday that looked ordinary

A platform team shipped a small change: they updated the retrieval index for an internal assistant. No application code changed. The architecture diagram was identical. Security review had signed off three months earlier.

By Thursday, the assistant was quoting confidential compensation data in responses to unrelated questions. The threat model had described data flows between the app, the vector store, and the model API. It had not described what happens when retrieval boundaries shift silently, when embeddings surface documents the designers never intended to expose, or when a user asks an innocent question that routes through poisoned context.

Nobody had done anything reckless on purpose. The index rebuild was routine maintenance. The architecture diagram was still accurate. Security had reviewed the system—and reviewed the *wrong questions*.

The incident was not a novel zero-day. It was a threat-modeling gap. The team had modeled components. They had not modeled **influence, authority, drift, and consequence** across a system that learns its behavior from context.

That gap is why this framework exists.

---

## What this framework is

The **AI Threat Modeling Framework** is an open, vendor-neutral, methodology-agnostic statement of **values, principles, patterns, and anti-patterns** for anyone threat modeling AI-enabled systems.

It applies to:

- Predictive machine learning
- Generative AI and large language models
- Retrieval-augmented generation (RAG)
- Tool-using agents and autonomous workflows
- Multi-agent systems
- Model Context Protocol (MCP) clients, servers, and ecosystems
- Plugins, skills, memory systems, and orchestration layers

It addresses security, privacy, safety, misuse, resilience, and human consequences **together**—because in practice, they arrive together.

## What this framework is not

| This framework is | This framework is not |
|-------------------|----------------------|
| A shared foundation for practice | A replacement for risk assessment or red teaming |
| Compatible with STRIDE, PASTA, LINDDUN, ATLAS, OWASP | A declaration that one methodology is universally correct |
| Short enough to read in under five minutes (core text) | A product-specific control catalog |
| Supported by separate implementation guides | Another OWASP Top 10 or vulnerability enumeration |
| Honest about uncertainty and probabilistic behavior | A claim that guardrails or human approval solve every problem |

## Our promise

> A community-built foundation for understanding what AI systems can influence, what can influence them, what authority they can exercise, what can go wrong, and what evidence is needed to trust their operation.

## The gap we fill

As of 2026, the landscape contains mature foundations—but not this specific bridge:

| What exists | What it contributes | What it does not replace |
|-------------|--------------------|-------------------------|
| [Threat Modeling Manifesto](https://www.threatmodelingmanifesto.org/) | Enduring values for threat modeling practice | AI-specific reasoning about authority, context-as-instruction, and drift |
| [Responsible AI Manifesto](https://responsibleaimanifesto.org/) | Community behavior and responsible-AI framing | Adversarial threat modeling for operational systems |
| [NIST AI RMF](https://www.nist.gov/itl/ai-risk-management-framework) | Risk-management outcomes and governance | Concise practitioner values for threat modeling sessions |
| [MITRE ATLAS](https://atlas.mitre.org/) | Adversary tactics and techniques | Foundational principles for how to think before you enumerate |
| [OWASP AI Threat Modeling](https://owasp.org/www-project-threat-modeling/resources/ai-tm) | AI-specific threat categories and refresh triggers | A vendor-neutral framework stating enduring practice values |
| [OWASP Top 10 for Agentic Applications](https://genai.owasp.org/resource/owasp-top-10-for-agentic-applications-for-2026/) | Agentic risk taxonomy: autonomy, tools, identity, memory | Enduring values for how to think before you enumerate |
| [OWASP MCP Top 10](https://owasp.org/www-project-mcp-top-10/) | Protocol-specific risks: shadow servers, tool poisoning, scope creep | A methodology-agnostic statement of practice priorities |

We extend the spirit of prior work. We do not compete with it.

This framework is **compatible with** regulatory and governance frameworks such as the [EU AI Act](https://eur-lex.europa.eu/eli/reg/2024/1689/oj/eng) and [ISO/IEC 42001](https://www.iso.org/standard/42001)—it is not derived from them, and it does not replace legal advice or formal conformity assessment. It gives compliance and legal readers a shared vocabulary for threat modeling conversations that those frameworks expect organizations to conduct.

## Who should read this

If you build, secure, govern, audit, or are affected by AI-enabled systems, this framework is for you:

- Threat modelers and application security engineers
- AI/ML engineers and platform teams
- Red teamers and incident responders
- Privacy, safety, and responsible-AI specialists
- MCP and agentic-system builders
- Product owners, legal and compliance teams, and auditors
- Researchers, civil society, and communities impacted by automated decisions

You do not need permission from a single authority to use these ideas. You need judgment, evidence, and colleagues who see the system from different angles.

## How to read this document

| Chapter | Focus |
|---------|-------|
| [Chapter 2](02-why-ai-changes-threat-modeling.md) | Why traditional threat modeling must evolve |
| [Chapter 3](03-values.md) | What we prioritize when values conflict |
| [Chapter 4](04-principles.md) | Twelve principles that should change decisions |
| [Chapter 5](05-patterns.md) | Practices worth adopting |
| [Chapter 6](06-anti-patterns.md) | Failures we have seen too often |
| [Chapter 7](07-putting-it-into-practice.md) | Refresh triggers, pilots, and organizational adoption |

The [one-page core framework](../README.md) distills Chapters 3–6 for quick reference.

## A note on language

We write for practitioners, not for marketing decks. Where we say "agent," we mean any system component that plans, delegates, or acts with partial autonomy—not only autonomous agents in the hype-cycle sense. Where we say "model," we mean any learned or configured component whose behavior is not fully specified by deterministic code alone.

We use plain language on purpose. Jargon ages quickly. Principles should not.

## Terms we use precisely

A few words carry real weight throughout this framework. We define them here so later chapters can use them without re-explaining each time.

| Term | What we mean |
|------|--------------|
| **Authority** | Everything a system can actually do—credentials, scopes, tool access, and the actions those enable—regardless of what any diagram says it is supposed to do. |
| **Consequence** | The real-world effect of an action or output: a record changed, a message sent, a decision made, a person affected. |
| **Influence** | Anything that can change a system's behavior without a code change—prompts, policies, retrieved documents, tool descriptions, memory, or another agent's output. |
| **Drift** | Behavioral change over time that occurs without a corresponding code deploy—through model updates, retraining, retrieval-corpus changes, or accumulating context. |
| **Context channel** | Any path by which content reaches a model or agent—chat input, retrieved documents, tool results, images, audio, memory, or inter-agent messages. Each one is a potential instruction channel, not only a data channel (Principle 5). |
| **Composition** | The combined capability created when individually acceptable tools, agents, or permissions are used together—often exceeding what any single component's review considered (Principle 6). |
| **Autonomy tier** | A defined level of independent action (suggest only, act with review, act within bounds, delegate to other agents) that a system is authorized for, tied to evidence rather than granted by default (Principle 7). |

These terms recur from here forward. When we use them, we mean exactly this.

---

**Next:** [Chapter 2 — Why AI Changes Threat Modeling](02-why-ai-changes-threat-modeling.md)
