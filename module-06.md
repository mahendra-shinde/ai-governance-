# Module 6: Day 1 Review and Discussion

## Learning Objectives
- Consolidate the four sources of AI harm covered in Module 4 into a single working mental model.
- Apply the Day 1 material (Modules 1–5) to participant-identified, real AI use cases from their own organisations.

---

## 6.1 Consolidation of the Four Sources of AI Harm

Before moving into the regulatory and frameworks content of Day 2, it is essential to fix the Day 1 harm model firmly in place, because every later module — regulation, frameworks, generative/agentic risk, and governance design — is, at its core, a different answer to the same question: **"How do we control for these four sources of harm?"**

### The Four-Source Model (Recap of Module 4)

1. **Data** — historical bias and unrepresentative samples; proxy variables causing indirect discrimination.
2. **Model** — metric mis-specification, opacity, and brittleness.
3. **Deployment Context** — context mismatch and the amplifying effect of scale.
4. **Human Interaction** — automation bias and oversight that is nominal rather than effective.

### A Diagnostic Walkthrough

A useful exercise is to re-examine each Module 3 case study through this four-source lens, to confirm the model's explanatory power:

| Case | Primary Source(s) of Harm |
|---|---|
| Conversational AI misstatement | Model (opacity, ungrounded generation) + Human Interaction (no escalation path) |
| Welfare bias model | Data (proxy variables) + Model (metric mis-specification: optimised for fraud catch rate alone) |
| Hiring/screening discrimination | Data (historical bias, proxies) + Deployment Context (no re-validation on actual population) |
| Deepfake financial fraud | Deployment Context (verification channel assumed to be unforgeable) + Human Interaction (no out-of-band check) |
| Public administration automated harm | Deployment Context (scale) + Human Interaction (ineffective oversight, weak contestability) |

This confirms a key insight: **most real incidents are not caused by a single failure, but by the compounding of failures across two or more sources simultaneously.** Strong governance therefore cannot rely on a single control (e.g., "we tested for bias in the data") — it needs layered controls addressing all four sources.

## 6.2 Open Discussion on Participant-Identified AI Use Cases

This session is structured as a facilitated, interactive discussion rather than a lecture. Participants should come prepared to discuss one or more AI-enabled tools or workflows already in use, or under consideration, within their own function.

### Suggested Discussion Framework

For each participant-identified use case, work through the following questions as a group:

1. **Classification:** Is this a predictive system, a generative system, or an agentic system (Module 2)? What role does our organisation play — Provider, Deployer, or both (Module 2)?
2. **Harm sourcing:** Using the four-source model, where is this use case most exposed — data, model, deployment context, or human interaction?
3. **Principle trade-offs:** Which Responsible AI principles (Module 5) are most in tension for this specific use case? Has anyone explicitly chosen and documented a fairness definition (Module 5) for it?
4. **Case study parallels:** Does this use case most resemble any of the five Module 3 case studies in its risk profile? What specific lesson transfers?
5. **Immediate gap:** What is the single most glaring governance gap for this use case today — missing validation, missing oversight, missing contestability, or something else?

### Facilitator Notes
- Encourage participants to surface use cases they consider "low risk" or "not really AI" (e.g., a spreadsheet-based scoring rule, a vendor chatbot, an internal productivity copilot) — some of the highest-risk governance gaps hide in tools nobody has formally classified as "AI" yet.
- Resist the urge to resolve every identified gap in this session; the goal is surfacing and classifying, not remediating. Remediation design is the subject of Module 12.
- Capture the use cases and gaps raised here — they will be useful reference points throughout Day 2, particularly when working through the EU AI Act's risk classification (Module 8) and the AI governance function design (Module 12).

---

## Key Takeaways
- The four-source harm model (data, model, deployment context, human interaction) explains all five Module 3 case studies, usually through a *combination* of sources rather than a single cause.
- Layered controls addressing all four sources are necessary; no single control is sufficient.
- Translating Day 1 concepts onto participants' own real use cases is the critical bridge into Day 2's regulatory and governance-design content.

## Discussion Prompt
Of all the use cases discussed in this session, which one would you prioritise for a governance review first — and why?
