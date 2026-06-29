---
title: "Building a Transparent Writing Workflow"
description: "Raw session notes from redesigning Authentibits into a place for drafts, edits, and public source notes."
pubDate: "Jun 29 2026"
sourceType: "session"
---

I started by updating Authentibits because it had become stale. I wanted it to become useful again, not as a polished marketing site, but as a place for blogging ideas and anything that might connect to a personal YouTube channel.

The first pass was infrastructure and design:

- update Astro and packages
- simplify the theme
- keep it minimalist and easy to read
- make sure the public repo is safe to publish
- commit and push the cleaned-up version

I did most of that with Codex. Codex handled the mechanical repo work: inspecting files, updating packages, cleaning stale copy, running builds, launching the local preview, checking what was safe to make public, and committing the cleanup. I also used Codex for the brainstorming around the homepage header and for designing the workflow itself.

That is an important detail for the final post. The lesson is not only "I made a transparent writing workflow." It is also "I used Codex as the operating partner for the mechanical parts, the iteration, and the workflow design, while keeping the source ideas and final decisions mine."

Then the bigger question showed up: how should I actually write here?

I do not want a blog site created by AI. I want my ideas. I want to be able to write, dictate, or paste whatever I am thinking as a raw document. Then I want AI to help the way a human editor would help: proofread it, clarify it, polish it, preserve my voice, and not quietly replace my thinking with safe, generic prose.

The raw document should be public too. It should be part of the site and linkable from the final post. That creates transparency. Someone can read the final version and then inspect the source note behind it.

The workflow should not require me to remember a long prompt. I should be able to start a new Codex chat and say something like:

- start a raw post
- I dictated this
- turn this raw idea into a post
- start writing from this

The repo or local agent instructions should know what to do from there.

The draft-to-post flow should be:

1. Capture the raw thought first.
2. Treat the raw note as the source of truth.
3. Pull out the real idea, strongest lines, open questions, and claims that need checking.
4. Create a light editorial plan before rewriting.
5. Polish as an editor, not as a ghostwriter.
6. Link the final post back to the raw note.
7. Before publishing, do a final editorial pass for generic phrasing and make sure the post still feels connected to the raw note.

Another goal is to get better at storytelling. At first, the raw note and final post might be far apart because I still need help finding the shape. Over time, the gap should get smaller. Ideally, some future drafts only need grammar fixes, cleaner ordering, and a few cuts.

The whole session itself should become a blog post. It should explain what happened: I cleaned up the site, pushed it toward a simpler personal writing surface, realized I needed a transparent writing workflow, and then codified that workflow in the repo.
