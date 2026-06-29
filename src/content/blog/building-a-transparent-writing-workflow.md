---
title: "Building a Writing Workflow I Can Trust"
description: "How I used Codex to turn this site into a place for raw ideas, edited posts, and transparent source notes."
pubDate: "Jun 29 2026"
rawSlug: "building-a-transparent-writing-workflow"
---

I came back to this site because it had gone stale.

Authentibits started as a technical blog. It worked, but I had not kept it alive. I wanted it to become useful again: a place for blog ideas, notes from building things, and maybe companion writing for anything I put on YouTube.

So the first job was mechanical. Update Astro. Refresh the packages. Clean up the theme. Make it minimal and readable. Make sure the public repo was not carrying anything private. Commit it. Push it.

That part was straightforward.

Mostly because I did it with Codex.

I was not manually chasing every dependency, stale line of copy, route, and build check. I had Codex inspect the repo, update the stack, simplify the theme, run the build, launch the local preview, scan for anything that should not be public, and commit the cleanup.

Then I kept using it for the less mechanical part. We worked through homepage language. I rejected a few directions. One line finally felt right: "A place for what I'm learning." From there, the conversation moved from site maintenance into workflow design.

That is probably the useful part. Codex did not create the blog for me. It helped clear the floor, test the shape of the idea, and turn the workflow into something repeatable.

The harder question came after the site looked usable again: how do I write here without turning the whole thing into something smoother than it is true?

## The part I care about

I do not want a blog created by AI.

I want my thoughts to be the source. I want to be able to dictate something messy, paste a half-formed idea, or write a rough note without worrying about structure. Then I want AI to help the way a good editor helps.

An editor can point out repetition. An editor can make a sentence clearer. An editor can tell you where the argument loses its thread. What an editor should not do is replace the point with something smoother but less true.

That became the actual workflow I needed.

## Raw notes first

Every post that starts as a rough idea now gets a raw note.

The raw note lives in the site. It is public. It has its own URL. The final post links back to it.

That matters because it creates a check on the editing process. If the polished version no longer feels connected to the raw note, something went wrong. The post may be cleaner, but it is no longer mine in the way I want it to be.

The raw version does not need to be elegant. It can be dictation. It can be fragments. It can repeat itself. Its job is to preserve the original thinking.

The final post can do the work of helping that thinking land.

## Codifying the workflow

I also do not want to remember a long prompt every time I write.

So the workflow now lives in the repo. A future chat should be able to understand requests like:

- start a raw post
- I dictated this
- turn this raw idea into a post
- start writing from this

Those requests should trigger the same pattern:

1. Create the raw note first.
2. Treat it as the source of truth.
3. Pull out the main idea, strongest lines, open questions, and claims that need checking.
4. Make a light editorial plan.
5. Edit for clarity without replacing the point.
6. Link the final post back to the raw note.
7. Do a final editorial pass for generic phrasing before publishing.

The implementation is small, but it changes the feel of the site. Raw notes have their own route. Blog posts can declare the raw note they came from. The layout adds the link automatically.

That is enough structure to make transparency normal instead of performative.

## Practicing the story

There is another reason I want this workflow: I want to get better at storytelling.

At first, the raw note and the final post may be far apart. Codex can help find the shape: what belongs first, what needs to be cut, where the point is hiding, and where I am explaining around something instead of saying it plainly.

But I do not want that gap to stay large forever.

If this works, the raw notes should get better. The difference between source and final version should become smaller. Some posts may eventually need grammar, a cleaner order, and a few cuts instead of a full rewrite.

That would be progress. The workflow is not only for publishing. It is a practice loop.

## What changed

This session started as a site cleanup.

It turned into a writing system:

- Codex handled the mechanical repo work and helped design the workflow
- raw notes are public
- final posts link back to their source
- AI can edit, but the source note remains the authority
- future writing sessions have a simple trigger
- the gap between raw notes and final posts can show whether my storytelling is improving

That feels closer to the site I actually want.

A place for what I am learning, with receipts.
