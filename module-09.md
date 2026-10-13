# Module 9: India AI Governance Guidelines and the Global Landscape

## Learning Objectives
- Summarise the MeitY India AI Governance Guidelines and their core principles.
- Describe the institutional structure supporting AI governance in India.
- Identify the practical expectations placed on organisations under the guidelines.
- Explain how the Digital Personal Data Protection Act, 2023 (DPDPA) intersects with AI systems.
- Recognise the role of sectoral regulators in India and the broader global regulatory patchwork.

> **Note:** India's AI governance guidelines and institutional structures are an evolving policy area. Confirm current details, institutional names, and obligations against official MeitY publications and current legal counsel before relying on them for compliance decisions.

---

## 9.1 MeitY India AI Governance Guidelines: Core Principles

India's Ministry of Electronics and Information Technology (MeitY) has articulated an approach to AI governance centred on a "pro-innovation, pro-safety" philosophy — encouraging AI adoption and economic growth while establishing guardrails for trust and accountability. The guidelines are built around principles including:

- **People-centricity**: AI systems should be designed and deployed with the well-being, dignity, and interests of individuals and society as the central concern, not merely organisational or commercial efficiency.
- **Fairness**: AI outcomes should not produce unjustified or discriminatory disadvantage against individuals or groups — conceptually aligned with the fairness discussion in Module 5.
- **Accountability**: Organisations deploying or providing AI systems must be able to identify who is responsible for the system's behaviour and outcomes, echoing the accountability themes introduced in Module 1.
- **Transparency**: Meaningful information about the use and functioning of AI systems should be available to affected stakeholders, proportionate to risk and context.

Unlike the EU AI Act, India's approach (at the time of this course's writing) is primarily articulated through **guidelines and institutional frameworks** rather than a single, standalone, binding AI-specific statute with direct penalties — though it operates alongside binding sectoral law (such as the DPDPA, discussed in 9.4) that already applies to many AI use cases.

## 9.2 Institutional Structure

India's approach establishes (or proposes) a layered institutional architecture to operationalise these principles:

- **AI Governance Group (AIGG)**: A coordinating body intended to provide strategic direction on AI governance, bringing together government, industry, and expert perspectives to shape policy evolution.
- **Technology and Policy Expert Committee (TPEC)**: A technical and policy advisory body intended to provide specialist input into standards, risk assessment approaches, and emerging technical issues (e.g., how to evaluate foundation models, how to classify risk tiers for Indian use cases).
- **AI Safety Institute (AISI)**: Modelled conceptually on similar institutes established internationally (e.g., in the UK and US), an AI Safety Institute function is intended to support technical evaluation of advanced AI systems, safety research, and incident analysis.

**Governance implication:** This layered structure (strategic group → technical/policy committee → safety institute) mirrors a pattern seen in other jurisdictions: policy direction, technical standard-setting, and safety evaluation are kept as related but distinct functions, rather than concentrated in a single regulator.

## 9.3 Expectations Placed on Organisations

