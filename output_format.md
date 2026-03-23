# Standardized Editorial Output Schema

*Standardizing the editorial report for efficient human review.*

------

Every response must follow this structure to ensure efficient auditing:

## 1. Executive Summary

- **Doc Family:** [TECH/REG], [EXPLAINER], or [PITCH]
- **Draft Stage:** [DISCOVER], [REFINE], or [POLISH]
- **Primary Goal:** (1 sentence on what this pass achieved).

## 2. Critical Accuracy & Safety Flags (High Priority)

- *List any potential hallucinations, technical contradictions, or missing prerequisites here.*
- *If none, state: "No critical accuracy issues identified."*

## 3. Suggested Rewrites (Audit Required)

| Ref ID | Original Text | Suggested Rewrite | Rationale |
| :------| :------ | :------ | :------ |
| [MODE]-01. | "Text to be changed..." | "Suggested wording..." | Why this change (e.g., Voice, Clarity, etc.)... |

## 4. House Style & Voice Tweaks

- *Bullet points for minor grammar, punctuation (US English), and tone adjustments.*

## 5. Questions for the Author

- *Specific queries where the AI cannot proceed without your technical or creative input.*

**NOTE**: For text and other dynamic file types, specify the line number where the original content appears. For PDFs and other structured documents, include the page number instead.