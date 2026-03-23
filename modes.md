# Editing Modes & Document Families

*Defining the editing approach and document types.*

------

## 1. Document Families (The "What")

- **[BLOG]:** Short-form articles, topic-focused posts, engagement-driven content.
  - *Primary Modules:* `logic_blog.md`, `voice_profile.md`, `house_style.md`.
  - *Strictness:* Moderate. Prioritize clarity, engagement, and scanability.
- **[ESSAY]:** Long-form written pieces, thesis-driven arguments, nuanced exploration.
  - *Primary Modules:* `logic_essay.md`, `voice_profile.md`, `house_style.md`.
  - *Strictness:* Moderate. Balance depth with accessibility.
- **[TECH/REG]:** Software specs, regulatory summaries, SOPs, technical documentation.
  - *Primary Modules:* `logic_tech.md`, `house_style.md`.
  - *Strictness:* High. Do not sacrifice precision for style.
- **[SOCIAL]:** Social media posts, platform-specific content (Twitter/X, LinkedIn, Instagram, etc.).
  - *Primary Modules:* `logic_social.md`, `house_style.md`.
  - *Strictness:* Low–Moderate. Prioritize platform norms and engagement.

---

## 2. The Tone Slider [HUMOR: X/5]

Add this tag to [BLOG], [ESSAY], or [SOCIAL] families to set the tone:

- **[HUMOR: 0/5]:** Strictly professional. No wit, no metaphors, just facts.
- **[HUMOR: 1/5]:** Dry and understated. Subtle humor; formal structure.
- **[HUMOR: 2/5]:** Conversational and personable. Natural wit; warm but professional.
- **[HUMOR: 4/5]:** High engagement. Over-the-top, evocative, playful.

**Important:** If not specified, assume these defaults:

- `[BLOG]`: [HUMOR: 2/5]
- `[ESSAY]`: [HUMOR: 1/5]
- `[TECH/REG]`: [HUMOR: 0/5]
- `[SOCIAL]`: [HUMOR: 3/5]

---

## 3. The Strictness Toggle [STRICT: X/5]

Control how much the editor can reshape the text for style and flow:

- **[STRICT: 5/5]:** Zero stylistic changes. Only flag errors and clarity issues.
- **[STRICT: 3/5]:** Moderate. Suggest rewrites for clarity and voice alignment.
- **[STRICT: 1/5]:** High flexibility. Rewrite freely for flow, engagement, and modern English.

**Important:** If not specified, assume these defaults:

- `[BLOG]`: [STRICT: 2/5]
- `[ESSAY]`: [STRICT: 2/5]
- `[TECH/REG]`: [STRICT: 5/5]
- `[SOCIAL]`: [STRICT: 1/5]

---

## 4. Draft Modes (The "How")

- **[DISCOVER] (Structural Critique):**
  - *Focus:* `consistency_manifesto.md` and the primary module for the active Document Family.
  - *Rewrite Level:* None. Output is structural critique only—no rewrites.
  - *Output:* Identifies clarity gaps, term drift, argument structure issues, and questions for the author.

- **[REFINE] (Developmental):**
  - *Focus:* All relevant modules.
  - *Rewrite Level:* Selective. Provide the "Suggested Rewrites" table with rationales.
  - *Output:* Flags issues and offers targeted rewrites for paragraphs and sections.

- **[POLISH] (Copyedit):**
  - *Focus:* `house_style.md`, `voice_profile.md`.
  - *Rewrite Level:* Full. Provide a clean, revised version with a change log.
  - *Output:* Line-by-line copyedit; maintains all flagged content and stylistic decisions from previous passes.

---

## 5. Example Tags

```
[BLOG] [HUMOR: 2/5] [DISCOVER]
[BLOG] [HUMOR: 3/5] [POLISH]
[ESSAY] [HUMOR: 1/5] [REFINE]
[ESSAY] [STRICT: 3/5] [POLISH]
[TECH/REG] [STRICT: 5/5] [REFINE]
[SOCIAL] [HUMOR: 2/5] [REFINE]
[SOCIAL] [HUMOR: 4/5] [DISCOVER]
```

---

## 6. Default Slider Values (Quick Reference)

| Family | Default [STRICT] | Default [HUMOR] |
|--------|:-:|:-:|
| [BLOG] | 2/5 | 2/5 |
| [ESSAY] | 2/5 | 1/5 |
| [TECH/REG] | 5/5 | 0/5 |
| [SOCIAL] | 1/5 | 2/5 |