Even without a single binding AI statute carrying direct financial penalties (as of this course's writing), organisations operating in or serving India are expected to operationalise the guidelines through concrete practices:

- **Transparency reporting**: Documenting and, where appropriate, disclosing information about AI systems' purpose, data use, and risk mitigation measures to regulators, partners, or the public.
- **Grievance redress**: Establishing accessible channels through which individuals affected by an AI-driven decision can raise concerns or seek correction — directly analogous to the "contestability" principle from Module 5 and the lesson from the Module 3 public-administration case study.
- **Risk management**: Embedding structured risk identification, assessment, and mitigation processes across the AI lifecycle, consistent with frameworks such as the NIST AI RMF (Module 10).

**Practical note for multinational organisations:** Even where direct legal penalties are not yet codified specifically for AI, failure to meet these expectations can still translate into regulatory friction through sectoral regulators (9.5), data protection enforcement (9.4), and reputational/commercial risk — and is likely to inform the direction of future binding rules.

## 9.4 The Digital Personal Data Protection Act, 2023 (DPDPA) and Its Intersection with AI

The DPDPA is India's comprehensive data protection law, and it already applies directly to most AI systems that process personal data, independent of any AI-specific regulation:

- **Purpose limitation and consent**: Personal data used to train or operate an AI system must generally be collected and processed for a specified, lawful purpose, with appropriate consent or another valid legal basis — relevant to any AI system trained on customer, employee, or citizen data.
- **Data minimisation**: Organisations should only process personal data that is necessary for the specified purpose — a principle in tension with the common ML practice of collecting broad, exploratory datasets "in case they are useful."
- **Rights of data principals**: Individuals (termed "Data Principals" under the DPDPA) have rights including access, correction, and grievance redress regarding their personal data — which intersects directly with the contestability expectations described in 9.3 when an AI system has processed their data to produce a decision.
- **Significant Data Fiduciary obligations**: Organisations designated as handling data at a scale or sensitivity that qualifies them as a "Significant Data Fiduciary" face heightened obligations, including (depending on final rules) data protection impact assessments — directly relevant to high-risk AI deployments.

**Governance implication:** Even organisations waiting for India-specific binding AI law should treat the DPDPA as an *already-binding* floor of obligations for any AI system that touches personal data — which, in practice, is most commercially deployed AI.

## 9.5 Sectoral Regulators in India and the Wider International Regulatory Patchwork

Beyond MeitY's AI-specific guidelines and the DPDPA, AI systems in India are also subject to pre-existing sectoral regulation, for example:
- The **Reserve Bank of India (RBI)** for AI used in credit scoring, lending, and other financial services.
- The **Securities and Exchange Board of India (SEBI)** for AI used in trading, advisory, or capital markets contexts.
- The **Insurance Regulatory and Development Authority of India (IRDAI)** for AI used in underwriting and claims.
- Healthcare and telecom regulators for AI used in their respective sectors.

This "sectoral-plus-horizontal" pattern — a general AI governance framework layered on top of pre-existing sector-specific regulators — is common internationally, not unique to India:

- The **United States** currently relies primarily on a mix of executive orders, sectoral regulator guidance (e.g., financial regulators, the EEOC on employment discrimination), and state-level legislation (e.g., Colorado's AI Act), rather than a single comprehensive federal AI law.
- The **United Kingdom** has taken a "pro-innovation," principles-based approach, asking existing sectoral regulators to apply shared cross-cutting principles within their own remits, rather than creating a single new AI regulator.
- **China** has implemented targeted, binding rules for specific AI categories (e.g., generative AI services, recommendation algorithms, deep synthesis/deepfake technology) through distinct regulations rather than one omnibus law.
- International bodies (OECD, G7 Hiroshima Process, UN initiatives) provide non-binding principles that increasingly converge with, and influence, both the EU's and India's approaches.

**Governance takeaway:** Multinational organisations cannot comply with "AI regulation" as a single target. They must build a **regulatory map** per jurisdiction of operation, per sector, and per AI use case — recognising that horizontal AI-specific guidance (like MeitY's) and vertical sectoral regulation (like RBI's) both apply, often simultaneously, to the same system.

---

## Key Takeaways
- India's approach centres on people-centric, fair, accountable, and transparent AI, operationalised through the AIGG, TPEC, and AI Safety Institute rather than a single binding AI statute (as of this course's writing).
- The DPDPA already imposes binding obligations on AI systems that process personal data, regardless of AI-specific law.
- Sectoral regulators (RBI, SEBI, IRDAI, and others) apply pre-existing regulatory regimes to AI use cases within their domain.
- Globally, approaches range from the EU's comprehensive binding statute to the US's sectoral/state patchwork, the UK's principles-based regulator model, and China's targeted rules — organisations must map their own jurisdiction-by-jurisdiction, sector-by-sector exposure rather than assume one framework covers all operations.

## Discussion Prompt
For an AI use case operating in India, which sectoral regulator(s) would apply in addition to the general AI governance guidelines and the DPDPA?
