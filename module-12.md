# Module 12: Building an AI Governance Function

## Learning Objectives
- Map governance gates onto the AI lifecycle.
- Apply the three lines of defence model to AI risk.
- Design an AI governance council with clear escalation paths and decision authority.
- Identify the core policy and documentation artefacts an AI governance function needs.
- Explain why third-party and procurement risk is the dominant source of organisational AI exposure.
- Design assurance, monitoring, grievance, and incident response mechanisms.

---

## 12.1 The AI Lifecycle and the Placement of Governance Gates

AI governance works best when controls are placed as **gates** at defined lifecycle stages, rather than as a single end-of-process sign-off. A typical lifecycle:

```
Ideation/Use Case → Design & Data → Build & Validate → Pre-Deployment Review
   → Deployment → Monitoring & Review → Retirement/Decommission
```

Recommended gates:
1. **Ideation/Use Case gate**: Register the proposed use case in the AI registry (12.4); classify its risk tier (echoing the EU AI Act's risk classification, Module 8) and identify role (Provider/Deployer, Module 2) before any build work begins.
2. **Design & Data gate**: Review data sourcing, lawful basis, and known bias/proxy risks (Module 4) before model development proceeds.
3. **Build & Validate gate**: Require documented testing against accuracy, fairness (with an explicitly chosen definition, Module 5), robustness, and security criteria.
4. **Pre-Deployment Review gate**: A named governance body (12.3) formally reviews the completed impact assessment and documentation and authorises deployment, potentially with conditions.
5. **Deployment gate**: Confirm monitoring, logging, and human oversight mechanisms are live before the system is exposed to real decisions or users.
6. **Monitoring & Review gate**: Periodic (and event-triggered) re-assessment as data drifts, usage scales, or context changes (Module 4's deployment-context harm).
7. **Retirement/Decommission gate**: Formal decommissioning, including data handling and dependency checks, when a system is withdrawn.

**Why gates, not a single review:** Module 3's case studies each involved a system that ran, under-monitored, for an extended period before harm was detected — a single pre-launch sign-off would not have prevented any of them. Gates at multiple lifecycle points create repeated opportunities to catch emerging risk.

## 12.2 Roles and Responsibilities: The Three Lines of Defence Applied to AI

The "three lines of defence" model, long used in financial and operational risk management, maps cleanly onto AI governance:

| Line | Who | AI Governance Role |
|---|---|---|
| **First line** | Business/product owners, data science and engineering teams | Own the AI system day-to-day; perform initial risk identification, build controls into design, operate within approved risk appetite (connects to Module 1's accountability map) |
| **Second line** | Risk, compliance, legal, and the AI governance function itself | Set policy and standards, provide independent challenge, review impact assessments, maintain the AI registry, monitor aggregate risk exposure |
| **Third line** | Internal audit | Provide independent assurance that first- and second-line controls are actually operating as designed, report directly to the board/audit committee |

**Common failure mode:** Collapsing the three lines — e.g., having the same team that builds a model also perform its only fairness validation — removes the independent challenge that makes the model meaningful. Each case in Module 3 involved, in some form, a missing or weak second-line challenge function.

## 12.3 The AI Governance Council, Escalation Paths, and Decision Authority

A cross-functional **AI Governance Council** (or equivalent committee) is the practical mechanism that gives the second line teeth. Typical composition includes representatives from: legal/compliance, risk, data science/engineering leadership, information security, data protection/privacy, procurement, and relevant business unit leadership — with clear executive sponsorship.

**Core responsibilities:**
- Approve or reject use cases at the Pre-Deployment Review gate (12.1).
- Own and periodically update the AI risk classification methodology and acceptable use policy (12.4).
- Serve as the escalation point for issues raised through monitoring (12.6) or incident response (12.6) that exceed first-line resolution authority.
- Report periodically to the board or a board risk committee on aggregate AI risk exposure.

**Escalation design principle:** Define, in advance, clear thresholds for what must escalate to the Council (e.g., any high-risk-tier system, any system affecting vulnerable populations, any incident involving regulatory exposure) versus what first-line teams can resolve independently — ambiguity here recreates the "who is accountable" confusion from Module 1 at the point it matters most.

## 12.4 Policy and Documentation

A functioning AI governance program is built on a consistent set of artefacts:

- **Acceptable Use Policy (AUP)**: Defines what AI tools and use cases are permitted, under what conditions, and what is prohibited — the primary lever against shadow AI (Module 11), provided it is paired with a usable sanctioned alternative.
- **AI Registry (Inventory)**: A living, centrally maintained record of every AI system in use (including shadow AI discovered through audit), its risk classification, role (Provider/Deployer), owner, and governance gate status. Without an accurate registry, none of the other controls in this module can be applied consistently — you cannot govern what you have not inventoried.
- **Model Cards**: Standardised, per-model documentation covering intended use, training data characteristics, performance across subgroups, known limitations, and the chosen fairness definition (Module 5) — giving downstream users and auditors a consistent reference point.
- **Impact Assessments**: A structured, documented evaluation of a system's likely effects on individuals and groups before deployment, directly analogous to a Data Protection Impact Assessment, and functionally similar to what the EU AI Act requires for high-risk systems (Module 8) and what India's guidelines encourage (Module 9).

## 12.5 Third-Party and Procurement Risk as the Dominant Source of Organisational AI Exposure

Most organisations do not build their own foundation models — they **buy or integrate** AI capability from vendors, cloud providers, and embedded features in existing software. This makes procurement the single most consequential control point in practice, for several converging reasons:

- As established in Module 2 and Case Study 3 (Module 3), being a **Deployer** does not eliminate an organisation's own legal obligations — yet procurement processes are frequently run as standard software purchases, without AI-specific due diligence.
- Vendors' claims about bias testing, data provenance, and copyright compliance (Module 11) are rarely independently verified before signing.
- AI capability is increasingly embedded *inside* other software (a CRM, an HR platform, a productivity suite) without being flagged as "an AI purchase" at all, so it bypasses AI-specific governance review entirely.

**Practical controls:**
- Extend procurement due diligence questionnaires to require evidence of bias testing, data lineage, security testing, and incident history for any tool with embedded AI.
- Require contractual provisions addressing liability allocation, audit rights, data handling, and incident notification obligations specific to AI functionality.
- Treat "AI capability added to an existing, already-approved tool" as a trigger for re-review, not an exemption from it.

## 12.6 Assurance, Monitoring, Grievance Channels, and AI Incident Response

- **Assurance**: Periodic internal and, where applicable (e.g., ISO/IEC 42001, Module 10), external audit against the governance framework's own stated controls — confirming gates are actually being applied, not merely documented.
- **Monitoring**: Ongoing, not one-time, tracking of model performance, fairness metrics across subgroups, data drift, and usage volume — sized to the deployment's actual scale, per the scale-amplification lesson of Module 4.
- **Grievance channels**: Accessible, low-friction mechanisms for affected persons to contest a decision or flag a concern — operationalising the contestability principle (Module 5) and directly addressing the gap identified in the Module 3 public-administration case study.
- **AI incident response**: A defined process — analogous to, and ideally integrated with, existing cybersecurity incident response — covering detection, containment, root-cause analysis (using the four-source harm model from Module 4), remediation, and regulatory notification where required (e.g., under the EU AI Act or DPDPA, Modules 8–9).

---

## Key Takeaways
- Governance gates placed across the full AI lifecycle catch risks that a single pre-launch review would miss.
- The three lines of defence — business/engineering, risk/compliance/governance, internal audit — must remain genuinely independent to provide real challenge.
- An AI Governance Council with clear escalation thresholds and decision authority converts distributed accountability (Module 1) into an operating structure.
- Core artefacts — acceptable use policy, AI registry, model cards, impact assessments — are the documentation backbone of the whole program.
- Procurement and third-party risk is the dominant real-world AI exposure for most organisations, because most AI is bought or embedded, not built in-house.
- Assurance, monitoring, grievance channels, and incident response must run continuously, not as one-time project deliverables.

## Discussion Prompt
Using your organisation's current structure, sketch who would sit on an AI Governance Council today. Is there a gap in representation (e.g., no information security voice, no business-unit voice) that would weaken its decisions?
