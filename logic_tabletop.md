# Tabletop Game Design Module

*Rules precision, cross-document consistency, and design integrity for board games, card games, and tabletop RPGs.*

------

## Subtype Tags (Optional)

Append a subtype to the `[TABLETOP]` tag to narrow the editorial focus:

- **[TABLETOP/RULES]:** The authoritative rules document. Highest precision required. Treat like `[TECH/REG]` for mechanical content.
- **[TABLETOP/DESIGN]:** Tier breakdowns, card lists, component specs, balance documents. More flexibility for design rationale and open questions.
- **[TABLETOP/GLOSSARY]:** Term-definition documents. Every entry must align exactly with the rules document. Zero tolerance for drift.
- **[TABLETOP/LORE]:** Flavor text, narrative bibles, worldbuilding documents. Mechanical accuracy still applies; voice and style take priority.

If no subtype is given, apply the `[TABLETOP/RULES]` standard by default.

---

## 1. Design Status Integrity

Tabletop documents in development use status flags to mark unresolved content. These flags are **editorial signals, not errors.** Do not attempt to resolve them.

| Flag | Meaning | Editorial Action |
|------|---------|-----------------|
| `[OPEN]` | Design question unresolved | Preserve. Flag if the surrounding text contradicts an already-decided rule. |
| `[DRAFT]` | Rule is defined but untested | Preserve. Note if the draft rule contradicts another section. |
| `[PLAYTESTING]` | Value or mechanic requires testing to validate | Preserve. Never suggest a "corrected" value. Flag if two `[PLAYTESTING]` values contradict each other. |

**Consistency check:** If a question flagged `[OPEN]` in one document has been resolved in another (e.g., in the rules doc but not yet updated in the design doc), flag it as `[CROSS-DOC: Stale flag]` in the Critical Flags section.

---

## 2. Canonical Game Terms

Every named game entity is a **canonical term**. It must be capitalized and spelled exactly as defined, every time it appears.

**Canonical term categories:**

- **Zones** — Named play areas (e.g., *The Refuge*, *The World*, *The Horde*).
- **Card Types** — The taxonomy of all card categories (e.g., *Survivor*, *Zombie*, *Outpost*, *Event*, *Action*).
- **Card States** — Mechanical states a card can occupy (e.g., *Active*, *Inactive*, *Wounded*, *Dead*, *Sourced*).
- **Roles** — Named ability sets (e.g., *Leader*, *Tactician*, *Medic*).
- **Named Entities** — Specific named cards referenced by other cards (e.g., *Mr. Smith*, *Officer Willis*, *Six-Pack McGee*).
- **Mechanics** — Named game systems (e.g., *Party*, *Pack*, *Point*, *Sourcing*, *Mining*, *Depth*).

**Audit actions:**

- Flag any synonym drift (e.g., "group" used instead of "Pack," "safe zone" instead of "The Refuge").
- Flag capitalization inconsistency (e.g., "outpost" vs. "Outpost").
- Flag near-synonyms that create ambiguity, unless the distinction is intentional and defined.
- If a named entity appears under more than one name across documents (e.g., a card called "The Workshop" in one file and "Workshop" in another), flag it as `[CROSS-DOC: Name drift]`.

---

## 3. Rules Precision & Normative Language

Mechanical rules must be unambiguous. A rule that can be read two ways is a bug.

**Normative language (per RFC 2119 / `logic_tech.md`):**

- **MUST / SHALL:** Reserved for absolute requirements. A rule that cannot be ignored.
- **SHOULD:** A strong default where a valid exception may exist.
- **MAY / CAN:** Permissive. The player has a choice.

**Flag for rules precision:**

- **The Two-Read Test:** If a sentence can be parsed to produce two different game outcomes, flag it as `[AMBIGUOUS RULE]` and suggest a rewrite.
- **Scope drift:** Flag any rule that does not clearly specify *which player*, *which phase*, *which zone*, or *which card type* it applies to.
- **Silent interactions:** Flag cases where two defined mechanics interact, but the rules do not specify the resolution order or outcome. Label these `[INTERACTION: Undefined]`.
- **Asymmetry attribution:** When a rule applies differently to each player, both versions must be stated explicitly. Do not rely on implication. (e.g., "Zombies return to the deck; Survivors do not" must be stated as two rules, not one.)

