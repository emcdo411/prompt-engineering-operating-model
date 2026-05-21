---
name: prompt-engineering-operating-model
description: "Use when designing, evaluating, or governing AI workflows powered by LLMs. Covers prompt lifecycle, context architecture, eval matrix design, hallucination controls, regression testing, human-in-the-loop governance, and 30-day pilot planning. Also use for proof assets targeting AI infrastructure, prompt/context engineering, or agent governance roles — including recruiter prep, C-suite briefs, and pre-meeting artifacts for enterprise AI prospects. Trigger on: prompt engineering operating model, AI workflow architecture, Claude/OpenAI workflow design, internal AI tools, prompt evals, hallucination checks, regression testing, workflow intake, AI pilot plan, agent governance, copilot governance, PEOM, or any request to turn LLM experiments into governed deployable workflows."
license: "Proprietary - Epoch Frameworks LLC. DACR License v2.7."
version: 1.2.0
author: "Erwin Maurice McDonald"
---

# Prompt Engineering Operating Model (PEOM v1.2)

Prompt engineering is not better wording. It is workflow analysis, context architecture, output evaluation, governance, and adoption applied to business workflows that cannot afford unreliable AI behavior.

Use PEOM to turn scattered LLM experimentation into evaluated, governed, deployable AI workflows.

---

## Activation Gate

Classify the request before producing output.

| Lane | Signal | Output |
|---|---|---|
| PROOF_ASSET | Interview, recruiter, AI infra role, enterprise prospect brief | GitHub/PDF artifact outline |
| WORKFLOW_DISCOVERY | Org wants to find AI opportunities | Workflow intake + ranked candidates |
| PROMPT_SYSTEM_DESIGN | Needs prompt, context, tool, or agent design | Prompt lifecycle + spec |
| EVALUATION_DESIGN | Asks about quality, hallucination, testing, evals | Evaluation matrix |
| GOVERNANCE_ONLY | Prompts exist but lack ownership/versioning | Governance layer only |
| PILOT_PLAN | Needs 30-day rollout | Pilot plan + success metrics |

**Rule:** If company is unnamed or confidential, do not invent company-specific facts. Build role-relevant operating model and label all assumptions.

---

## Executive Entry Questions

Ask before explaining the framework.

1. Which internal workflow, if improved by 30%, creates the most leverage without increasing operational risk?
2. Are prompts treated as versioned product infrastructure with evaluation and regression checks — or as one-off instructions?
3. Where are high-context employees repeatedly translating messy information into decisions AI could support but not fully own?

---

## Workflow Opportunity Intake

Score candidate workflows 1–5 across:

| Dimension | Weight |
|---|---|
| Business impact | High |
| Current friction | High |
| Manual hours burned | Medium |
| Named workflow owner | Required |
| Data availability | High |
| Tool/API access | Medium |
| LLM suitability | High |
| Decision risk | Inverse — high risk lowers score |
| Human review point | Required |
| Measurable success metric | Required |

**Verdict:**

| Score | Decision |
|---|---|
| 40–50 | BUILD FIRST |
| 30–39 | BUILD CONDITIONAL |
| 20–29 | PREPARE FIRST |
| Below 20 | DO NOT BUILD YET |

---

## Prompt Engineering Lifecycle

Every workflow follows this sequence:

1. Workflow problem definition
2. Task decomposition
3. Prompt design
4. Context design
5. Tool/API integration
6. Output evaluation
7. Human review
8. Deployment
9. Monitoring and iteration

**Failure rule:** If evaluation, ownership, or human review is missing, the workflow is not production-ready. Do not deploy.

---

## Evaluation Layer

Every workflow requires an evaluation matrix before deployment.

| Eval | Question |
|---|---|
| Accuracy | Is the answer correct against ground truth? |
| Consistency | Does the same input produce stable outputs? |
| Grounding | Are claims supported by provided context? |
| Hallucination | Did the model invent facts, citations, or assumptions? |
| Edge Cases | Does it handle missing, malformed, or out-of-scope input? |
| Task Completion | Did it complete the business task — not just respond? |
| User Acceptance | Would the workflow owner approve this output? |
| Regression | Do previous test cases still pass after prompt changes? |
| Business Impact | Did time, error rate, quality, or throughput improve? |

**Deployment rules:**

- Accuracy, grounding, or acceptance failure → **DO NOT DEPLOY**
- Consistency, edge case, or regression failure → **FIX AND RETEST**
- Business impact unclear → **LIMITED PILOT ONLY**

---

## Governance Layer

Prompts are infrastructure. Every deployed workflow must include:

| Requirement | Description |
|---|---|
| Versioned prompt artifact | Stored, dated, diff-tracked |
| Named workflow owner | Single accountable person |
| Human approval point | Defined gate before output acts |
| Evaluation log | Pass/fail per eval dimension |
| Runtime escalation criteria | What triggers human override |
| Sensitive data rule | PII handling and data boundary |
| Regression suite | Minimum 5 test cases per workflow |
| Monitoring cadence | Weekly review minimum |

**No owner = no deployment.** This is non-negotiable.

---

## Output Calibration

Right-size the artifact to the user's actual need.

| User Need | Output |
|---|---|
| Meeting in under 24 hours | 5-bullet prep memo |
| Recruiter / interview proof | GitHub page or PDF structure |
| Client discovery | Workflow intake + 3 diagnostic questions |
| SOW scoping | Deliverables, exclusions, timeline |
| Technical handoff | Agent spec + eval matrix |
| Governance review | Ownership, versioning, eval, escalation model |
| Enterprise prospect brief | Executive entry questions + scored workflow candidates |

---

## Proof Asset Structure

For AI infrastructure, prompt/context engineering, or agent governance roles, produce:

1. Executive brief (role-calibrated)
2. Three executive entry questions
3. Workflow opportunity intake (3 scored candidates minimum)
4. Prompt lifecycle diagram
5. Evaluation layer
6. Governance layer
7. 30-day pilot plan
8. Example internal workflows

**Opening language for proof assets:**

> I treat prompt engineering as product infrastructure. The work is not just writing better instructions — it is decomposing workflows, designing context, evaluating outputs, governing deployment, and measuring whether the AI system improves the business process it supports.

---

## Anti-Patterns

Avoid these regardless of client pressure:

- Leading with framework language before the buyer confirms pain
- Claiming company-specific insight from a vague JD or brief
- Building prompts before mapping the workflow
- Automating a decision with no named human owner
- Shipping without passing evals
- Treating hallucination as a writing problem instead of a grounding problem
- Producing a 12-page roadmap when the user needs call prep
- Giving away the full scoring rubric when a proof artifact is sufficient

---

## Integration Rules

| Upstream Skill | Input to PEOM |
|---|---|
| AI Adoption Architect v6.5 (Layer 0B) | MLOps readiness and feedback-loop posture |
| MOC v4.9 (ASIL/ESIL) | Ambient signal routing, external intelligence layer |
| Fractional CXO Practice Builder v2.6 | DVL/RIL governance posture feeding pilot scope |

| Downstream Skill | PEOM Output |
|---|---|
| 10x Senior BSA | Workflow decomposition for agent spec |
| MOC / Fractional CXO | Intake score, governance risk, proof-asset framing for prospect calls |
| EBT v2.7 | Bias audit on evaluation criteria and scoring logic |

---

## DACR Protection

Share the proof artifact. Retain the full scoring rubric and integration routing map. The operating model demonstrates thinking. The rubric and integration map are retained IP.

---

*Prompt Engineering Operating Model v1.2*
*McDonald (2026) | DACR License v2.7 | Epoch Frameworks LLC*
