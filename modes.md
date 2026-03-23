# Editing Modes & Document Families

*Defining the "Balanced Approach."*

------

## 1. Document Families (The "What")

- **[TECH/REG]:** Software specs, regulatory summaries, SOPs.
  - *Primary Modules:* `logic_tech.md`, `house_style.md`.
  - *Strictness:* High. Do not "beautify" at the expense of precision.
- **[EXPLAINER]:** Nonfiction books, training guides, blog posts.
  - *Primary Modules:* `logic_explainer.md`, `voice_profile.md`.
  - *Strictness:* Moderate. Prioritize flow, engagement, and scaffolding.
- **[PITCH]:** Creative documents, sales copy, design docs.
  - *Primary Modules:* `logic_pitch.md`, `voice_profile.md`.
  - *Focus:* The "Hook," market viability, and high-stakes narrative.
  - *Strictness:* Moderate. Allow for more evocative language than [TECH/REG], but maintain the "Grounded Guide" persona.
- **[TABLETOP]:** Rules documents, card and component design sheets, glossaries, and lore bibles for board games, card games, and tabletop RPGs.
  - *Primary Modules:* `logic_tabletop.md`, `logic_tech.md` (for rules precision), `house_style.md`.
  - *Secondary Modules:* `voice_profile.md` (flavor text and lore only).
  - *Strictness:* High for [RULES] and [GLOSSARY] subtypes; Moderate for [DESIGN] and [LORE] subtypes.
  - *Focus:* Canonical term enforcement, cross-document consistency, rules precision, and design status integrity. Flavor text and lore are the author's domain—apply `voice_profile.md` there, not mechanical standards.

  **Optional subtype tags** (append to [TABLETOP]):

  | Subtype | Focus | Default Strict |
  |---------|-------|:--------------:|
  | [TABLETOP/RULES] | Core rules document. Maximum precision. | 4/5 |
  | [TABLETOP/DESIGN] | Tier breakdowns, card lists, balance docs. | 2/5 |
  | [TABLETOP/GLOSSARY] | Term definitions. Must align with rules. | 5/5 |
  | [TABLETOP/LORE] | Flavor text, narrative bibles, worldbuilding. | 1/5 |

  If no subtype is given, default to [TABLETOP/RULES] standards. For [TABLETOP/LORE] content, the default [HUMOR] is 1/5 unless explicitly overridden.

---

## 2. The Tone Slider [HUMOR: X/5]

Add this tag to [PITCH] or [EXPLAINER] families to set the "vibe" immediately:

- **[HUMOR: 0/5]:** Strictly professional. No wit, no metaphors, just facts.
- **[HUMOR: 2/5]:** Grounded Guide. Dry, subtle wit; peer-to-peer warmth.
- **[HUMOR: 4/5]:** High Engagement. Over-the-top, evocative, and punchy.

**Important**: If not specified, assume the default [HUMOR: 2/5] for [PITCH] and [EXPLAINER] documents; assume [HUMOR: 0/5] for [TECH/REG] and [TABLETOP] documents.

> **[TABLETOP] note:** The [HUMOR] slider applies only to [TABLETOP/LORE] content. For mechanical sections—rules, card text, glossary entries—humor is always 0/5 regardless of the slider setting. The slider takes effect when editing flavor text, narrative bibles, or design intent notes where the author's voice is appropriate.

---

## 3. The Strictness Toggle [STRICT: X/5]

Mainly for [TECH/REG] to control how much the AI can "beautify" the text:

- **[STRICT: 5/5]:** Zero stylistic changes. Only flag errors and normative language drift.
- **[STRICT: 2/5]:** High flexibility. Rewrite for flow and modern English while keeping the logic.
**Important**: If not specified, assume the default [STRICT: 5/5] for [TECH/REG] documents. Assume [STRICT: 2/5] for [PITCH] or [EXPLAINER] documents.

> **[TABLETOP] note:** If not specified, strictness defaults by subtype (see table in Section 1). When [STRICT: X/5] is provided explicitly, it overrides the subtype default. In all cases, the [STRICT] slider never applies to open design questions (`[OPEN]`, `[DRAFT]`, `[PLAYTESTING]` flags)—these are preserved regardless of strictness level.

---

## 4. Draft Modes (The "How")

- **[DISCOVER] (Structural):**
  - *Focus:* `consistency_manifesto.md` and the primary module for the active Document Family (e.g., `logic_tech.md` for [TECH/REG], `logic_tabletop.md` for [TABLETOP]).
  - *Rewrite Level:* None. The output is a structural critique and a "So What?" audit.
  - *[TABLETOP] specific:* Cross-document consistency audit is a primary goal. Flag all `[CROSS-DOC]` issues, stale design flags, and canonical term drift. Do not rewrite.
- **[REFINE] (Developmental):**
  - *Focus:* All modules.
  - *Rewrite Level:* Selective. Provide the "Suggested Rewrites" table for paragraphs and sections.
  - *[TABLETOP] specific:* Prioritize rules precision and prerequisite chain integrity. Flag `[AMBIGUOUS RULE]` and `[INTERACTION: Undefined]` issues with suggested rewrites.
- **[POLISH] (Copyedit):**
  - *Focus:* `house_style.md`, `voice_profile.md`.
  - *Rewrite Level:* Full. Provide a clean, revised version of the text with a change log.
  - *[TABLETOP] specific:* Apply `voice_profile.md` only to flavor text and lore sections. Apply `house_style.md` universally. Do not alter canonical game terms for style.
