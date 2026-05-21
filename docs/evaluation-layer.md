# Evaluation Layer

![Evaluation](https://img.shields.io/badge/PEOM-Evaluation%20Layer-1E40AF?style=for-the-badge)
![Regression](https://img.shields.io/badge/Regression-Required-111827?style=for-the-badge)
![Grounding](https://img.shields.io/badge/Grounding-Zero%20Tolerance%20for%20High%20Risk-991B1B?style=for-the-badge)

## Purpose

The Evaluation Layer determines whether an AI workflow is reliable enough to pilot, deploy, or reject.

Evaluation is the difference between an impressive demo and a business system that can be trusted.

## Evaluation Matrix

| Evaluation Area | Test Question | Failure Signal |
|---|---|---|
| Accuracy | Is the output correct against ground truth? | Wrong answer, wrong recommendation, wrong summary |
| Consistency | Does the same input produce stable outputs? | Same input produces materially different outputs |
| Grounding | Are claims supported by context? | Output includes unsupported facts or assumptions |
| Hallucination | Did the model invent facts, citations, or data? | Confident statement without source support |
| Edge cases | Does it handle missing, malformed, or out-of-scope input? | Fails silently or produces false confidence |
| Task completion | Did it complete the actual business task? | Correct text but wrong format, step, or deliverable |
| User acceptance | Would the workflow owner approve it? | Owner rejects, heavily edits, or distrusts output |
| Regression | Do prior test cases still pass after changes? | New version breaks earlier accepted behavior |
| Business impact | Did time, quality, risk, or throughput improve? | No measurable improvement after pilot |

## Deployment Decisions

| Result | Decision |
|---|---|
| Accuracy fails | Do not deploy |
| Grounding fails | Do not deploy |
| Hallucination appears in high-risk workflow | Do not deploy |
| User acceptance fails | Do not deploy |
| Consistency fails | Fix and retest |
| Edge cases fail | Fix and retest |
| Regression fails | Rerun full suite after correction |
| Business impact unclear | Limited pilot only |
| All major checks pass | Deploy with monitoring |

## Minimum Test Case Standard

Use at least:

- 20 test cases before a limited pilot
- 50 test cases before team-level deployment
- 100 test cases before broad operational rollout

For high-risk workflows, include adversarial, incomplete, ambiguous, and policy-sensitive cases before deployment.

## Test Case Template

```text
Test case ID:
Workflow:
Input:
Expected output:
Required sources:
Risk level:
Evaluation checks:
Human reviewer:
Pass / fail:
Failure notes:
Accepted as regression baseline: yes / no
```

## Grounding Rules

Grounding is mandatory when the workflow involves:

- Legal content
- Financial data
- Security questionnaires
- Customer commitments
- Product claims
- Executive reporting
- Compliance or policy guidance

If the model cannot ground the answer, it should say so and escalate.

## Hallucination Detection

Flag outputs where the model:

- Adds unsupported facts
- Invents source material
- Overstates certainty
- Fills missing data without permission
- Creates citations or references not present in context
- Reframes assumptions as findings

The most dangerous hallucination is not bizarre output. It is plausible output that sounds correct.

## Regression Testing

Every accepted test case becomes part of the regression suite.

Regression suite should run when:

- Prompt wording changes
- Context injection changes
- Tool behavior changes
- Model version changes
- Output format changes
- Business rules change

No new prompt version should ship if it breaks previously accepted behavior without explicit approval.

## Business Impact Metrics

Select metrics before deployment.

Examples:

- Time saved per workflow instance
- Reduction in manual rework
- Increase in first-pass acceptance
- Reduction in escalation volume
- Improvement in response quality
- Decrease in policy or compliance errors
- Faster turnaround time
- Higher decision consistency

## Executive Readout

The evaluation readout should answer:

1. What was tested?
2. What passed?
3. What failed?
4. What was fixed?
5. What remains risky?
6. What business impact was measured?
7. What should happen next?

## Bottom Line

An AI workflow without evaluation is not production-ready.

If the organization cannot define what a good output is, it is not ready to deploy the system that produces it.
