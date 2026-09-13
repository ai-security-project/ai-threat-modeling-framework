# Framework Crosswalks

*Mapping framework principles to external resources — Draft 0.1*

## Framework principles → OWASP AI Threat Modeling refresh themes

| Principle | OWASP AI TM refresh theme |
|-----------|---------------------------|
| 3 Authority | Tool and authority changes |
| 5 Context channels | Instruction and context changes |
| 6 Composition | Orchestration and multi-agent changes |
| 7 Autonomy | Oversight and autonomy changes |
| 8 Observation | Detection and recovery |
| 9 Change/drift | Model, memory, policy changes |

Source: [OWASP AI and Agentic Threat Modeling](https://owasp.org/www-project-threat-modeling/resources/ai-tm)

---

## Framework principles → OWASP MCP Top 10

| MCP risk | Principles | Values / anti-patterns |
|----------|------------|------------------------|
| MCP01 Sensitive secrets | 3, 4, 8 | Prompt-as-Policy |
| MCP02 Scope creep | 3, 7, 9 | Autonomy by Default |
| MCP03 Tool poisoning | 5, 6 | Model-in-a-Box |
| MCP04 Supply chain | 1, 9 | — |
| MCP05 Command injection | 4, 5 | Prompt-as-Policy |
| MCP06 Intent-flow subversion | 2, 5, 6 | Happy-Path Intent |
| MCP07 Weak authorization | 3, 4, 7 | Prompt-as-Policy |
| MCP08 Missing telemetry | 8, 11 | Compliance Theatre |
| MCP09 Shadow servers | 1, 7, 9 | Diagram Freeze |
| MCP10 Context over-sharing | 2, 5, 10 | Model-in-a-Box |

Source: [OWASP MCP Top 10](https://owasp.org/www-project-mcp-top-10/)

---

## Framework principles → NIST AI RMF functions

| NIST function | Framework alignment |
|---------------|---------------------|
| **Govern** | Values 5, 10; Principles 7, 11, 12 |
| **Map** | Principles 1, 2, 3, 6, 10 |
| **Measure** | Values 2; Principles 7, 11 |
| **Manage** | Principles 4, 8, 9, 12 |

Source: [NIST AI RMF](https://www.nist.gov/itl/ai-risk-management-framework)

---

## Framework principles → MITRE ATLAS (illustrative)

| ATLAS tactic category | Framework emphasis |
|-----------------------|-------------------|
| Reconnaissance | Principle 2 (inbound influence) |
| Resource development | Principle 1 (supply chain) |
| Initial access | Principles 5, 9 (context, change) |
| ML attack staging | Principles 5, 6 |
| Exfiltration | Principles 2, 3, 8 |
| Impact | Principles 8, 10 |

Use ATLAS for technique enumeration; use this framework for *how to think* before enumerating.

Source: [MITRE ATLAS](https://atlas.mitre.org/)

---

## Framework values → Threat Modeling Manifesto

| AI TM Framework | Threat Modeling Manifesto (inherited spirit) |
|-----------------|-----------------------------------------------|
| Continuous, triggered modeling | "A great threat model is built continuously" |
| Multidisciplinary collaboration | "Threat modeling is best done collaboratively" |
| Connect analysis to action | "Done well, threat modeling makes systems better" |
| End-to-end system | "Understanding the system" |

We extend—not replace—the original manifesto.

Source: [Threat Modeling Manifesto](https://www.threatmodelingmanifesto.org/)

---

## Patterns → AWS Agentic Security Principles

| AWS principle | Framework pattern / principle |
|---------------|------------------------------|
| Secure lifecycle | Principle 9, refresh triggers |
| Traditional controls still apply | Chapter 2 (what still holds) |
| Deterministic controls outside agent | Principle 4, Pattern 6 |
| Autonomy earned through evidence | Principle 7, Value 3 |

Source: [AWS Four Security Principles for Agentic AI](https://aws.amazon.com/blogs/security/four-security-principles-for-agentic-ai-systems/)
