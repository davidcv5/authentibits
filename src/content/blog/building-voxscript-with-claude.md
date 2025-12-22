---
title: "The AI Dictation Duel: Building a macOS App in 3 Hours"
description: "Apple Dictation sucks. So I built a replacement using Claude Opus 4.5 and Claude Code in a single afternoon. Here is the breakdown of the 3-hour sprint."
pubDate: "Dec 21 2025"
heroImage: "../../assets/blog-placeholder-about.jpg"
---

# The AI Dictation Duel: From Idea to Production in 3 Hours

It happened while I was taking out the trash.

I wasn't dictating at the moment, but my mind was racing with ideas for a tool I desperately needed. I work on my Mac all day, and as someone for whom English is a second language, typing out everything can sometimes slow down my train of thought. I _want_ to use dictation to speed things up, but Apple's built-in solution just doesn't cut it.

Apple Dictation is a friction point, not a productivity tool. It struggles with accents, fails completely on technical context (try saying "camelCase variable"), and forces you to stop and fix mistakes constantly. Instead of speeding me up, it slowed me down.

I realized I was avoiding dictation because I didn't trust it. I wanted something that didn't just "transcribe words" but actually _understood_ my intent. I needed a tool that could take my spoken thoughts and turn them into clear, structured instructions for my agentic coding tools, or perfectly written emails, without me having to wrestle with typos and missing words.

So, right there on the driveway, I pulled out my phone and started brainstorming with Claude. The goal? **VoxScript**. A native macOS app using local Whisper models for high-accuracy transcription, coupled with an LLM post-processing step to fine-tune the output.

I didn't just want text; I wanted _clarity_. And I wanted it built _now_.

---

## The 3-Hour Sprint: Gemini vs. Claude

I decided to run a benchmark. I created a comprehensive Product Requirements Document (PRD) and handed it to two of the most advanced AI agents available today to see who could get me to a working build first.

### The Contenders:

1.  **Antigravity (using Gemini Flash 3):** Fast, integrated, but struggled with the depth of the project. It hit multiple build errors, got stuck in troubleshooting loops, and required constant "hand-holding" to navigate the macOS Accessibility APIs.
2.  **Claude Code (using Claude Opus 4.5):** This was the clear winner.

While Gemini was circling back on basic configuration issues, **Claude Opus 4.5** produced a starting point that actually built and ran on the first try. It didn't just write code; it understood the _nuances_ of the macOS environment.

### The Implementation Timeline:

- **Minute 0:** Idea while taking out the trash.
- **Minute 15:** PRD finalized by Claude.
- **Hour 1:** Claude Code implements the core engine (WhisperKit integration).
- **Hour 2:** Refining the UI and solving the "Terminal Problem" (Terminal apps require specific event handling for text insertion).
- **Hour 3:** Creating the DMG, initializing the GitHub repo, and publishing the first release.

In just 3 hours, I went from a frustration in my driveway to a production-ready tool that is becoming my daily driver.

---

## Why Claude Opus 4.5 Won the Duel

The difference between "AI that codes" and "AI that builds projects" is in the iteration. Claude Opus 4.5 demonstrated a superior grasp of:

- **System Integration:** It correctly identified that terminal apps (iTerm2, Warp) ignore standard Accessibility API calls and proactively implemented a `CGEvent` fallback.
- **State Management:** It handled complex SwiftUI singleton patterns for the transcription engine without me having to debug "multiple instance" errors.
- **The "Final 10%":** It didn't stop at a "working script." It generated the `Info.plist`, handled microphone permissions, and even wrote the README.

---

## The Result: VoxScript

VoxScript isn't just a project on my hard drive. It’s a tool that is poised to save me hours of "rectification time" every week. It’s local, it’s fast, and it was built in the time it takes to watch a long movie.

**The Takeaway:**

The "Zero to Hero" workflow is real, but it has nuance.

For specific, contained tools like VoxScript, "vibe coding" with AI is incredibly powerful. You can go from idea to executable in an afternoon. But for larger, complex systems like **TallyFlex** (my main business), the story is different. AI helps implement features faster, but it doesn't replace the need for deep engineering experience.

When you're building a complex platform, you can't rely on "vibes" alone. You need to know how to architect the system, ask the right questions, and validate the answers. AI can write the mundane code, but you still need to be the lead engineer who knows when a solution is robust and when it's just a hallucination.

VoxScript proves that for the right scope, you can clear the path from frustration to solution in record time. Which brings me back to my driveway: if I hadn't taken out the trash, I might still be fixing "word salads" today.

You can check out the project here: [VoxScript on GitHub](https://github.com/davidcv5/VoxScript)

---

_I’m David Cruz, and I build things that make my life easier. This blog is where I share those discoveries._
