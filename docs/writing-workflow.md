# Transparent Writing Workflow

Use this workflow for Authentibits posts that begin as raw thoughts, dictation, notes, or a pasted draft. The goal is not to make AI write the post. The goal is to preserve David's thinking and use AI like an editor, proofreader, and structure partner.

## File Pattern

Start with the raw source:

```text
src/content/raw/<slug>.md
```

Publish the final edited post here:

```text
src/content/blog/<slug>.md
```

The final post should set `rawSlug` in frontmatter so the site links back to the raw note:

```yaml
---
title: "Post Title"
description: "Short SEO description"
pubDate: "Jun 29 2026"
rawSlug: "post-slug"
---
```

## Workflow

1. Capture the raw idea first. Keep it messy if needed.
2. Extract the actual idea, strong lines, open questions, and claims that need checking.
3. Create a brief editorial plan before rewriting.
4. Edit for clarity, order, grammar, and rhythm without replacing David's point of view.
5. Mark any invented bridge, added claim, or unsupported inference for approval.
6. Audit the final post against [Wikipedia:Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing).
7. Publish the raw note and final post together so the transparency link works.

## Editing Rules

- Preserve the core claim, uncertainty, and emotional texture from the raw note.
- Prefer David's original phrasing when it is clear and alive.
- Tighten repetition, filler, and unclear transitions.
- Do not add confident claims that are not in the raw note or verified source material.
- Do not make the ending grander than the raw idea supports.
- Do not use generic AI essay patterns such as broad universal claims, inflated stakes, canned contrast phrasing, or summary-heavy conclusions.

## AI-Writing Audit

Before a post is considered ready, check the final draft against the Wikipedia field guide for signs of AI writing. Treat it as a judgment aid, not a detector. Look especially for:

- Generic significance language that says the topic is important without showing why.
- Formulaic contrast such as "not just X, but Y" when it was not natural in the raw note.
- Repetitive three-part lists or balanced phrases that sound polished but empty.
- Vague attribution, over-explaining, or broad claims without concrete grounding.
- Conclusions that summarize instead of landing a specific thought.

If the audit finds these patterns, revise toward the raw source rather than adding more polish.
