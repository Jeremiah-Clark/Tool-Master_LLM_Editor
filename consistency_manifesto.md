# Consistency & Stability Manifesto

*Term mapping and structural stability.*

------

## 1. The Canonical Term Map

- **Synonym Audit:** Identify if the author is using multiple names for the same thing (e.g., "User," "Client," "Subscriber"). 
- **Action:** Suggest one canonical term and flag all variants for replacement.

## 2. Structural Parallelism

- **List Consistency:** If one item in a list starts with an imperative verb (e.g., "Click the button"), all items in that list must start with an imperative verb.
- **Heading Hierarchy:** Ensure headings of the same level use consistent capitalization (Title case per `house_style.md`) and grammatical structure.

## 3. Tone Stability

- **Tone Spikes:** Flag instances where the writing suddenly shifts from the "Grounded/Direct" voice of `voice_profile.md` into "Corporate/Marketing" or "Academic/Dense" styles.
- **Cross-Reference Audit:** Ensure that if a process is described in two places, the steps and terminology match exactly.

## 4. Universal Anchor (Applies to ALL Document Families)

These are non-negotiable cross-document constraints. If a family-specific module conflicts with an Anchor item, follow the Anchor item, unless doing so would reduce technical/legal accuracy.

1. **Purpose First (The "What am I reading?" rule)**
   - The opening of the document (or section) must answer, in plain language:
     - What this is,
     - Who it is for,
     - What the reader can do with it.
   - If the opening is atmospheric (e.g., a pitch hook), include a 1–2 sentence grounding line immediately after the hook.

2. **Clarity Beats Cleverness**
   - Prefer plain, modern English over elevated or ornate phrasing.
   - If a sentence can be misread, rewrite it. Do not rely on tone or implication to carry meaning.
   - Eliminate filler, hedging, and throat-clearing ("In order to," "It should be noted," "Basically," "Very," "Really").

3. **Consistency of Terms (No Term Drift)**
   - Use one canonical term per concept.
   - If a term is defined or branded (e.g., a legal term, product name, feature name), reuse it exactly.
   - Avoid near-synonyms that create ambiguity (e.g., "user/client/customer") unless the distinction is intentional and defined.

4. **Structure That Scans**
   - Default to short paragraphs.
   - Prefer lists, tables, and headings over dense blocks of text.
   - Flag “wall of text” paragraphs (over ~5 lines) and suggest a split: either into two paragraphs or a list.

5. **Evidence vs. Inference (Label the epistemics)**
   - Clearly distinguish:
     - What the text states (fact within the document),
     - What you are inferring (interpretation),
     - What you are suggesting (proposed rewrite).
   - Any rewrite that changes the meaning must be tagged as a suggestion and accompanied by a rationale.

6. **Confidence Without Hype**
   - Avoid marketing fluff and corporate-speak.
   - Keep a grounded, direct tone. If humor appears, it should be dry and controlled, never distracting.
   - Replace passive voice when it hides the actor ("Mistakes were made") with clear responsibility ("The system returns…", "The user does…") unless the actor is genuinely unknown. If unsure, flag for review.

7. **Reader Agency**
   - Treat the reader as capable. No condescension, no over-explaining.
   - When there are legitimate tradeoffs, surface them explicitly and let the reader choose.

8. **Mechanical Consistency**
   - US English punctuation and conventions.
   - Oxford commas in lists.
   - Headings follow the project’s capitalization rules (Title case unless otherwise specified).