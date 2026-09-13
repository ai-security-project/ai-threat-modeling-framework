# AI Threat Modeling Canvas

*Workshop template — Draft 0.1*

## System overview

| Field | Your notes |
|-------|------------|
| System name | |
| Owner | |
| One-sentence purpose | |
| Consequence if it fails badly | |
| Autonomy tier (suggest / act with review / act within bounds / delegate) | |

---

## Section A: Socio-technical system map

List all components—not only the model.

| Component | Type | Trust level | Notes |
|-----------|------|-------------|-------|
| | User / human | | |
| | Model / agent | | |
| | Prompt / policy | | |
| | Retrieval / memory | | |
| | Tool / MCP server | | |
| | Identity / auth | | |
| | Downstream system | | |
| | Affected non-users | | |

**Principle check:** 1 (whole system), 10 (human impact)

---

## Section B: Influence — inbound

*What can influence the AI system?*

| Source | Channel | Trust | Adversarial scenarios |
|--------|---------|-------|----------------------|
| User input | Chat, API | | Injection, manipulation |
| Retrieved content | RAG, web | | Poisoning, indirect injection |
| Tool results | MCP, APIs | | Tool response manipulation |
| Memory | Session, long-term | | Memory poisoning |
| Inter-agent messages | Delegation | | Confused deputy |
| Tool metadata | Schemas, descriptions | | Tool poisoning |

**Principle check:** 2 (inbound influence), 5 (context as instruction)

---

## Section C: Influence — outbound

*What can the AI system influence?*

| Target | Action type | Max impact | Reversible? |
|--------|-------------|------------|-------------|
| | Read | | |
| | Write | | |
| | Execute | | |
| | Communicate | | |
| | Transact | | |
| | Delegate | | |

**Principle check:** 2 (outbound), 3 (authority), 8 (recovery)

---

## Section D: Authority and composition

| Identity / agent | Scopes and permissions | Combines with | Effective max harm |
|------------------|------------------------|---------------|-------------------|
| | | | |

**Composition question:** What becomes possible when tools A + B + C are chained?

**Principle check:** 3, 6, 7

---

## Section E: Enforcement boundaries

| Critical action | Enforced where? | Deterministic? | If model cooperates with attacker? |
|-----------------|-----------------|----------------|-----------------------------------|
| | | Yes / No | |

**Principle check:** 4 (reasoning vs enforcement)

---

## Section F: Threats and dispositions

| ID | Threat | Likelihood | Impact | Disposition | Owner | Due |
|----|--------|------------|--------|-------------|-------|-----|
| T1 | | | | Mitigate / Accept / … | | |

**Principle check:** 11 (uncertainty), 12 (action)

---

## Section G: Refresh triggers

| Trigger | Threshold | Last reviewed |
|---------|-----------|---------------|
| Model version change | Any prod change | |
| Retrieval corpus update | Any index change | |
| New tool or MCP server | Any addition | |
| Scope expansion | Any new permission | |
| Incident | Any material event | |
| Scheduled | Quarterly minimum | |

**Principle check:** 9 (change and drift)

---

## Section H: Anti-pattern self-check

Mark any that apply today:

- [ ] Model-in-a-Box
- [ ] Prompt-as-Policy
- [ ] Diagram Freeze
- [ ] Human Rubber Stamp
- [ ] Single-Agent Blindness
- [ ] Benchmark Absolutism
- [ ] Autonomy by Default
- [ ] Compliance Theatre
- [ ] Happy-Path Intent
- [ ] Unowned Residual Risk

---

## Workshop participants

| Name | Role | Present? |
|------|------|----------|
| | Security / TM | |
| | AI/ML | |
| | Platform / SRE | |
| | Product / domain | |
| | Privacy / legal | |
| | Safety / RAI | |

**Value check:** Multidisciplinary collaboration (Value 10)
