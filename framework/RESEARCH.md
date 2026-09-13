# Research

*Evidence base for the AI Threat Modeling Framework — Draft 0.1*


**Gap:** No broadly recognized, vendor-neutral framework focuses specifically on **how the values and practice of threat modeling must evolve for AI systems**.

That gap is what this initiative fills.

---

## Manifestos and declarations

| Initiative | Type | Contribution | Relationship |
|------------|------|--------------|--------------|
| [Threat Modeling Manifesto](https://www.threatmodelingmanifesto.org/) | Manifesto | Five values, principles, patterns, anti-patterns; methodology-agnostic | Closest structural precedent; extend spirit, do not replace |
| [Responsible AI Manifesto](https://responsibleaimanifesto.org/) | Manifesto | Definitions, openness, collaboration, operationalization | Useful for community framing; not adversarial threat modeling |
| [Asilomar AI Principles](https://futureoflife.org/open-letter/ai-principles/) | Declaration | Safety, transparency, human control, long-term risk | Ethical precedent; less operational for threat modeling |
| [Rome Call for AI Ethics](https://www.vatican.va/content/dam/wss/roman_curia/pontifical_academies/acdlife/documents/rc_pont-acd_life_doc_20202228_rome-call-for-ai-ethics_en.pdf) | Call | Human-centered values | Foundation, not security practice guide |
| [ML with Requirements Manifesto](https://ora.ox.ac.uk/objects/uuid%3Aa3a03c35-6726-441f-b22b-4bbab023db5c) | Academic | Requirements engineering for ML | Lifecycle and traceability; narrower scope |

---

## Frameworks and guidance (not manifestos)

| Resource | Contribution |
|----------|--------------|
| [OWASP AI and Agentic Threat Modeling](https://owasp.org/www-project-threat-modeling/resources/ai-tm) | AI-specific refresh triggers: tools, authority, instructions, models, memory, oversight, orchestration |
| [OWASP Multi-Agentic System Threat Modeling Guide](https://genai.owasp.org/resource/owasp-multi-agentic-system-threat-modeling-guide-v1-0/) | Multi-agent architecture, trust boundaries, emergent risks |
| [OWASP Top 10 for Agentic Applications](https://genai.owasp.org/resource/owasp-top-10-for-agentic-applications-for-2026/) | Agentic risk taxonomy: autonomy, tools, identity, memory, orchestration |
| [OWASP MCP Top 10](https://owasp.org/www-project-mcp-top-10/) | MCP risks: secrets, scope creep, tool poisoning, supply chain, injection, authorization, telemetry, shadow servers, context over-sharing |
| [NIST AI RMF](https://www.nist.gov/itl/ai-risk-management-framework) | Risk outcomes, trustworthiness, lifecycle governance |
| [NIST Generative AI Profile](https://doi.org/10.6028/NIST.AI.600-1) | GenAI risk categories |
| [MITRE ATLAS](https://atlas.mitre.org/) | Adversary tactics and techniques for AI systems |
| [Google SAIF](https://cloud.google.com/security/saif) | Secure-by-design across data, infrastructure, models, applications |
| [AWS Agentic AI Security Principles](https://aws.amazon.com/blogs/security/four-security-principles-for-agentic-ai-systems/) | Lifecycle security, traditional controls, deterministic external controls, earned autonomy |
| [MCP Authorization Security](https://modelcontextprotocol.io/specification/2026-07-28/basic/authorization/security-considerations) | Protocol authorization threats and requirements |
| [IETF MCP Security Considerations](https://www.ietf.org/archive/id/draft-mohiuddin-mcp-security-considerations-00.html) | Emerging MCP trust analysis (work in progress) |

---

## Gap analysis

| Need | Threat Modeling Manifesto | Responsible AI declarations | OWASP/NIST/MITRE frameworks | AI TM Framework |
|------|---------------------------|----------------------------|----------------------------|-----------------|
| Enduring practice values | ✓ | Partial | Partial | ✓ |
| AI-specific authority & autonomy | — | — | Partial | ✓ |
| Context-as-instruction | — | — | Partial | ✓ |
| Change/drift triggers for TM | — | — | Partial | ✓ |
| MCP/agentic focus | — | — | Partial | ✓ |
| Under 5-minute core text | ✓ | Varies | — | ✓ |
| Vendor-neutral | ✓ | ✓ | Mostly | ✓ |

---

## Positioning statement

**Not** a replacement for existing threat modeling.  
**Not** another AI risk list.  
**The missing bridge** between mature threat-modeling values and the realities of probabilistic, context-driven, tool-using, increasingly autonomous systems.

The strongest differentiating idea: an AI threat model must represent not only components and data flows, but also **influence, authority, autonomy, consequences, uncertainty, and change over time**.

---

## Evidence matrix

*Work in progress — populate during Phase 1 evidence collection*

### Template

For ongoing research, track sources with:

| Field | Purpose |
|-------|---------|
| Source | Stable link and citation |
| Source type | Manifesto, standard, framework, taxonomy, research, incident, regulation |
| AI scope | ML, GenAI, RAG, agentic, multi-agent, MCP, general |
| Lifecycle | Design, data, training, deployment, operation, retirement |
| Risk dimensions | Security, privacy, safety, misuse, fairness, resilience, human impact |
| Key principle | Concise paraphrase |
| Evidence strength | Standard, peer-reviewed, practitioner guidance, opinion |
| Manifesto relevance | Adopt, adapt, challenge, exclude |
| Licensing | Reuse limitations |

### Current entries

| Source | Type | AI Scope | Key principle (paraphrase) | Relevance | Evidence strength |
|--------|------|----------|----------------------------|-----------|-------------------|
| [Threat Modeling Manifesto](https://www.threatmodelingmanifesto.org/) | Manifesto | General | Continuous, collaborative threat modeling driven by design | Adopt spirit | Practitioner consensus |
| [OWASP AI Threat Modeling](https://owasp.org/www-project-threat-modeling/resources/ai-tm) | Guidance | GenAI, agentic | Refresh TM on tool, authority, memory changes | Adapt | Practitioner guidance |
| [OWASP MCP Top 10](https://owasp.org/www-project-mcp-top-10/) | Taxonomy | MCP | Tool poisoning, scope creep, shadow servers | Adapt | Practitioner guidance |
| [MITRE ATLAS](https://atlas.mitre.org/) | Taxonomy | AI-enabled | Adversary TTPs for ML systems | Crosswalk | Research + practitioner |
| [NIST AI RMF](https://www.nist.gov/itl/ai-risk-management-framework) | Framework | General AI | Govern, map, measure, manage risk | Crosswalk | Normative standard |
| [MCP Authorization Security](https://modelcontextprotocol.io/specification/2026-07-28/basic/authorization/security-considerations) | Specification | MCP | Authorization threats in protocol design | Adapt | Normative (protocol) |

*Contributors: add rows following the template above.*
