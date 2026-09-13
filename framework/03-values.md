# Chapter 3: Our Values

*The AI Threat Modeling Framework*

---

## How to read our values


We follow that tradition. The items on the right are not worthless. Teams under delivery pressure often choose them for understandable reasons. Our values state what should win when you must choose—or when you discover you have been optimizing for the wrong thing.

Each value below includes a short rationale and a question you can ask in your next review.

### Using these values in a workshop

A **values card sort** helps teams surface real priorities before diving into threats:

1. Print or share the ten values (left-hand column only—hide the "than…" comparison initially).
2. Ask each participant to rank their top three and bottom one.
3. Reveal the full comparative format. Discuss where rankings diverged and why.
4. Pick one tension (see "When values collide" below) relevant to your system and decide explicitly—not by default.

Fifteen minutes on values often saves an hour of arguing about controls nobody agrees on.

---

## Value 1

**Modeling behavior, authority, and consequences** over documenting architecture alone.

*Rationale:* Architecture diagrams describe structure. They do not describe what a system can actually do when models, tools, and context combine. A beautiful diagram can hide dangerous authority.

*Ask in review:* "If this diagram were perfect, would we still know the worst thing this system could do?"

---

## Value 2

**Evidence from evaluation and operation** over confidence based on intended behavior.

*Rationale:* Intended behavior is a hypothesis. Evaluation, monitoring, incidents, and red-team results are evidence—imperfect, but grounding.

*Ask in review:* "What would convince us we were wrong about this system's safety?"

---

## Value 3

**Deterministic boundaries for critical actions** over relying solely on prompts and model self-restraint.

*Rationale:* Prompts are instructions, not enforcement. When consequences are material—financial loss, data exfiltration, irreversible action—policy must be applied outside probabilistic reasoning.

*Ask in review:* "If the model cooperates with an attacker, what still stops the worst outcome?"

---

## Value 4

**Continuous, change-triggered threat modeling** over a one-time pre-release exercise.

*Rationale:* AI systems change when models, prompts, retrieval corpora, tools, scopes, and orchestration change. A threat model that is not refreshed becomes a historical document.

*Ask in review:* "What changed since we last threat-modeled this—and did that change trigger a review?"

---

## Value 5

**Human accountability and meaningful control** over performative approval checkpoints.

*Rationale:* A human "approve" button that reviewers cannot understand is not oversight. It is liability theater. Accountability requires comprehensible information and the power to intervene.

*Ask in review:* "Could a responsible human actually prevent or reverse a bad outcome with what we show them?"

---

## Value 6

**End-to-end system analysis** over evaluating the model in isolation.

*Rationale:* The model is one component in a socio-technical system. Tools, data pipelines, identity, infrastructure, business process, and people determine real-world risk.

*Ask in review:* "Are we threat-modeling a product, or only the model API we buy?"

---

## Value 7

**Explicit trust and delegation boundaries** over assumed trust between agents, tools, data, and users.

*Rationale:* Agents delegate. Tools inherit scopes. MCP servers join ecosystems mid-flight. Trust assumptions that are implicit become incidents that are surprising.

*Ask in review:* "Who does this component trust, for what, and what happens when that trust is wrong?"

---

## Value 8

**Abuse cases and affected-human perspectives** over developer-intent-only analysis.

*Rationale:* Attackers are creative. Users misuse systems. People who never log in still get harmed. Threat modeling only for the intended user on the intended path is incomplete.

*Ask in review:* "Who could be hurt by this system who is not in our primary user persona?"

---

## Value 9

**Reversible and observable actions** over autonomy without containment or recovery.

*Rationale:* Autonomy without attribution, interruption, and rollback is experimentation on production. High-impact systems need circuit breakers, not hope.

*Ask in review:* "If this goes wrong at 2 a.m., how do we detect it, stop it, and undo it?"

---

## Value 10

**Open, multidisciplinary collaboration** over security decisions made by a single specialist group.

*Rationale:* AI risk lives at the intersection of security, privacy, safety, ML engineering, product, legal, operations, and affected communities. One discipline cannot see the whole system.

*Ask in review:* "Who is not in the room whose absence will embarrass us later?"

---

## Values at a glance

| # | We value more… | Than… |
|---|----------------|-------|
| 1 | Behavior, authority, consequences | Architecture alone |
| 2 | Evaluation and operational evidence | Intended behavior |
| 3 | Deterministic boundaries | Prompts and self-restraint |
| 4 | Continuous, triggered modeling | One-time pre-release review |
| 5 | Meaningful human control | Performative approval |
| 6 | End-to-end system analysis | Model-in-isolation review |
| 7 | Explicit trust boundaries | Assumed trust |
| 8 | Abuse cases and affected humans | Developer intent only |
| 9 | Observable, reversible actions | Unbounded autonomy |
| 10 | Multidisciplinary collaboration | Single-group security decisions |

## When values collide

Values sometimes tension with each other. Monitoring improves detection but may affect privacy. Human oversight improves accountability but can be gamed or overwhelmed. Transparency helps reviewers but may expose sensitive context.

We do not pretend these tensions vanish. We insist they be **named, owned, and decided explicitly**—not resolved by default through whichever team shouts last.

Document the trade-off. Record who accepted residual risk. Revisit when the system or its consequences change.

### Worked examples

**Meaningful human control vs. reversible autonomy (Values 5 and 9)**

A fraud-detection agent flags transactions for human review. At peak volume, reviewers approve 90% within four seconds—Human Rubber Stamp in practice. The team faces a choice: add headcount and better review UX (Value 5), or reduce autonomy so fewer cases need human judgment—tightening deterministic rules and auto-denying borderline cases (Value 9).

*Resolution:* They chose a hybrid. High-confidence fraud auto-blocks with deterministic rules. Medium-confidence cases get a richer review interface with a 60-second minimum and one-click reversal. Low-confidence cases auto-approve within strict caps. The tension was documented; neither value "won" entirely—the trade-off was explicit.

**Operational evidence vs. privacy (Values 2 and 8)**

An enterprise assistant logs full prompts and retrieved documents for incident investigation—excellent operational evidence. The same logs contain employee health questions, salary discussions, and attorney-client material pulled from retrieval.

*Resolution:* Tiered logging. High-consequence tool calls get full context lineage. Routine queries get hashed retrieval IDs and redacted prompts. Security retains investigation capability without building a surveillance archive. Privacy and legal signed the retention policy; AppSec owns the redaction rules.

**Continuous modeling vs. delivery pressure (Values 4 and 10)**

A product team wants to ship a new MCP server before a quarterly business deadline. Security wants a full composition review that needs platform and legal in the room—three calendars, two weeks minimum.

*Resolution:* Fast-track path: ship read-only, internal-users-only with a 30-day cap, deterministic egress block, and a dated full review before expanding scope. Value 4 (continuous modeling) was not suspended—it was **scoped**: threat modeling continued, but the first iteration operated under provably low blast radius until the full multidisciplinary review completed.

---

**Previous:** [Chapter 2 — Why AI Changes Threat Modeling](02-why-ai-changes-threat-modeling.md) · **Next:** [Chapter 4 — Our Principles](04-principles.md)
