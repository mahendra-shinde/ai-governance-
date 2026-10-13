# Module 8: The European Union AI Act

## Learning Objectives
- Explain the EU AI Act's risk-based classification system.
- Determine when the Act applies to an organisation outside the European Union (extraterritorial scope).
- Identify the obligations and dates attached to each phase of the Act's rollout.
- Avoid the most common misinterpretations of the compliance timeline.

> **Note:** This module summarises the structure and phased timeline of the EU AI Act, including adjustments introduced by the European Commission's "Digital Omnibus" simplification proposal. Regulatory details, interpretations, and deadlines are subject to ongoing amendment and official guidance; organisations must confirm current obligations against the official text and authoritative legal counsel before relying on any date or threshold for compliance planning.

---

## 8.1 Risk Classification

The EU AI Act takes a **risk-based, pyramid-shaped** approach: the regulatory burden on a system scales with the risk it poses to health, safety, and fundamental rights.

```
        ▲  Prohibited (banned outright)
       ╱ ╲
      ╱   ╲  High-Risk (heavy obligations: conformity assessment,
     ╱     ╲  technical documentation, risk management, human oversight)
    ╱       ╲
   ╱         ╲ Limited-Risk (transparency obligations only)
  ╱           ╲
 ╱_____________╲ Minimal-Risk (no mandatory obligations; voluntary codes encouraged)
```

- **Prohibited practices** (Title II, Art. 5): AI uses considered to pose unacceptable risk and banned outright — e.g., social scoring by public authorities, certain forms of real-time remote biometric identification in public spaces for law enforcement (with narrow exceptions), manipulative/subliminal techniques that materially distort behaviour causing harm, and exploitation of vulnerabilities of specific groups (children, persons with disabilities).
- **High-risk systems** (Title III, Annex III): Systems used in sensitive domains — employment and worker management, access to essential services (credit, insurance), education and vocational training, law enforcement, migration and border control, administration of justice, and critical infrastructure. These carry the heaviest obligations: a risk management system, data governance requirements, technical documentation, logging, human oversight design, accuracy/robustness/cybersecurity requirements, and conformity assessment before market placement.
- **Limited-risk systems**: Systems that pose a lower but non-trivial risk, primarily because they interact with or generate content for people. These are mainly subject to **transparency obligations** (Article 50) — informing people they are interacting with an AI system, or labelling AI-generated content — rather than the full high-risk compliance regime.
- **Minimal-risk systems**: The large majority of AI applications (e.g., spam filters, AI-enabled video games). No mandatory obligations beyond existing law, though voluntary codes of conduct are encouraged.

## 8.2 Extraterritorial Scope

A frequent misunderstanding is that the AI Act only applies to organisations established in the EU. In fact, like the GDPR before it, the Act has **extraterritorial reach**:

- It applies to Providers that place AI systems on the market or put them into service in the EU, **regardless of where the Provider is established**.
- It applies to Providers and Deployers located outside the EU **if the output produced by the AI system is used in the EU**.
- It applies to Deployers that have their place of establishment, or are located, within the EU.

**Practical implication:** An organisation headquartered entirely outside the EU, with no EU office, can still fall within scope simply by (a) selling an AI-enabled product to EU customers, or (b) having an AI system's output used by anyone within the EU — for example, a resume-screening model built outside the EU but used to evaluate EU-based job applicants.

## 8.3 Prohibited Practices and AI Literacy Obligations — Applicable from February 2025

The first obligations under the Act to take effect were:
- **Prohibited practices (Article 5)** became enforceable, banning the unacceptable-risk uses described above.
- **AI literacy obligations (Article 4)** require Providers and Deployers to ensure, to the best extent possible, that their staff and others dealing with the operation and use of AI systems have a sufficient level of AI literacy, taking into account their technical knowledge, experience, education, and the context in which the AI systems will be used.

This early date signals a deliberate regulatory choice: ban the clearest harms and mandate basic organisational competence first, before the heavier technical obligations phase in.

## 8.4 General-Purpose AI Model Obligations — Applicable from August 2025

Obligations specific to **General-Purpose AI (GPAI) models** — including most foundation models and large language models — came into force, including:
- Technical documentation requirements for GPAI model providers.
- Obligations to provide information and documentation to downstream providers who integrate the GPAI model into their own systems.
- A copyright-related obligation to put in place a policy to comply with EU copyright law, including with respect to text and data mining.
- Additional obligations for GPAI models classified as carrying **systemic risk** (generally very large, highly capable models), including model evaluation, adversarial testing, incident reporting, and cybersecurity protections.

