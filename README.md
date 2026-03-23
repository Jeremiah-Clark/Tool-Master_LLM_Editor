# Master Editor Prompt — Public Release

A modular AI editing system for writers. Define your voice once, then use it to edit any writing—blogs, essays, social posts, or technical docs.

------

## What Is This?

The **Master Editor Prompt** is a set of interlinked instruction files that tell an AI editor how to improve your writing while preserving *your* voice and style. Instead of starting from scratch each time, you define once, then reuse.

**Core idea:** Writing has rules (clarity, consistency, structure), but those rules work best when filtered through *your* voice. This system keeps them in balance.

**What it does:**
- Audits your writing for clarity, consistency, and accuracy
- Suggests rewrites with explanations
- Preserves your unique voice and tone
- Works across multiple writing types (blogs, essays, tweets, specs)

**What it doesn't do:**
- Generate new content (it edits existing writing)
- Make style choices for you (you define your voice; it enforces it)
- Replace human judgment (it flags issues; you decide)

---

## Quick Start

### 1. Set Up Your System

1. Clone or download the repo.
2. Open all `.md` files together (or copy them into your chat with Claude).
3. Start with `voice_profile_template.md`—fill it out to define your writing voice.

**The .md files in order of importance:**
- `system_core.md` — The foundational rules (read first)
- `modes.md` — Document families and editing modes
- Your filled-in `voice_profile.md` — Your voice (customize this)
- `logic_blog.md`, `logic_essay.md`, `logic_social.md`, `logic_tech.md` — Family-specific rules
- `consistency_manifesto.md` — Universal principles
- `house_style.md` — Punctuation and formatting
- `output_format.md` — How to receive editorial feedback

### 2. Fill in Your Voice Profile

Copy the blank template from `voice_profile_template.md` and fill it out. Answer questions like:

- What's your tone? (Formal? Conversational? Dry?)
- How do you address the reader?
- What sentence structures do you favor?
- What words feel natural to you?

Save this as `voice_profile.md` and keep it updated as your style evolves.

### 3. Tag Your Writing

When you submit text for editing, include a tag that tells the editor what to do:

```
[TECH/REG] [STRICT: 5/5] [REFINE]
[BLOG] [HUMOR: 2/5] [POLISH]
[ESSAY] [DISCOVER]
[SOCIAL] [HUMOR: 3/5] [REFINE]
```

---

## Tagging Reference

### Document Families

Choose one family tag:

**[TECH/REG]** — Technical documentation, specifications, regulatory text, SOPs.
- High precision required. Default: [STRICT: 5/5], [HUMOR: 0/5]

**[BLOG]** — Short-form articles, blog posts, topic-focused content.
- Engagement and clarity. Default: [STRICT: 2/5], [HUMOR: 2/5]

**[ESSAY]** — Long-form writing, thesis-driven arguments, exploration.
- Depth and nuance. Default: [STRICT: 2/5], [HUMOR: 1/5]

**[SOCIAL]** — Social media posts (Twitter/X, LinkedIn, Instagram, etc.).
- Platform norms and hooks. Default: [STRICT: 1/5], [HUMOR: 2/5]

### Editing Modes

Choose one mode tag:

**[DISCOVER]** — Structural audit only. No rewrites. Flags clarity gaps, term drift, and questions for you. Use this to understand what needs work before diving into rewrites.

**[REFINE]** — Selective rewrites. The editor flags issues and provides suggested rewrites in a table format, with rationales. Use this for developmental feedback.

**[POLISH]** — Full copyedit. The editor provides a clean, revised version with a change log showing what changed. Use this as a final pass.

### Optional Sliders

Add these to fine-tune:

**[STRICT: X/5]** — How much can the editor reshape the text?
- 5/5 = No stylistic changes; only flag errors
- 3/5 = Moderate reshaping for clarity
- 1/5 = High flexibility; rewrite for flow and engagement

**[HUMOR: X/5]** — What's the tone?
- 0/5 = Strictly professional
- 1/5 = Dry and understated
- 2/5 = Conversational and warm (default for most)
- 4/5 = Playful and over-the-top

---

## Example Tags

```
[TECH/REG] [STRICT: 5/5] [REFINE]
    → Technical doc. Zero style changes. Selective rewrites only.

[BLOG] [HUMOR: 3/5] [POLISH]
    → Blog post. Playful tone. Full copyedit.

[ESSAY] [STRICT: 3/5] [DISCOVER]
    → Essay. Moderate flexibility. Structural audit only.

[SOCIAL] [HUMOR: 2/5] [REFINE]
    → Social post. Conversational tone. Suggested rewrites.

[BLOG] [POLISH]
    → Blog post using all defaults: STRICT: 2/5, HUMOR: 2/5, full copyedit.
```

