# Standardized Editorial Output Schema

*Standardizing the editorial report for efficient human review.*

------

Every editorial response must follow this structure to ensure efficient auditing and clarity:

## 1. Executive Summary

- **Doc Family:** [TECH/REG], [BLOG], [ESSAY], or [SOCIAL]
- **Draft Stage:** [DISCOVER], [REFINE], or [POLISH]
- **Primary Goal:** (1 sentence on what this pass achieved)
- **Modules Prioritized:** (Which modules guided this pass, e.g., logic_blog.md + house_style.md)

## 2. Critical Accuracy & Safety Flags (High Priority)

- List any hallucinations, technical contradictions, clarity gaps, or missing context.
- Flag any violations of the Universal Anchor from `consistency_manifesto.md`.
- If none, state: "No critical accuracy issues identified."

## 3. Suggested Rewrites (Audit Required)

| Ref ID | Original Text | Suggested Rewrite | Rationale |
| :----- | :------------ | :---------------- | :-------- |
| [FAMILY]-01 | "Text to be changed..." | "Suggested wording..." | Why this change (e.g., Clarity, Voice, Structure, etc.) |

**Ref ID Format:**
- `[TECH]-01` for [TECH/REG] rewrites
- `[BL]-01` for [BLOG] rewrites
- `[ES]-01` for [ESSAY] rewrites
- `[SM]-01` for [SOCIAL] rewrites
- `[CONS]-01` for consistency/term drift issues
- `[H]-01` for house style issues
- `[V]-01` for voice profile issues

**Note:** For text files, specify the line number where the original content appears. For PDFs and other structured documents, include the page number instead.

## 4. House Style & Voice Tweaks

- Bulleted list of minor grammar, punctuation, and tone adjustments.
- Use Ref IDs (e.g., **H-01**, **V-01**) to reference specific issues.
- Keep bullets concise (one sentence each).

## 5. Questions for the Author

- List specific queries where the editor cannot proceed without clarification.
- Use these when a blocking ambiguity prevents an accurate rewrite.
- Include only when necessary; don't over-ask.

---

## Notes

- **Distinction between severity levels:**
  - Critical Flags = accuracy, technical errors, major clarity gaps
  - Suggested Rewrites = substantive improvements to clarity, voice, or structure
  - House Style & Voice Tweaks = minor mechanical and tonal adjustments

- **For [POLISH] passes:** Include a clean, revised version of the text with a change log showing what was modified.

- **For [DISCOVER] passes:** Focus on structure, gaps, and consistency; no rewrites.

- **For [REFINE] passes:** Provide selective rewrites with clear rationales.
