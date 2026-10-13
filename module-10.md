# Module 10: Frameworks and Standards

## Learning Objectives
- Explain the four functions of the NIST AI Risk Management Framework: Govern, Map, Measure, Manage.
- Describe ISO/IEC 42001 and the route to certification as an AI Management System.
- Summarise ISO/IEC 23894 and the OECD AI Principles.
- Apply criteria for selecting and combining frameworks for a specific organisation.

---

## 10.1 NIST AI Risk Management Framework (AI RMF)

The U.S. National Institute of Standards and Technology's AI Risk Management Framework is a voluntary, widely referenced framework structured around four core functions, intended to operate continuously and iteratively rather than as a one-time project:

- **Govern**: Establish and maintain the organisational culture, policies, and processes needed to manage AI risk — including defined roles, accountability structures, and risk tolerance — conceptually the foundation that everything else sits on. This function is cross-cutting: it should inform and be informed by the other three.
- **Map**: Establish the context for a specific AI system — its intended purpose, deployment setting, affected stakeholders, and the risks and benefits specific to that context. This is where a team documents "what is this system for, who does it affect, and what could go wrong" before deeper risk measurement begins.
- **Measure**: Analyse, assess, benchmark, and monitor AI risk using appropriate quantitative, qualitative, or mixed methods — including testing for bias, robustness, accuracy, and other properties identified during Map.
- **Manage**: Allocate resources to prioritise and respond to identified risks on an ongoing basis — deciding which risks to mitigate, transfer, accept, or avoid, and tracking the effectiveness of those decisions over time.

```
   ┌───────────────── GOVERN (cross-cutting) ─────────────────┐
   │                                                            │
   │   MAP  ──────────▶  MEASURE  ──────────▶  MANAGE           │
   │   (context)         (assess & test)       (respond & track) │
   │                                                            │
   └────────────────────────────────────────────────────────────┘
```

**Why it matters:** The AI RMF is deliberately framework-agnostic and non-prescriptive about specific metrics or thresholds, making it a popular *foundation* for building an internal AI risk program — but it does not, by itself, satisfy a certification requirement the way ISO/IEC 42001 can.

## 10.2 ISO/IEC 42001: The AI Management System and the Route to Certification

ISO/IEC 42001:2023 is the first international standard specifying requirements for an **AI Management System (AIMS)** — structured analogously to other ISO management system standards such as ISO 27001 (information security) and ISO 9001 (quality management).

Key characteristics:
- **Management system structure**: Like other ISO standards, it follows the common "Annex SL" high-level structure — context of the organisation, leadership, planning, support, operation, performance evaluation, and improvement — making it easier to integrate with existing ISO-certified management systems a company may already run.
- **AI-specific controls**: Annex A of the standard provides a set of AI-specific control objectives and controls, covering areas such as AI system impact assessments, data management, third-party and customer relationships, and responsible use of AI throughout the lifecycle.
- **Certifiable**: Unlike the NIST AI RMF, ISO/IEC 42001 can be used as the basis for **third-party certification** by an accredited certification body — giving an organisation (and its customers, regulators, and partners) independently verified assurance that an AIMS is in place and operating effectively.

**Route to certification (typical path):**
1. Gap analysis against ISO/IEC 42001 requirements and Annex A controls.
2. Design and implementation of the AIMS (policies, risk assessment process, roles, documentation).
3. Internal audit and management review.
4. Stage 1 certification audit (documentation review).
5. Stage 2 certification audit (implementation evidence, interviews, sampling).
6. Certification issuance, followed by periodic surveillance audits and recertification (typically a three-year cycle, mirroring other ISO management system certifications).

**Governance implication:** Organisations seeking to demonstrate AI governance maturity to regulators, enterprise customers, or auditors — particularly where contracts or procurement processes require independent assurance — should treat ISO/IEC 42001 as the natural certification target, built on top of a NIST AI RMF-style internal risk process.

## 10.3 ISO/IEC 23894 and the OECD AI Principles

### ISO/IEC 23894: AI Risk Management
ISO/IEC 23894:2023 provides **guidance** on managing risks specifically associated with the development and use of AI, adapting the general risk management principles of ISO 31000 to the AI context. It is a guidance document, not a certifiable management system standard like ISO/IEC 42001 — the two are complementary: ISO/IEC 23894 can inform the risk management process that sits inside an ISO/IEC 42001-certified AIMS, or inside a NIST AI RMF-based program.

### OECD AI Principles
Adopted in 2019 (and updated since) and adhered to by dozens of countries, the OECD AI Principles were among the first intergovernmental standards for AI policy, establishing five values-based principles:
1. **Inclusive growth, sustainable development and well-being**
2. **Human-centred values and fairness**
3. **Transparency and explainability**
4. **Robustness, security and safety**
5. **Accountability**

The OECD Principles are **not a technical framework or management system** — they are high-level policy principles that have directly influenced the drafting of binding and semi-binding instruments covered elsewhere in this course, including the EU AI Act's principle set and the structure of India's MeitY guidelines (Module 9). Understanding the OECD Principles helps explain *why* so many seemingly independent national frameworks converge on a similar vocabulary of fairness, transparency, accountability, and safety.

## 10.4 Selecting and Combining Frameworks for an Organisation

No single framework is sufficient on its own — each operates at a different altitude:

| Framework | Type | Best Use |
|---|---|---|
| **OECD AI Principles** | High-level policy principles | Board-level framing; aligning language across jurisdictions |
| **NIST AI RMF** | Voluntary operational framework | Building the internal day-to-day risk management process |
| **ISO/IEC 23894** | Risk management guidance | Detailing the risk assessment methodology within that process |
| **ISO/IEC 42001** | Certifiable management system standard | Formalising and externally certifying the overall AI governance program |
| **EU AI Act / sectoral law** | Binding legal obligation | Setting the non-negotiable legal floor the program must meet |

**A practical selection approach:**
1. Start with binding legal obligations (EU AI Act, DPDPA, sectoral law) as the non-negotiable floor — frameworks cannot substitute for legal compliance.
2. Use the NIST AI RMF's Govern–Map–Measure–Manage structure as the operational skeleton for the internal program, since it is flexible and widely recognised.
3. Use ISO/IEC 23894 to strengthen the specific risk assessment methodology within that skeleton.
4. Pursue ISO/IEC 42001 certification where external assurance is commercially or contractually valuable (e.g., enterprise customers, regulated sectors, public tenders).
5. Use the OECD Principles as shared vocabulary when communicating with international regulators, partners, or boards spanning multiple jurisdictions.

This layered approach avoids the common mistake of treating frameworks as competing alternatives to choose between, when in practice they are designed to be **combined** at different levels of the governance stack.

---

## Key Takeaways
- NIST AI RMF structures risk management around Govern, Map, Measure, and Manage, and is voluntary and non-certifiable.
- ISO/IEC 42001 is the certifiable AI Management System standard, giving organisations a route to independently verified assurance.
- ISO/IEC 23894 provides AI-specific risk management guidance; the OECD AI Principles provide the shared high-level policy vocabulary behind many binding regimes.
- Frameworks should be combined, layered from legal floor → operational skeleton → risk methodology → certifiable management system → shared vocabulary, not treated as mutually exclusive choices.

## Discussion Prompt
If your organisation had to choose one framework to adopt in the next six months, which would deliver the most immediate risk reduction, and which would deliver the most external credibility?
