# Module 5: Responsible AI Principles and Their Trade-offs

## Learning Objectives
- List the core Responsible AI principles and give a working definition of each.
- Compare demographic parity, equalised odds, and predictive parity, and explain why they are mathematically incompatible when base rates differ.
- Identify at least three genuine trade-offs between principles.
- Reframe "fairness" as a documented business decision rather than a technical switch.

---

## 5.1 Core Principles

Most Responsible AI frameworks converge on a similar core set of principles, even if the exact wording differs between NIST, ISO, OECD, and the EU AI Act:

| Principle | Working Definition |
|---|---|
| **Fairness** | The system does not produce unjustified disparate outcomes across groups defined by protected or sensitive characteristics. |
| **Transparency** | Stakeholders can understand, to a degree appropriate to the context, that an AI system is involved, and have access to meaningful information about how it works and why it produced a given output. |
| **Accountability** | A specific, identifiable person or function owns the consequences of the system's behaviour, and can be held responsible for it. |
| **Safety** | The system does not create unacceptable risk of physical, psychological, financial, or societal harm, including under adversarial or edge-case conditions. |
| **Privacy** | The system respects data protection law and the reasonable privacy expectations of the people whose data it processes. |
| **Human Oversight** | A human retains meaningful ability to monitor, intervene in, or override the system's operation. |
| **Contestability** | An affected person has a practical, accessible way to challenge or seek review of a decision made or materially informed by the system. |

These are not independent checkboxes — they interact with, and sometimes directly conflict with, one another. That tension is the subject of the rest of this module.

## 5.2 Definitions of Fairness

"Fairness" is not a single mathematical property; it is a family of different, competing definitions. The three most commonly cited in practice:

- **Demographic Parity (Statistical Parity):** The positive outcome rate (e.g., rate of loan approval) should be equal across groups, regardless of the groups' underlying qualification rates. $P(\hat{Y}=1 \mid A=a) = P(\hat{Y}=1 \mid A=b)$
- **Equalised Odds:** Among people who actually qualify (true positives) and among people who do not (true negatives), the model's error rates should be equal across groups. Formally, the true positive rate and false positive rate should both be equal across groups: $P(\hat{Y}=1 \mid Y=1, A=a) = P(\hat{Y}=1 \mid Y=1, A=b)$ and similarly for false positive rate.
- **Predictive Parity (Calibration):** Among people the model scores as positive (e.g., "high risk"), the actual rate of the outcome should be equal across groups: $P(Y=1 \mid \hat{Y}=1, A=a) = P(Y=1 \mid \hat{Y}=1, A=b)$

## 5.3 Why Fairness Definitions Are Mathematically Incompatible Where Base Rates Differ

This is one of the most important technical facts in Responsible AI, and it is frequently misunderstood as a solvable engineering problem rather than a mathematical constraint.

**The impossibility result:** If two groups have different *base rates* (different underlying prevalence of the actual outcome being predicted — e.g., different true default rates, different true reoffending rates), then it is mathematically impossible for a model (other than a perfect, error-free predictor) to simultaneously satisfy equalised odds and predictive parity. Satisfying one will necessarily violate the other, except in the trivial case of a perfectly accurate model or equal base rates.

This was the central, public controversy in the COMPAS recidivism-scoring debate: ProPublica showed the tool violated equalised odds (Black defendants who did not reoffend were flagged as high-risk at a higher rate than white defendants who did not reoffend), while the tool's vendor showed it satisfied predictive parity (within each risk score band, the actual reoffense rate was similar across races). **Both claims were correct — and simultaneously satisfying both was mathematically impossible once the two groups' base rates differed.**

**Governance implication:** You cannot ask a technical team to "just make it fair" in the abstract. You must specify *which* definition of fairness applies to *this* use case, and accept that choosing one definition means deliberately not satisfying another. This choice has to be made consciously, document the reasoning, and be owned by someone with the authority to accept the trade-off — not left to whichever default a modelling library happens to use.

## 5.4 Trade-offs Between Principles

Beyond fairness-versus-fairness tensions, the principles above regularly conflict with each other:

- **Transparency vs. Security:** Publishing full details of a fraud-detection model's logic helps affected persons understand decisions, but also hands attackers a blueprint for evading detection. Full transparency can directly undermine safety and security.
- **Accuracy vs. Privacy:** More and richer personal data generally improves model accuracy, but increases the privacy footprint and the potential harm of a data breach or misuse. Privacy-preserving techniques (aggregation, anonymisation, differential privacy) typically reduce accuracy to some degree.
- **Autonomy vs. Usefulness:** The more autonomously an agentic system acts (Module 11), the more useful and efficient it tends to be — but the less opportunity there is for meaningful human oversight before harm occurs. Maximising usefulness through autonomy directly erodes the practical strength of human oversight.
- **Explainability vs. Model Performance:** Simpler, inherently interpretable models (e.g., linear models, shallow decision trees) are easier to explain and audit, but often achieve lower predictive accuracy than complex models (deep neural networks, large ensembles), which in turn are harder to interpret.

## 5.5 Fairness as a Documented Business Decision, Not a Technical Setting

The single most important mindset shift in this module: **"Make the model fair" is not a valid instruction to give an engineering team**, because fairness is underdetermined — there are multiple legitimate, mutually exclusive mathematical definitions, and multiple legitimate trade-offs against other principles like accuracy, privacy, and transparency.

Instead, Responsible AI governance requires:
1. A named business or risk owner who **chooses** which fairness definition applies to this specific use case, based on its context, legal obligations, and stakeholder impact.
2. **Documentation** of that choice, the reasoning behind it, and the trade-offs knowingly accepted.
3. **Review and sign-off** by a function with the authority and standing to own that decision (e.g., a governance council, as covered in Module 12) — not a default left to whichever metric the development team found easiest to optimise.
4. **Periodic re-evaluation**, because a fairness definition appropriate at launch may no longer be appropriate as the deployment context, population, or regulation changes.

---

## Key Takeaways
- The core Responsible AI principles — fairness, transparency, accountability, safety, privacy, human oversight, contestability — regularly conflict with one another; none can be maximised in isolation.
- Demographic parity, equalised odds, and predictive parity are mutually incompatible whenever group base rates differ — this is a mathematical fact, not an engineering shortfall.
- "Fairness" must be defined, chosen, and documented as a conscious business and risk decision for each use case, with clear ownership — never left as an implicit default.

## Discussion Prompt
For a scoring or decision system you know of, which fairness definition (demographic parity, equalised odds, or predictive parity) is currently being used — explicitly or implicitly — and who made that choice?
