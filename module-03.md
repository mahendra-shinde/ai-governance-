# Module 3: Case Studies – How AI Fails in Practice

## Learning Objectives
- Analyse five real-world categories of AI failure and the organisational conditions that enabled them.
- Identify the common governance failure patterns that recur across unrelated incidents.
- Connect each case to the Responsible AI principles explored later in Module 5.

---

> **Note on use of these cases:** These case studies are presented as illustrative archetypes based on widely reported categories of AI incident (conversational AI liability, public-sector algorithmic bias, hiring discrimination claims, deepfake fraud, and large-scale automated decision harm). Facilitators should substitute or supplement with the most current, jurisdiction-relevant public incidents at delivery time, and participants should treat the lessons as transferable patterns rather than as a definitive legal record of any single event.

## Case Study 1: Conversational AI Misstatement and Organisational Liability

**What happened:** A customer-facing chatbot, deployed to answer policy and support questions, generated a plausible-sounding but incorrect answer about a refund or bereavement policy. The customer relied on the chatbot's statement. When the company later tried to apply the *actual* policy, the customer disputed it — and in disputes of this kind, tribunals and courts have held companies to the statements made by their own automated agents, reasoning that the company is responsible for the information it chooses to publish, regardless of the channel.

**Why it happened:**
- The chatbot was not constrained to a verified knowledge base; it generated free-text answers.
- There was no disclaimer, no escalation path, and no human review of high-stakes answers (e.g., ones involving money or bereavement).
- Nobody in the organisation treated "the chatbot's answer" as an equivalent of "a written company policy statement" for governance purposes.

**Governance lesson:** Generative AI outputs that touch policy, pricing, legal rights, or entitlements must be **grounded** in verified source documents (not free generation) and should trigger human review or clear, conspicuous disclaimers before being relied upon.

---

## Case Study 2: Bias Mitigation Failure in a Public-Sector Welfare Model

**What happened:** A government agency deployed a predictive model to flag welfare claims for fraud investigation. The model systematically over-flagged a specific demographic or geographic group, leading to disproportionate investigations, clawbacks, and hardship for already vulnerable populations. Attempts to "fix" the bias by removing the sensitive attribute from the model did not solve the problem, because proxy variables correlated with the protected group remained in the data.

**Why it happened:**
- The model was optimised for a narrow accuracy metric (fraud detection rate) without evaluating fairness metrics across subgroups.
- Removing the protected attribute created a false sense of fairness ("fairness through unawareness") while proxies did the same discriminatory work indirectly.
- There was no independent, pre-deployment impact assessment, and feedback loops from affected citizens were weak or absent.

**Governance lesson:** Fairness cannot be achieved by deleting a column from a dataset. It requires active measurement across defined fairness metrics (Module 5) and an impact assessment before deployment, especially in public-sector, high-stakes contexts.

---

## Case Study 3: AI Hiring and Screening Tools Under Discrimination Litigation

**What happened:** An automated resume-screening or video-interview-scoring tool was found, under legal challenge, to disadvantage candidates on the basis of age, disability, or other protected characteristics — even though the tool never used those characteristics directly as inputs. Plaintiffs and regulators argued that the tool's scoring correlated with protected characteristics through proxies (e.g., employment gaps, speech patterns, certain universities).

**Why it happened:**
- The vendor's claims of "bias-free" scoring were not independently validated by the deploying organisation.
- The deploying organisation (as **Deployer**) assumed compliance responsibility rested solely with the **Provider** (vendor) — a direct instance of the role confusion discussed in Module 2.
- No adverse-impact testing was conducted on the specific population actually being screened.

**Governance lesson:** Deployers cannot outsource their legal exposure to vendors. Independent validation, documented adverse-impact testing, and a clear human-in-the-loop override are required regardless of vendor assurances.

---

## Case Study 4: Deepfake-Enabled Financial Fraud and the Failure of Verification Controls

**What happened:** Fraudsters used AI-generated voice or video (a "deepfake") impersonating a senior executive to authorise a fraudulent financial transfer, in some reported incidents reaching tens of millions of dollars, by convincing an employee on a video call or phone call that they were receiving a legitimate instruction from leadership.

**Why it happened:**
- Verification procedures for high-value transactions relied on voice/visual recognition — exactly the channel that generative AI can now convincingly forge.
- There was no out-of-band, secondary verification step (e.g., a callback to a known number, a code word, a multi-person approval) that assumed voice/video could be faked.
- Staff had not been trained to treat urgent, pressure-laden instructions — even ones that "look and sound right" — as a red flag.

**Governance lesson:** As generative AI defeats traditional identity verification, controls must shift from "does this look/sound authentic" to "is this independently verifiable through an out-of-band channel." This is a direct and urgent implication of Module 11's deepfake discussion for operational risk and finance functions.

---

## Case Study 5: Large-Scale Automated Decision Harm in Public Administration

**What happened:** A government tax or benefits authority used an automated risk-scoring system to flag individuals for investigation or clawback of benefits/credits at national scale. Errors in the model — including reliance on weak or spurious risk indicators — led to wrongful accusations, demands for repayment, and reputational and financial harm to a large number of people, disproportionately affecting lower-income or minority populations, before systemic errors were acknowledged and remediated.

**Why it happened:**
- Scale meant that a modest false-positive rate still translated into a very large absolute number of harmed individuals.
- There was no effective, accessible channel for affected individuals to contest a decision early, cheaply, and quickly (the "contestability" principle from Module 5).
- Oversight bodies lacked visibility into the model's decision logic until harm had already accumulated over an extended period.

**Governance lesson:** At scale, even "acceptable" statistical error rates produce large absolute harm. Contestability mechanisms and early monitoring for disparate impact are not optional extras — they are what keeps a small error rate from becoming a systemic scandal.

---

## Common Governance Failure Patterns Observed Across the Five Cases

Across all five cases, the same structural weaknesses recur:

1. **No independent pre-deployment validation.** Organisations trusted vendor claims, internal developer assurances, or benchmark accuracy numbers without independent testing against their own population and use case.
2. **Metrics misaligned with real-world stakes.** Teams optimised for a single technical metric (accuracy, fraud-catch rate) while ignoring fairness, robustness, or downstream harm.
3. **Absent or weak human oversight.** Humans were either not in the loop at all, or were present only nominally ("rubber-stamping" automated outputs) — a pattern revisited in Module 11.
4. **No contestability or feedback channel.** Affected individuals had no fast, low-friction way to flag an error, allowing harm to compound before anyone noticed.
5. **Confusion about who is accountable.** In several cases, organisations assumed a vendor, a regulator, or "the algorithm" bore responsibility, when legal and reputational accountability remained with the deploying organisation.
6. **Treating AI governance as a one-time sign-off rather than a continuous control.** Each case involved an AI system that ran, unmonitored or under-monitored, for an extended period before the failure was detected.

---

## Key Takeaways
- Real AI harms recur in predictable patterns: ungrounded generative output, proxy-driven bias, outsourced accountability, defeated identity verification, and scale-amplified error rates.
- Every case traces back to a missing or under-resourced governance control, not merely "the algorithm being wrong."
- These patterns form the diagnostic checklist used throughout the rest of this course.

## Discussion Prompt
Which of the five failure patterns above is your organisation currently most exposed to, and why?