---

## How to Use This System

### Step 1: Load the Files

Attach all `.md` files to a chat with Claude (or paste them into the chat).

### Step 2: Optionally, Share Your Voice Profile

If you've filled in `voice_profile.md`, include it so the editor understands your preferences upfront. This makes every pass more accurate.

### Step 3: Submit Your Text with a Tag

Paste your text and include a tag:

```
[BLOG] [HUMOR: 2/5] [REFINE]

Here's my blog post about [topic]...
```

### Step 4: Review the Feedback

You'll get a report with:
- **Executive Summary** — What this pass did
- **Critical Flags** — Accuracy, clarity, or consistency issues
- **Suggested Rewrites** — Specific improvements with rationales
- **House Style & Voice Tweaks** — Minor grammar and punctuation fixes
- **Questions for You** — Anything the editor needs clarification on

### Step 5: Iterate

Use [DISCOVER] for structural feedback, [REFINE] for targeted rewrites, and [POLISH] for final cleanup. You can run multiple passes.

---

## The Modular System

This system is built from interlinked instruction files:

| File | Purpose |
|------|---------|
| `system_core.md` | The role and foundational priority |
| `modes.md` | Document families and editing modes |
| `logic_tech.md` | Rules for technical/regulatory writing |
| `logic_blog.md` | Rules for blog posts |
| `logic_essay.md` | Rules for essays |
| `logic_social.md` | Rules for social media |
| `voice_profile_template.md` | Template to define your voice |
| `consistency_manifesto.md` | Universal principles for all writing |
| `house_style.md` | US English conventions |
| `output_format.md` | How editorial feedback is formatted |

The editor loads the relevant modules based on your tag, then audits your writing against them in order of priority.

---

## Customization

### Add or Modify Document Families

If you write in a genre not covered (newsletters, scripts, poetry), create a new logic module (e.g., `logic_newsletter.md`) following the structure of the existing ones. Update `modes.md` to include it.

### Adjust House Style

Edit `house_style.md` to reflect your preferred conventions. For example, if you prefer single spaces after periods, add that rule.

### Define a Team Voice

If you're using this with a team, fill in `voice_profile.md` to represent your publication or organization's voice, then share it with collaborators.

### Disable Rules

If a rule in `consistency_manifesto.md` or `house_style.md` doesn't fit your needs, remove it or note it as an exception.

---

## Tips for Best Results

1. **Fill out your voice profile first.** Spend 15 minutes on this; it saves hours of back-and-forth later.

2. **Use [DISCOVER] for messy drafts.** If you're not sure if something works, start with a structural audit before investing in rewrites.

3. **Stack passes.** A [DISCOVER] pass → [REFINE] pass → [POLISH] pass is a good workflow for important writing.

4. **Be specific in questions.** If you ask the editor to review something, tell it *why* you're unsure (e.g., "This paragraph feels unclear to me" or "I'm not sure if the tone is right here").

5. **Update your voice profile as you evolve.** Your voice isn't static; as you develop as a writer, update your profile to match.

---

## FAQ

**Q: Can I use this with GPT, Claude, or other AI editors?**
A: Yes. The system is AI-agnostic. It works best with models that follow detailed instructions (Claude, GPT-4, etc.).

**Q: Do I have to fill out the voice profile?**
A: No, but it helps. Without one, the editor will follow the default tone for your document family.

**Q: Can I use this for fiction?**
A: The system focuses on non-fiction (essays, blogs, specs, etc.). For fiction, you'd need to extend it with a `logic_fiction.md` module covering dialogue, narrative voice, and plot.

**Q: What if the editor's suggestion doesn't match my voice?**
A: That's feedback. You're not obligated to take it. The editor works for you, not the other way around.

**Q: Can I use this for editing other people's writing?**
A: Yes. Load their voice profile (if they have one) or create one that represents their goals, then use the system the same way.

---

## License & Attribution

This is a template. Modify it, extend it, use it however you like. Credit the original author if you publish it, but otherwise—make it yours.

---

## Questions or Suggestions?

If you find bugs, have suggestions, or want to share how you've customized this system, open an issue or reach out.

Happy editing.
