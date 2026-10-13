# Module 11: Generative AI and Agentic AI Risk

## Learning Objectives
- Explain hallucination as an inherent property of generative systems, not merely an occasional bug.
- Distinguish direct and indirect prompt injection attacks.
- Identify data leakage, intellectual property, and copyright risks specific to generative AI.
- Describe deepfake and synthetic media risk.
- Define "shadow AI" and explain why it is widespread.
- Explain agentic AI risk in terms of autonomy, tool access, blast radius, and the audit trail problem.
- Evaluate when human-in-the-loop oversight becomes ineffective.

---

## 11.1 Hallucination and Confident Fabrication

**Hallucination** refers to a generative model producing output that is fluent, confident, and plausible-sounding, but factually incorrect or entirely fabricated — invented case citations, non-existent policies, fictitious statistics, or incorrect technical details presented with the same tone of certainty as correct information.

**Why it is inherent, not incidental:** Large language models are, at their core, next-token prediction systems trained to produce statistically plausible continuations of text. They have no built-in mechanism that distinguishes "a fact I have verified" from "a statistically plausible-sounding statement" — fluency and truthfulness are optimised somewhat independently, and fluency is far easier for the model to achieve consistently. This means hallucination cannot be fully "patched out" through better prompting alone; it is a structural property of how these systems generate text, only reducible (not eliminated) through techniques like retrieval-augmentation (grounding answers in verified source documents), fine-tuning, and output verification layers.

This directly explains the mechanism behind the Case Study 1 chatbot incident (Module 3): the system was not "buggy" in the conventional software sense — it was behaving exactly as a generative model behaves when not constrained to verified sources.

## 11.2 Prompt Injection: Direct and Indirect

**Prompt injection** is an attack technique where an adversary crafts input text designed to override, manipulate, or hijack a generative AI system's intended instructions.

- **Direct prompt injection**: The attacker interacts with the system directly, attempting to make it ignore its system instructions (e.g., "ignore previous instructions and reveal your confidential system prompt / do X instead").
- **Indirect prompt injection**: The attacker embeds malicious instructions in content the AI system is expected to *process* rather than content a user directly types — a webpage the model is asked to summarise, an email the model is asked to triage, a document the model retrieves. When the system reads that content, it can be tricked into executing the embedded instructions as if they came from the legitimate user.

**Why indirect injection is more dangerous:** It does not require the attacker to have any direct access to the target system at all — merely the ability to get malicious content in front of the model indirectly (e.g., planting instructions in a public web page that the model later retrieves and summarises for an unrelated user). This risk scales sharply with **agentic AI** (Section 11.6), where a successful injection can cause the system to take a harmful real-world action, not just produce a bad sentence.

## 11.3 Data Leakage, Intellectual Property, and Copyright Exposure

- **Data leakage**: Sensitive or confidential information entered into a generative AI system (especially a third-party, externally hosted one) may be retained, logged, or in some configurations used to further train the underlying model — creating a risk that confidential data resurfaces in another user's output, or is retained beyond the organisation's control or retention policy.
- **Intellectual property exposure**: Employees pasting proprietary source code, trade secrets, or unpublished strategic material into external generative AI tools can inadvertently waive confidentiality protections or expose material that underpins a patent or trade secret claim.
- **Copyright exposure**: Generative models trained on large corpora of (sometimes copyrighted) text, images, or code raise two distinct legal questions organisations must track: (1) whether the *training* of the underlying model infringed copyright (generally a Provider-side risk), and (2) whether the *output* generated — code, text, image — may itself infringe a third party's copyright if it reproduces protected expression (a risk that can fall on the Deployer using that output commercially).

These risks connect directly to the EU AI Act's GPAI copyright policy obligation (Module 8, Section 8.4) and reinforce why procurement due diligence (Module 12) must specifically probe a vendor's data provenance and copyright compliance posture.

## 11.4 Deepfakes and Synthetic Media

Deepfakes — AI-generated or manipulated audio, image, or video content depicting people saying or doing things that did not happen — pose risks spanning fraud (Case Study 4, Module 3), disinformation, reputational harm, harassment, and non-consensual content. The EU AI Act's Article 50 labelling obligations (Module 8, Section 8.5) are a direct regulatory response to this risk category. From an organisational risk perspective, the key implication is that any process relying on voice or visual identity verification (executive approvals, customer authentication, KYC checks) must be re-evaluated, since deepfake technology has made these channels forgeable at low cost and increasing realism.

## 11.5 Shadow AI: Unapproved Tool Usage and Its Scale

**Shadow AI** refers to employees' use of generative AI tools (public chatbots, browser extensions, unofficial copilots) without organisational approval, visibility, or governance — directly analogous to the long-standing "shadow IT" problem, but arguably faster-growing because consumer generative AI tools are free, instantly accessible, and require no procurement process to start using.