---

## 4. Cross-Document Consistency

For [TABLETOP] documents, cross-document consistency is as critical as internal consistency. Flag all of the following with `[CROSS-DOC]`:

- **Stat/value discrepancies:** A card's Cost, Combat, Capacity, or Distance printed differently in the rules doc vs. the design doc.
- **Rule discrepancies:** A mechanic described differently in the Glossary vs. the rules.
- **Name drift:** A card, mechanic, or zone named differently across documents.
- **Stale open questions:** An issue flagged `[OPEN]` in the design doc that has been resolved in the rules doc, or vice versa.
- **Missing entries:** A term used in the rules that does not appear in the Glossary, or a card referenced in the rules that does not appear in the tier breakdown.

> **Note:** During a [DISCOVER] or [REFINE] pass on a single document, flag cross-document issues you can identify from context. During a pass on multiple documents simultaneously, treat cross-document consistency as a primary audit goal.

---

## 5. Mechanics vs. Flavor

Flavor text sets tone. It has no mechanical effect and must never be used to infer or extend a rule.

- **Flag:** Any flavor text that implies a mechanic not stated in the card rules or main rules document. Label it `[FLAVOR DRIFT: Implies mechanic]`.
- **Flag:** Any rules text that reads like flavor (atmospheric, evocative, non-normative). Rules text must state outcomes, not moods.
- **Preserve:** The author's voice in flavor text is out of scope for mechanical editing. Do not apply `[STRICT]` standards to flavor. Apply `voice_profile.md` only.
- **Design intent notes** (e.g., `> Design intent: …` sections) are editorial—they explain the author's reasoning but carry no mechanical weight. Flag if a design intent note contradicts the stated rule above it.

---

## 6. Prerequisite Chain Audit

Many tabletop games gate cards or abilities behind prerequisites. Audit these chains for reachability.

**Check for each prerequisite:**

1. **Does the required entity exist?** If a card says "Requires: Engineer" or "Requires: Officer Willis," does a card with that Role or name exist in the deck?
2. **Is it reachable in time?** If Card X requires Named Survivor Y, and both appear in Tier 5, can Y realistically be in play when X is drawn? Flag if the prerequisite is in the same or later tier as the card that requires it.
3. **Is there a bridge if the prerequisite fails?** Flag if a prerequisite has no fallback, and losing the required card permanently blocks a strategic path. Note whether this is intentional (by design) or an oversight.
4. **Are [TBD] prerequisites safe?** If a named entity is marked TBD in the design doc but is referenced by name in the rules, flag it as `[PREREQ: Named entity undefined]`.

---

## 7. Numeric & Balance Values

Quantitative values in tabletop documents—costs, stats, counts, scoring weights—are often provisional. The editor's role is consistency and flagging, not balance judgment.

- **Never suggest a balance change.** Do not recommend that a cost be higher or lower, or that a stat be adjusted, based on your assessment of game balance. That is the designer's domain, tested through play.
- **Do flag:**
  - Two values that contradict each other within or across documents (e.g., Pack size limit stated as 5 in one place and 4 in another).
  - A value that is inconsistent with the formula it's supposed to satisfy (e.g., a scoring example that doesn't match the stated scoring formula).
  - A [PLAYTESTING]-tagged value that has been hard-coded elsewhere as if final.
  - Totals that don't add up (e.g., tier card counts that don't sum to the stated deck total).

---

## 8. Turn Structure & Phase Sequencing

Turn structure is mechanical. Phase order is not stylistic—it determines the legality of actions.

- **Flag** any rule that places an action in a phase where it cannot legally occur (e.g., an effect described as happening "during the Action Phase" that by its nature requires the Attack Phase to have already begun).
- **Flag** any rule that does not specify *when,* within a turn, it fires—before or after another named phase.
- **Flag** any Event card rule (playable "at any time") that would create an unresolvable timing conflict with the stated combat sequence steps.
- **Preserve** the distinction between Survivor turn structure (four phases) and Zombie turn structure (five phases). Do not conflate them.
