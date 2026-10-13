# Module 2: Foundations and Terminology

## Learning Objectives
- Distinguish Artificial Intelligence, Machine Learning and Deep Learning as nested concepts.
- Differentiate Foundation Models, Generative AI and Agentic AI.
- Compare predictive and generative systems, and how their failure modes differ.
- Apply the AI Act's role taxonomy — Provider, Deployer, Distributor, Affected Person — to real scenarios.
- Explain why role confusion is the most common source of compliance failure.

---

## 2.1 Artificial Intelligence, Machine Learning and Deep Learning

These three terms are often used interchangeably in casual conversation, but they describe a set of nested concepts:

- **Artificial Intelligence (AI)** is the broadest category: any system that performs tasks normally associated with human intelligence — reasoning, perception, language, planning. This includes rule-based "expert systems" that contain no learning at all.
- **Machine Learning (ML)** is a subset of AI in which the system learns patterns from data rather than following explicitly programmed rules. A credit-scoring model trained on historical repayment data is an ML system.
- **Deep Learning (DL)** is a subset of ML that uses multi-layered artificial neural networks. It is the technique behind most of the recent breakthroughs in image recognition, speech, and language.

```
AI  ⊃  Machine Learning  ⊃  Deep Learning
```

Why this matters for governance: regulation and risk controls must be proportionate to what the system actually is. A simple rules engine does not carry the same opacity risk as a deep neural network, even though both may be loosely called "AI" in marketing material. Governance teams must learn to ask "what kind of system is this, really?" before applying controls.

## 2.2 Foundation Models, Generative AI and Agentic AI

- **Foundation Models** are large models trained on broad data at scale, designed to be adapted (via fine-tuning or prompting) to a wide range of downstream tasks, rather than built for one narrow purpose. Large language models (LLMs) are the most visible example.
- **Generative AI** refers to systems that produce new content — text, images, audio, code — rather than simply classifying or scoring. Most generative AI products today are built on foundation models.
- **Agentic AI** refers to systems that do not just generate a response but take a sequence of actions in pursuit of a goal — calling tools, invoking other software, making multi-step decisions with limited human review at each step. Agentic systems introduce a qualitatively different governance challenge because they can *act in the world*, not merely *output content*.

These three terms describe different, overlapping dimensions: a foundation model can be used generatively (to write text) or can be wrapped in an agentic framework (to autonomously complete a task using tools).

## 2.3 Predictive Systems vs. Generative Systems — and How Their Failures Differ

| | Predictive Systems | Generative Systems |
|---|---|---|
| **Typical task** | Classify, score, or predict (e.g., approve/deny, risk score) | Produce new content (text, image, code, decision narrative) |
| **Output** | A bounded, structured value | Open-ended, high-dimensional output |
| **Typical failure** | Systematic bias, miscalibration, unfair disparate impact across groups | Hallucination, fabrication, inconsistency, unsafe or toxic content |
| **Detectability** | Can often be measured statistically against ground truth and protected attributes | Harder to measure; "correctness" may not have a single ground truth |
| **Classic harm example** | A welfare-eligibility model wrongly flags a demographic group for fraud (Module 3) | A chatbot invents a refund policy that doesn't exist and the company is held to it (Module 3) |

The governance implication: **you cannot apply the same testing and monitoring playbook to both types of system.** Predictive systems are governed primarily through statistical fairness and accuracy testing. Generative systems require additional controls such as content filtering, groundedness checks, red-teaming, and human review of outputs before they are relied upon.

## 2.4 Roles Recognised Under AI Regulation

The EU AI Act (and frameworks influenced by it) define distinct roles along the AI value chain. Understanding which role your organisation occupies — possibly in more than one system — is the single most practical governance skill in this course.

- **Provider**: The entity that develops an AI system (or has it developed) and places it on the market or puts it into service under its own name or trademark. Providers carry the heaviest obligations: technical documentation, conformity assessment, risk management systems.
- **Deployer**: The entity that uses an AI system under its own authority in a professional context. Most organisations that buy and use AI tools (e.g., an HR department using a third-party screening tool) are Deployers, not Providers — but Deployers still carry real obligations: human oversight, monitoring, informing affected persons, and in some cases conducting a fundamental rights impact assessment.
- **Distributor**: An entity in the supply chain (other than the Provider or Importer) that makes an AI system available on the market without modifying it — e.g., a reseller or marketplace.
- **Affected Person**: A natural person subject to or impacted by the output of an AI system — e.g., a job applicant screened by an AI tool, a loan applicant scored by a model. Affected Persons are not obligation-holders; the Act creates protections and rights (such as a right to explanation in certain contexts) for them.

A single organisation can hold **multiple roles simultaneously** for different systems: Provider for an in-house fraud model it builds and sells, Deployer for a commercial HR tool it buys, and effectively an "Affected Person" representative concern when assessing how its own customers are treated.

## 2.5 Why Role Confusion Is the Most Common Source of Compliance Failure

In practice, organisations fail compliance not because they ignore the law, but because they misclassify their own role:

- A company fine-tunes a third-party foundation model and assumes it remains merely a "Deployer" of the original vendor's system — when substantial modification can make it a **Provider** of a new AI system, inheriting the full weight of Provider obligations.
- A business unit assumes "the vendor handles compliance" because the vendor is the Provider — while remaining blind to its own Deployer obligations (human oversight, monitoring, usage logging, informing affected persons).
- Procurement treats an AI purchase like ordinary software procurement, without triggering the AI-specific due diligence (training data lineage, bias testing evidence, intended purpose boundaries) that Deployer obligations actually require.

**Governance takeaway:** Every AI system in an inventory needs an explicit, documented answer to "what role do we play here, and for which obligations are we therefore responsible?" This single question, asked consistently, prevents the majority of real-world compliance gaps.

---

## Key Takeaways
- AI, ML and DL are nested, not synonymous; foundation models, generative AI and agentic AI describe different dimensions of modern systems.
- Predictive and generative systems fail in structurally different ways and need different controls.
- The EU AI Act's Provider/Deployer/Distributor/Affected Person taxonomy determines who owes which obligations — and most organisations are Deployers more often than they are Providers.
- Misidentifying your own role is the single most common root cause of AI compliance failure.

## Discussion Prompt
For an AI tool your organisation currently uses, is it a predictive or generative system? Is your organisation the Provider, Deployer, or both? What evidence would you need to prove that classification to a regulator?