## 8.5 Article 50 Transparency Obligations — Applicable from August 2026

Article 50 introduces specific transparency duties aimed at limited-risk systems that interact directly with people or generate synthetic content:
- **Chatbot disclosure**: Providers must ensure natural persons are informed they are interacting with an AI system, unless this is obvious from the circumstances.
- **Deepfake labelling**: Deployers of AI systems generating or manipulating image, audio, or video content that constitutes a "deepfake" must disclose that the content has been artificially generated or manipulated.
- **Synthetic content marking**: Providers of AI systems generating synthetic audio, image, video, or text content must ensure outputs are marked in a machine-readable format as artificially generated or manipulated.

These obligations connect directly to the generative AI risks discussed in Module 11 (hallucination, deepfakes) and the Case Study 1 and Case Study 4 incidents from Module 3.

## 8.6 Deferred Obligations Under the Digital Omnibus

In response to industry feedback about implementation readiness, the European Commission's **Digital Omnibus** simplification package deferred some of the heaviest high-risk obligations:

- **Annex III high-risk systems** (the employment, credit, education, law enforcement, etc. use cases listed above): core obligations deferred to **December 2027**.
- **Annex I embedded product AI** (AI safety components embedded in regulated products, such as machinery, medical devices, and toys, which already undergo third-party conformity assessment under existing EU product law): obligations deferred to **August 2028**.

**Why this matters:** The deferral does not mean these systems are unregulated in the meantime — prohibited practices, GPAI obligations, and Article 50 transparency rules still apply on their original schedule. It specifically delays the heaviest, most resource-intensive compliance regime (full high-risk conformity assessment) to give organisations and notified bodies more time to build the necessary infrastructure.

## 8.7 Penalty Framework

The Act uses a tiered penalty structure, broadly modelled on the GDPR's approach of scaling fines to global turnover:
- Violations of **prohibited practices**: up to **€35 million or 7% of total worldwide annual turnover**, whichever is higher.
- Violations of most other obligations (e.g., high-risk system requirements): up to **€15 million or 3% of total worldwide annual turnover**.
- Supplying **incorrect, incomplete, or misleading information** to authorities: up to **€7.5 million or 1% of total worldwide annual turnover**.
- Distinct, generally lower caps apply for SMEs and startups.

## 8.8 Common Misinterpretations of the Compliance Timeline

1. **"The Act doesn't apply yet because high-risk obligations were deferred."** Incorrect — prohibited practices, AI literacy, GPAI obligations, and Article 50 transparency rules are already in force or in force imminently on their original schedule; only Annex III/Annex I high-risk obligations were deferred.
2. **"We're not in the EU, so this doesn't apply to us."** Incorrect, given the extraterritorial scope described in 8.2 — use of output in the EU can trigger obligations regardless of where the organisation is based.
3. **"We bought the AI system from a vendor, so the vendor is responsible for everything."** Incorrect — Deployer obligations (human oversight, monitoring, informing affected persons) apply independently of Provider obligations, as discussed in Module 2 and Module 3 (Case Study 3).
4. **"This is a single compliance deadline, not a phased rollout."** Incorrect — the Act phases in obligations across at least four distinct dates (February 2025, August 2025, August 2026, and the deferred December 2027/August 2028 dates), each with different scope.

---

## Key Takeaways
- The Act classifies AI systems by risk: prohibited, high-risk, limited-risk, minimal-risk — with obligations scaled accordingly.
- Extraterritorial scope means non-EU organisations can still be in scope if their AI system's output is used in the EU.
- Obligations phase in across multiple dates: prohibited practices and AI literacy (Feb 2025), GPAI obligations (Aug 2025), Article 50 transparency (Aug 2026), with Annex III and Annex I obligations deferred to Dec 2027 and Aug 2028 respectively under the Digital Omnibus.
- Penalties scale with the severity of the violation and are calculated as the higher of a fixed amount or a percentage of global turnover.

## Discussion Prompt
Based on the systems discussed in Module 6, which risk tier would each likely fall into under the Act's classification — and which compliance deadline would apply to it?
