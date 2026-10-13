# Module 4: Sources of AI Harm

## Learning Objectives
- Classify AI harm by its root source: data, model, deployment context, and human interaction.
- Explain proxy variables and indirect discrimination with concrete examples.
- Describe how scale changes the severity profile of deployment-context harm.
- Explain automation bias and why human oversight can fail even when nominally present.

---

AI harm does not come from a single cause. It is useful to decompose it into four sources, because each source requires a *different* control to mitigate it. A governance team that only checks "the data" will miss harms rooted in deployment or human interaction, and vice versa.

```
Data  →  Model  →  Deployment Context  →  Human Interaction
 │           │              │                    │
historical  metric        scale &            automation bias,
bias,       mis-spec,      context            ineffective
proxies     opacity,       mismatch           oversight
            brittleness
```

## 4.1 Harm Arising from Data

### Historical Bias
Training data is a record of the past, including the past's inequities. A hiring model trained on ten years of "successful hires" at a company that historically under-hired women into technical roles will learn to reproduce that pattern — not because the algorithm is prejudiced, but because it is faithfully learning the statistical pattern present in the data it was given.

### Unrepresentative Samples
If a medical imaging model is trained predominantly on data from one demographic group, its accuracy will typically degrade for groups underrepresented in the training set. The model is not "wrong" in a general sense — it is simply under-informed about populations it rarely saw.

**Key distinction:** Historical bias is bias that is *accurately* learned from a *biased world*. Sampling bias is *inaccuracy* caused by a *non-representative dataset*. Both produce discriminatory outcomes, but the fix is different: the first requires a decision about what *should* be true (a fairness intervention), while the second requires better data collection.

## 4.2 Proxy Variables and Indirect Discrimination

A **proxy variable** is a feature that is not itself a protected characteristic (such as race, gender, age, or disability) but is statistically correlated with one, such that the model can reconstruct the effect of the protected characteristic even when that characteristic is excluded from the input.

Common examples:
- **Postal/ZIP code** can act as a proxy for race or socioeconomic status.
- **Name** can act as a proxy for ethnicity or national origin.
- **Employment gaps** can act as a proxy for disability, pregnancy, or caregiving responsibilities.
- **Device type or browsing time patterns** can act as a proxy for age or income.

This is why "we don't use gender/race as an input" is **not** a valid fairness defence on its own — a theme already raised in the Case Study 2 welfare model (Module 3) and the Case Study 3 hiring tool (Module 3). Proxy-driven discrimination is sometimes called **indirect discrimination**, and most anti-discrimination law — independent of any AI-specific regulation — already prohibits it regardless of whether a human or a model produced the outcome.

## 4.3 Harm Arising from the Model

### Metric Mis-specification
Models are trained to optimise a specific, mathematically defined objective. If that objective is a poor proxy for the real-world goal, the model will optimise the metric perfectly while failing the actual goal. Example: a content-recommendation model optimised purely for "engagement time" may learn to surface outrage-inducing or extreme content, because that content keeps people watching — even though no one explicitly instructed it to do so.

### Opacity
Many high-performing models, especially deep neural networks, are not humanly interpretable in their internal reasoning. This "black box" quality makes it difficult to answer basic governance questions: *why* did the model produce this output, and *can we justify it* to an affected person or regulator?

### Brittleness
Models can perform well on data that resembles their training distribution and fail unpredictably, sometimes severely, when faced with inputs slightly outside that distribution (a different accent, a rare combination of features, an adversarially crafted input). This "brittleness" is a core reason robustness testing is a named requirement in frameworks such as the NIST AI RMF (Module 10).

## 4.4 Harm Arising from Deployment Context and the Effect of Scale

A model that is statistically "fine" in a lab setting can still cause large real-world harm because of *how* and *where* it is deployed:

- **Context mismatch.** A model trained and validated on one population or use case is deployed on a different one without re-validation (e.g., a credit model built for one country's financial behaviour applied in another market with different informal-economy patterns).
- **Scale.** As seen in Case Study 5 (Module 3), a 1% error rate is a minor quality issue at 100 decisions and a systemic scandal at 10 million decisions. Scale is a multiplier on harm, not just a multiplier on efficiency gains, and governance must size controls (monitoring frequency, audit sampling, contestability capacity) to the actual volume of decisions, not just the model's reported accuracy.
- **Feedback loops.** Automated decisions can change the very population the model later sees (e.g., people flagged as high-risk are denied opportunity, which then makes them look "higher risk" in the next retraining cycle), entrenching harm over time.

## 4.5 Harm Arising from Human Interaction

### Automation Bias
Automation bias is the well-documented human tendency to over-trust the output of an automated system, even when a reasonable person reviewing the underlying evidence independently would reach a different conclusion. People tend to defer to "what the system says" especially when they are under time pressure, poorly trained on the system's limitations, or penalised for slowing down a process.

### Ineffective Oversight
Human oversight is often present on paper but ineffective in practice. Common failure modes:
- **Rubber-stamping**: a human is nominally "in the loop" but has neither the time, information, nor incentive to meaningfully challenge the system's output.
- **Alert fatigue**: when a system over-flags, reviewers become desensitised and start approving flagged cases by default.
- **Asymmetric information**: the human reviewer sees only the model's output, not the underlying evidence or confidence level, making genuine review impossible.

This directly connects to Module 11's discussion of human-in-the-loop oversight for agentic AI, where the stakes of ineffective oversight are magnified because the system can take real-world actions, not just produce a recommendation.

---

## Key Takeaways
- AI harm has four distinct root sources — data, model, deployment context, and human interaction — and each needs a different mitigation.
- Excluding a protected attribute from a model does not prevent discrimination if proxy variables remain.
- Scale transforms small statistical error rates into large absolute harms.
- Human oversight only works as a safeguard if it is genuinely resourced, informed, and incentivised — not merely present in a process diagram.

## Discussion Prompt
Pick one AI system you are familiar with. For each of the four harm sources, identify one specific, concrete risk it could introduce — even if no incident has yet occurred.
