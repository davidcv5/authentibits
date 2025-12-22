---
title: "AI Is a Force Multiplier (And Zero Times Anything Is Zero)"
description: "Everyone's talking about AI replacing developers. But after months of building with Claude Code, I've realized the real story: AI amplifies what you bring. If you bring experience, you get a team. If you bring nothing, you get nothing."
pubDate: "Dec 22 2025"
heroImage: "../../assets/blog-placeholder-about.jpg"
---

Every day I see another video about how AI will replace developers. Often, the person giving the advice has never shipped production software—or if they have, it was long enough ago that they've forgotten what it actually takes.

They show off single-shot games, one-prompt websites, and declare the end of engineering. Meanwhile, I'm in the trenches watching the best models struggle with actual complex systems. And it scares me—not because AI isn't powerful, but because there's a gold rush happening, and nobody seems to care about the wreckage it might leave behind.

## The Gold Rush

Here's what I keep seeing: single-shot demos hyped as production-ready solutions, courses on building apps from people who've never maintained one past day two, coding advice that skips everything that makes software actually work.

To be clear: not everyone making AI content is part of the problem. Some are genuinely helping beginners find their footing, and that matters. But the loudest voices often aren't the most qualified ones, and the algorithm doesn't care about nuance.

The part that worries me? These videos get millions of views. And real engineering—understanding systems, anticipating failures, designing for the humans who'll use it and maintain it—doesn't fit in a 60-second clip.

## What Claude Code Actually Does Well

Here's what I've learned after months of building with Claude Code: it's not just about having a great model. It's about how it grabs context from wherever you need, understands it, distills it, and synthesizes solutions from its knowledge combined with your specific situation.

Once you get used to it, you realize something powerful: you don't need to learn every feature it offers. You need to know what you want.

Recently I needed to create a custom skill for this blog—a way to ensure consistent voice across posts. I didn't read the skill documentation. I didn't study the syntax. I told Claude Code what I wanted, and it figured out how to build it. It read the existing skills on my machine, understood the patterns, and created one that works.

This extends to everything. CI/CD configuration? Claude handles it. Firebase deployment? Done. Astro site setup? Built in a single conversation. I know how to do all of this—but it's tedious, and it takes time away from the actual problem I'm solving. Claude does it in minutes.

And then there's the stuff I genuinely don't know. I've built cross-platform apps with Flutter for years, but I'd never created a fully native macOS app until VoxScript. Swift, AppKit, menu bar APIs—all new territory. Claude didn't just save me time; it let me build something I couldn't have built alone.

## The Multiplier Effect

Think about how software used to get built: You have an idea. You design it. Maybe you have a team to brainstorm. Once everything's written down, specialists implement each piece. If you're a senior engineer with Kubernetes experience, but your project needs a frontend, you either learn React or hire someone who knows it.

Now? Claude becomes your team of engineers, researchers, and whiteboard.

I know I need encryption for sensitive data, so I'd use Google KMS. I don't need to spend days reading API documentation. I tell Claude what I need, it investigates the options, proposes a plan, and I review it. If it makes sense, I ask it to implement.

The key is that I knew to ask about encryption in the first place. I knew KMS was an option. That came from experience—years of building systems where security wasn't optional.

If you have experience building software, you know the right questions. Claude helps you find the answers faster than ever.

## Where It Breaks Down

I have two projects. VoxScript is a simple macOS dictation app I built in three hours. TallyFlex is a HIPAA-compliant behavior data collection platform that hundreds of practitioners depend on daily.

For VoxScript, vibe coding works. Low stakes, simple tool, no real consequences if something breaks. I let Claude run, fixed a few things, shipped it.

TallyFlex is nothing like that. It needs strong security. Compliance. It cannot fail. Real people depend on it to do hard work with vulnerable populations.

Even the best models struggle with details that matter. They miss edge cases. They make assumptions that work in demos but fail in production. The insight that catches these things comes from experience, not from the prompt.

Claude helps me move fast—but I never let it take the rails. Certain things need specific expertise. Your insight. Your unique way of seeing the problem. That's how you create solutions that actually work.

## The Takeaway

AI is a force multiplier. But here's the thing about multipliers: zero times anything is still zero.

If you bring years of engineering experience, you get a team of researchers and implementers working at superhuman speed. If you bring a YouTube tutorial and vibes, you get code that looks right but breaks in ways you won't understand.

But here's the thing for people just starting out: AI can help you *build* that experience faster—if you use it right. Don't just accept what it generates. Ask it to explain. Break things on purpose. Understand why the code works, not just that it works. The shortcut to nowhere is copying code you don't understand. The shortcut to somewhere is using AI as a teacher, not just a typist.

The gold rush will fade. The courses will stop selling. The hype cycle will move on.

The builders will remain.

I might be wrong about all of this. But after months of building real products with real users, this is how I see it playing out. AI doesn't replace experience. It reveals how much you actually have.

---

_I'm David Cruz, and I build things while learning hard lessons. This is where I share them so you don't have to._
