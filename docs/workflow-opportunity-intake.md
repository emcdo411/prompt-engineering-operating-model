# Workflow Opportunity Intake

![PEOM](https://img.shields.io/badge/PEOM-Workflow%20Opportunity%20Intake-0B3D91?style=for-the-badge)
![Decision](https://img.shields.io/badge/Decision-Build%20First%20%7C%20Prepare%20First-111827?style=for-the-badge)
![Owner](https://img.shields.io/badge/Requirement-Named%20Workflow%20Owner-0F766E?style=for-the-badge)

## Purpose

Workflow Opportunity Intake identifies which internal AI workflow should be built first, which should be prepared first, and which should not be automated yet.

The goal is to prevent the organization from starting with the most exciting AI idea instead of the most leverage-producing workflow.

## Core Principle

Do not begin with a prompt.

Begin with the workflow owner, the business friction, the available data, the human review point, and the success metric.

## Intake Questions

Use these questions in discovery before recommending a build.

| Dimension | Question | Score |
|---|---|---|
| Business impact | If this workflow improved by 30%, who would notice and why? | 1-5 |
| Current friction | How much manual effort, delay, rework, or inconsistency exists today? | 1-5 |
| Manual hours burned | How many hours per week are consumed by the current workflow? | 1-5 |
| Named workflow owner | Who owns this workflow and has authority to change it? | 1-5 |
| Data availability | Are the inputs structured, accessible, and current enough to use? | 1-5 |
| Tool / API access | Can the workflow connect to real systems without a major rebuild? | 1-5 |
| LLM suitability | Is this a language, reasoning, classification, retrieval, or generation task? | 1-5 |
| Decision risk | What happens if the AI produces a bad output? | 1-5 |
| Human review point | Where does a person approve, reject, edit, or escalate the output? | 1-5 |
| Success metric | How will the organization know the workflow improved? | 1-5 |

## Scoring Guide

| Score | Meaning |
|---|---|
| 5 | Strong evidence this dimension is ready |
| 4 | Mostly ready with minor cleanup |
| 3 | Partially ready but needs validation |
| 2 | Weak, unclear, or dependent on another decision |
| 1 | Missing, blocked, or not yet defined |

## Intake Verdict

| Total Score | Verdict | Action |
|---|---|---|
| 40-50 | Build First | Move into prompt lifecycle design |
| 30-39 | Build Conditional | Resolve the weakest missing dimension first |
| 20-29 | Prepare First | Map data, ownership, or process before building |
| Below 20 | Do Not Build Yet | Automation would create more operational risk than leverage |

## Executive Interpretation

The intake score is not meant to make the decision by itself.

It is meant to make the hidden tradeoffs visible:

- A workflow with high business impact but no owner is not ready.
- A workflow with strong data but no human review point is risky.
- A workflow with high friction but weak LLM suitability may need process redesign before AI.
- A workflow with measurable impact and a natural review point is usually a strong pilot candidate.

## Example Candidate Workflows

| Candidate Workflow | Likely Owner | AI Role | Risk Level |
|---|---|---|---|
| Security questionnaire response | Security / legal | Retrieve and draft structured responses | High |
| C-suite operational brief | Executive operations | Summarize, synthesize, and flag decisions | Moderate |
| Sales technical response | Sales engineering | Draft grounded prospect responses | Moderate |
| SOP assistant | Operations | Retrieve policy and process answers | Moderate |
| Product feedback classifier | Product | Summarize and classify user feedback | Low to moderate |

## Output Format

```text
Workflow candidate:
Primary owner:
Current friction:
Manual hours burned:
Available data:
Human review point:
Success metric:

Intake score:
Verdict:
Build recommendation:
Evidence needed before proceeding:
```

## Bottom Line

The first AI workflow should be selected because it has leverage, ownership, data, review, and measurable impact.

If those conditions are absent, the right move is preparation, not automation.
