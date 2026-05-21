# Prompt Engineering Operating Model

![Framework](https://img.shields.io/badge/Framework-PEOM-0B3D91?style=for-the-badge)
![Version](https://img.shields.io/badge/Version-1.2.0-0B3D91?style=for-the-badge)
![Use Case](https://img.shields.io/badge/Use%20Case-AI%20Infrastructure-111827?style=for-the-badge)
![Discipline](https://img.shields.io/badge/Discipline-Prompt%20%2B%20Context%20Engineering-2563EB?style=for-the-badge)
![Governance](https://img.shields.io/badge/Governance-Human%20in%20the%20Loop-0F766E?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Proof%20Asset-16A34A?style=for-the-badge)

![Evaluation](https://img.shields.io/badge/Evaluation-Accuracy%20%7C%20Grounding%20%7C%20Regression%20%7C%20Impact-1E40AF)
![Prompt Lifecycle](https://img.shields.io/badge/Lifecycle-Design%20%7C%20Context%20%7C%20Tools%20%7C%20Monitoring-334155)
![DACR](https://img.shields.io/badge/DACR-License%20v2.7-7C3AED)

---

## Executive Brief

AI infrastructure companies cannot afford informal internal AI adoption.

The same rigor applied to infrastructure products must be applied to internal LLM workflows: workflow selection, prompt and context design, output evaluation, human review, governance, versioning, and measurable business impact.

The **Prompt Engineering Operating Model (PEOM)** turns scattered prompt experimentation into evaluated, governed, deployable AI workflows.

This repository is a proof asset. It demonstrates how prompt engineering is treated as product infrastructure — not isolated instruction writing.

---

## The Three Questions

These are the executive entry points before any workflow is touched.

### C-Suite

> Which internal workflow, if improved by 30%, creates the most leverage across the company without increasing operational risk?

### Engineering / AI Leadership

> Are prompts treated as versioned product infrastructure with evaluation and regression checks — or as one-off instructions living in someone's notebook?

### Operations

> Where are high-context employees repeatedly translating messy information into decisions that AI could support, but not fully own?

If a company cannot answer these questions, that is the discovery engagement.

---

## Core Thesis

Prompt engineering is not better wording.

It is the operating discipline for shaping model behavior inside real business workflows. A production-ready prompt system requires a clear workflow owner, a defined business task, reliable context, testable outputs, human review, evaluation logs, regression checks, and monitoring.

If those components are missing, the organization does not have an AI workflow. It has an experiment.

---

## PEOM Workflow — Full System Architecture

```mermaid
flowchart TD
    START(["🔍 Workflow Request Received"]):::entry

    %% ─── ACTIVATION GATE ───────────────────────────────────────────
    subgraph GATE ["⬛  ACTIVATION GATE — Classify Before Building"]
        direction TB
        G1{{"What is the request type?"}}:::decision
        L1["📄 PROOF_ASSET\nInterview · Recruiter · Brief"]:::lane
        L2["🔎 WORKFLOW_DISCOVERY\nFind AI Opportunities"]:::lane
        L3["🧠 PROMPT_SYSTEM_DESIGN\nDesign Prompt · Context · Agent"]:::lane
        L4["📊 EVALUATION_DESIGN\nQuality · Hallucination · Testing"]:::lane
        L5["🏛 GOVERNANCE_ONLY\nOwnership · Versioning · Escalation"]:::lane
        L6["🚀 PILOT_PLAN\n30-Day Rollout"]:::lane
    end

    %% ─── WORKFLOW INTAKE ────────────────────────────────────────────
    subgraph INTAKE ["🟦  PHASE 1 — WORKFLOW OPPORTUNITY INTAKE"]
        direction TB
        I1["Score Candidate Workflows\nImpact · Friction · Owner · Risk · Metric"]:::phase
        I2{{"Intake Score?"}}:::decision
        I3["✅ BUILD FIRST\nScore 40–50"]:::pass
        I4["⚠️ BUILD CONDITIONAL\nScore 30–39"]:::warn
        I5["🔧 PREPARE FIRST\nScore 20–29"]:::fail
        I6["🚫 DO NOT BUILD YET\nBelow 20"]:::block
        I7["Resolve Blocking Condition\nData · Owner · Clarity"]:::fix
    end

    %% ─── BUILD PHASE ────────────────────────────────────────────────
    subgraph BUILD ["🟩  PHASE 2 — PROMPT SYSTEM BUILD"]
        direction TB
        B0["Define Workflow Problem\n+ Task Decomposition"]:::phase
        B1["🖊 Prompt Design\nRole · Task · Constraints · Format"]:::parallel
        B2["📦 Context Design\nRAG · Memory · Retrieval · Injection"]:::parallel
        B3["🔌 Tool / API Integration\nFunctions · External Systems"]:::parallel
        B4["Assemble Prompt System\nPrompt + Context + Tools unified"]:::phase
    end

    %% ─── EVALUATION GATE ────────────────────────────────────────────
    subgraph EVAL ["🟧  PHASE 3 — EVALUATION LAYER"]
        direction TB
        E0["Run Full Evaluation Matrix"]:::phase
        E1{{"Accuracy · Grounding\nAcceptance — pass?"}}:::decision
        E2["❌ DO NOT DEPLOY\nHard failure on core dims"]:::block
        E3{{"Consistency · Edge Cases\nRegression — pass?"}}:::decision
        E4["🔁 FIX AND RETEST\nReturn to Build Phase"]:::fix
        E5{{"Business Impact\nclear and measurable?"}}:::decision
        E6["🔬 LIMITED PILOT ONLY\nImpact unproven"]:::warn
        E7["✅ EVALUATION PASSED\nAll dimensions green"]:::pass
    end

    %% ─── GOVERNANCE GATE ────────────────────────────────────────────
    subgraph GOV ["🟥  PHASE 4 — GOVERNANCE LAYER"]
        direction TB
        V1{{"Named owner\nassigned?"}}:::decision
        V2["🚫 BLOCK DEPLOYMENT\nNo owner = no deployment"]:::block
        V3["Lock Governance Artifacts\nVersion · Eval Log · Escalation\nData Rule · Regression Suite · Cadence"]:::phase
        V4{{"Human review\npoint defined?"}}:::decision
        V5["🚫 BLOCK DEPLOYMENT\nNo human gate = no deployment"]:::block
    end

    %% ─── DEPLOYMENT & MONITORING ────────────────────────────────────
    subgraph DEPLOY ["🟪  PHASE 5 — DEPLOY + MONITOR + ITERATE"]
        direction TB
        D1["🚀 Deploy to Production"]:::pass
        D2["Monitor: Weekly Review Cadence"]:::phase
        D3{{"Drift or regression\ndetected?"}}:::decision
        D4["Escalate to Workflow Owner\n+ Trigger Regression Suite"]:::fix
        D5["Stable — Continue Monitoring"]:::pass
        D6["🔁 Iterate Prompt Version\nReturn to Build Phase"]:::fix
    end

    %% ─── CONNECTIONS ────────────────────────────────────────────────
    START --> G1
    G1 -->|"Proof Asset"| L1
    G1 -->|"Discovery"| L2
    G1 -->|"System Design"| L3
    G1 -->|"Eval Design"| L4
    G1 -->|"Governance"| L5
    G1 -->|"Pilot"| L6

    L1 & L2 & L3 & L4 & L5 & L6 --> I1
    I1 --> I2
    I2 -->|"40–50"| I3
    I2 -->|"30–39"| I4
    I2 -->|"20–29"| I5
    I2 -->|"< 20"| I6
    I5 --> I7
    I7 --> I1
    I6 --> I7
    I3 & I4 --> B0

    B0 --> B1 & B2 & B3
    B1 & B2 & B3 --> B4

    B4 --> E0
    E0 --> E1
    E1 -->|"Fail"| E2
    E1 -->|"Pass"| E3
    E3 -->|"Fail"| E4
    E4 --> B0
    E3 -->|"Pass"| E5
    E5 -->|"Unclear"| E6
    E6 --> D1
    E5 -->|"Clear"| E7

    E7 --> V1
    V1 -->|"No owner"| V2
    V1 -->|"Owner confirmed"| V3
    V3 --> V4
    V4 -->|"No review gate"| V5
    V4 -->|"Gate confirmed"| D1

    D1 --> D2
    D2 --> D3
    D3 -->|"Yes"| D4
    D4 --> D6
    D6 --> B0
    D3 -->|"No"| D5
    D5 --> D2

    %% ─── STYLES ─────────────────────────────────────────────────────
    classDef entry fill:#0B3D91,stroke:#0B3D91,color:#fff,rx:20
    classDef decision fill:#1E293B,stroke:#334155,color:#F8FAFC,rx:6
    classDef lane fill:#1E3A5F,stroke:#2563EB,color:#BFDBFE
    classDef phase fill:#134E4A,stroke:#0F766E,color:#CCFBF1
    classDef parallel fill:#14532D,stroke:#16A34A,color:#BBF7D0
    classDef pass fill:#166534,stroke:#16A34A,color:#DCFCE7
    classDef warn fill:#78350F,stroke:#D97706,color:#FEF3C7
    classDef fail fill:#7C2D12,stroke:#EA580C,color:#FFEDD5
    classDef block fill:#7F1D1D,stroke:#DC2626,color:#FEE2E2
    classDef fix fill:#3B1F6A,stroke:#7C3AED,color:#EDE9FE
```

---

## Workflow Opportunity Intake

PEOM scores candidate workflows before recommending any build.

| Dimension | What It Determines |
|---|---|
| Business impact | Whether the workflow matters enough to improve |
| Current friction | How much manual effort, delay, or inconsistency exists |
| Manual hours burned | Whether the labor cost justifies automation |
| Named workflow owner | Whether someone has authority to change the process |
| Data availability | Whether the workflow has usable inputs |
| Tool / API access | Whether the workflow can connect to real systems |
| LLM suitability | Whether the task fits language, reasoning, retrieval, or generation |
| Decision risk | What happens if the AI is wrong |
| Human review point | Where accountability remains human-owned |
| Success metric | How improvement will be measured |

### Intake Verdict

| Score | Decision | Meaning |
|---|---|---|
| 40–50 | **Build First** | High-value workflow with owner, data, and review path |
| 30–39 | **Build Conditional** | Worth pursuing after the blocking condition is resolved |
| 20–29 | **Prepare First** | Data, ownership, or process clarity is not ready |
| Below 20 | **Do Not Build Yet** | Automation would create more risk than leverage |

---

## Evaluation Layer

Evaluation is the difference between a prompt that works once and a system that can be trusted.

| Evaluation Area | Test Question |
|---|---|
| Accuracy | Is the output correct against ground truth? |
| Consistency | Does the same input produce stable outputs? |
| Grounding | Are claims supported by the provided context? |
| Hallucination | Did the model invent facts, citations, or assumptions? |
| Edge cases | Does it handle missing, malformed, or out-of-scope input? |
| Task completion | Did it complete the business task — not just respond? |
| User acceptance | Would the workflow owner approve the result? |
| Regression | Do previous test cases still pass after prompt changes? |
| Business impact | Did time, quality, risk, or throughput improve? |

### Deployment Rules

| Failure Type | Decision |
|---|---|
| Accuracy failure | **Do not deploy** |
| Grounding failure | **Do not deploy** |
| Acceptance failure | **Do not deploy** |
| Consistency failure | Fix and retest |
| Edge case failure | Fix and retest |
| Regression failure | Fix and rerun full suite |
| Impact unclear | Limited pilot only |

---

## Governance Model

Prompts are infrastructure. Infrastructure requires governance.

Every deployed AI workflow must include:

| Requirement | Description |
|---|---|
| Versioned prompt artifact | Stored, dated, and diff-tracked |
| Named workflow owner | Single accountable person — not a team |
| Human approval point | Defined gate before the output acts or routes |
| Evaluation log | Pass/fail recorded per eval dimension per version |
| Runtime escalation criteria | Conditions that trigger human override |
| Sensitive data rule | PII handling and data boundary explicitly defined |
| Regression test suite | Minimum 5 test cases per workflow |
| Monitoring cadence | Weekly review minimum — escalate on drift |

**No owner = no deployment.** This is non-negotiable.

---

## Example Internal AI Workflows

| Workflow | AI Role | Human Owner | Primary Risk |
|---|---|---|---|
| C-suite briefing assistant | Summarize and synthesize operational updates | Executive operations | Inaccurate figures |
| Security questionnaire assistant | Retrieve and draft structured responses | Security / Legal | Compliance exposure |
| Engineering knowledge copilot | Retrieve internal system knowledge | Engineering lead | Hallucinated system behavior |
| Sales technical response assistant | Draft technical responses | Sales engineering | Unsupported product claims |
| Product feedback classifier | Summarize and classify customer feedback | Product manager | Loss of nuance |
| SOP assistant | Answer policy and process questions | Operations owner | Outdated source material |

---

## 30-Day Pilot Plan

| Week | Focus | Output |
|---|---|---|
| Week 1 | Workflow discovery | Ranked workflow candidates and named owner confirmed |
| Week 2 | Prompt and context prototype | First working workflow prototype with eval baseline |
| Week 3 | Evaluation and feedback loop | Test cases, evaluation matrix, revision cycle |
| Week 4 | Limited pilot and executive readout | Pilot results, governance plan, next-build recommendation |

---

## Executive Readout Format

1. What workflow was selected and why it was prioritized
2. What the evaluation matrix showed — dimension by dimension
3. What governance was required before deployment was permitted
4. What business impact was observed or projected
5. What should be built next and in what sequence

---

## Repository Structure

```text
.
├── README.md
├── index.html
├── docs/
│   ├── workflow-opportunity-intake.md
│   ├── prompt-lifecycle.md
│   ├── evaluation-layer.md
│   ├── governance-model.md
│   └── 30-day-pilot-plan.md
├── assets/
│   ├── peom-workflow-diagram.png
│   └── evaluation-matrix.png
└── skill/
    └── SKILL.md
```

---

## What This Demonstrates

This repository shows how prompt engineering is treated in a business context.

Not as a writing exercise. As workflow architecture.

The value is not producing a better model response. The value is designing the operating conditions that make model behavior useful, measurable, governable, and safe enough to place inside a real business process.

---

**Prompt Engineering Operating Model v1.2**
McDonald (2026) | DACR License v2.7 | Epoch Frameworks LLC
Proprietary methodology. Public artifact shares the operating model, not the retained scoring logic.