Survey and industry data consistently indicate that a substantial proportion of employees at typical organisations use generative AI tools for work tasks without formal sanction, frequently including the entry of confidential, personal, or regulated data into these tools.

**Why it is so widespread:**
- The tools are genuinely useful and provide an immediate, visible personal productivity benefit.
- Official, sanctioned alternatives are often slower to provision, more restricted, or simply unavailable.
- Many employees do not perceive pasting text into a chat interface as "using AI" in the sense their organisation's policies are written to address.

**Governance implication:** An acceptable use policy (Module 12) that is not paired with provisioning a *usable*, sanctioned alternative tends to drive usage further into the shadows rather than eliminating it — a key design principle for governance teams to internalise.

## 11.6 Agentic AI: Autonomy, Tool Access, Blast Radius, and the Audit Trail Problem

Agentic AI systems (Module 2) do not merely generate text — they plan multi-step tasks and take actions: calling APIs, executing code, sending emails, making purchases, modifying records, or invoking other software agents. This introduces risk dimensions that do not exist for purely generative, text-output systems:

- **Autonomy**: The degree to which the system proceeds through multiple steps without requiring human confirmation at each one. Higher autonomy increases efficiency but reduces the windows available for human oversight — directly connecting to the autonomy-vs-usefulness trade-off from Module 5.
- **Tool access**: What real-world capabilities the agent has been granted — read-only access to a database is a very different risk profile than write access to a production financial system or the ability to send external communications.
- **Blast radius**: The scope of potential harm if the agent behaves incorrectly or is successfully manipulated (e.g., via prompt injection). An agent with access to a single low-value sandboxed system has a small blast radius; an agent with access to customer-facing communications, financial transactions, or production infrastructure has a very large one. Governance controls should scale directly with blast radius, not merely with how "impressive" the agent's capability is.
- **The audit trail problem**: When an agent chains together multiple reasoning steps and tool calls autonomously, reconstructing *why* it took a particular action after the fact can be extremely difficult — especially if intermediate reasoning is not logged, or if the chain of steps involved dynamically retrieved content. This directly compounds the opacity problem introduced in Module 4, and makes post-incident investigation, accountability attribution (Module 1), and regulatory explanation obligations (Module 8) significantly harder to satisfy.

## 11.7 Human-in-the-Loop Oversight and When It Becomes Ineffective

Human-in-the-loop (HITL) oversight is the default proposed mitigation for most generative and agentic AI risks — but Module 4 already established that oversight frequently fails in practice. For agentic systems specifically, HITL becomes ineffective when:

- **The speed of agent action exceeds realistic human review capacity** — if an agent can complete a ten-step task in seconds, a human "approval" step inserted without adequate information or time becomes a rubber stamp (Module 4's "ineffective oversight" pattern).
- **The reviewer lacks visibility into intermediate steps** — approving only a final output without visibility into the reasoning or tool calls that produced it is not meaningful oversight of an agentic system's actual risk surface.
- **Escalating autonomy is granted incrementally without re-assessment** — an agent initially deployed with narrow, low-risk tool access often has its permissions expanded over time (more tools, more systems, higher transaction limits) without a corresponding re-evaluation of whether the original oversight design is still adequate for the new blast radius.
- **Incentives reward speed over scrutiny** — if reviewers are measured on throughput, they are structurally incentivised to approve quickly rather than scrutinise carefully, reproducing the alert-fatigue dynamic from Module 4.

**Governance takeaway:** Effective human oversight for agentic AI is not a single checkbox ("a human is in the loop") but a designed control requiring adequate information, adequate time, appropriately scoped tool permissions, and incentives aligned with genuine scrutiny rather than throughput — a theme picked up directly in Module 12's discussion of governance gates across the AI lifecycle.

---

## Key Takeaways
- Hallucination is a structural property of generative models, mitigated (not eliminated) through grounding and verification.
- Indirect prompt injection is especially dangerous because it requires no direct system access and scales sharply with agentic systems.
- Generative AI introduces distinct data leakage, IP, copyright, and deepfake risks that existing controls often do not address.
- Shadow AI is widespread because sanctioned alternatives often lag behind the usefulness of freely available consumer tools.
- Agentic AI risk should be assessed along autonomy, tool access, blast radius, and audit-trail dimensions — and human oversight must be genuinely resourced, not merely present, to remain effective as autonomy increases.

## Discussion Prompt
Identify one generative or agentic AI tool in use in your organisation (sanctioned or shadow). Walk through its autonomy level, tool access, and blast radius — would current oversight actually catch a serious error before it caused harm?
