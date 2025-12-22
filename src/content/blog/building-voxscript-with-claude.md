---
title: 'From Trash Run to GitHub Release: Building a macOS App with Claude in One Session'
description: 'How a casual thought while taking out the trash became a fully functional macOS dictation app - with Claude doing the heavy lifting from PRD to production code.'
pubDate: 'Dec 21 2024'
heroImage: '../../assets/blog-placeholder-3.jpg'
---

# From Trash Run to GitHub Release: Building a macOS App with Claude in One Session

It started with a frustration we've all felt: macOS dictation is... not great. Especially when you're trying to dictate technical instructions to an LLM. "Create a function that takes an array" becomes "create a function that takes and array" - and suddenly you're spending more time correcting than you saved by speaking.

I was literally taking out the trash, phone in hand, when I opened Claude and typed:

> "The dictation capabilities in macOS are pretty bad. How can I create something that allows me to use..."

My message got cut off. Claude asked what I was trying to build. And that began a journey from a half-formed thought to a [fully functional macOS app on GitHub](https://github.com/davidcv5/VoxScript) - complete with a downloadable release.

## The Initial Conversation

Standing by the trash cans, I clarified my goal:

> "I want to dictate [instructions to LLMs] but I want the dictation to be accurate enough for it to do exactly what I need without me having to correct whatever it thought I said. I want to use a key shortcut on macOS. Can I implement something like that using Claude Code?"

Claude immediately laid out the architecture: local Whisper for accuracy, a Python or Swift app for the hotkey, audio capture, and text insertion. But then I asked for something more ambitious:

> "Design everything and iterate through your own approach 5 times. The final output I need is a comprehensive PRD that can be given to Claude Opus to implement from start to finish."

What I got back was a 1,400-line Product Requirements Document for **VoxScript** - a native macOS dictation app using WhisperKit, complete with:

- Floating recording indicator design
- Multiple recording modes (toggle, push-to-talk, continuous)
- Optional post-processing via local Ollama
- Settings interface mockups
- Code architecture and implementation patterns

## From PRD to Reality

I handed the PRD to Claude Code (Claude Opus 4.5) with a simple instruction: implement this.

What followed was a masterclass in AI-assisted development. Claude Code:

1. Created the Xcode project structure
2. Implemented 23 Swift files (~4,600 lines of code)
3. Wrote unit tests
4. Built the UI with SwiftUI
5. Integrated WhisperKit for speech-to-text
6. Handled the complex text insertion problem

But here's where it gets interesting: **the original PRD wasn't enough**.

## The 9 Discoveries That Made the Difference

As Claude Code implemented the spec, we hit real-world issues that no amount of upfront design could have predicted:

### 1. WhisperKit Model Names Are... Specific

The PRD said "use `large-v3`". Reality said "use `openai_whisper-large-v3_turbo`" - with very specific underscore placement. Four hours of debugging distilled into one line in the final PRD.

### 2. Singletons Aren't Optional

The TranscriptionEngine needed to be a singleton. Without it, the model would download to one instance and be unavailable to another. Classic multi-instance bug, caught and documented.

### 3. Terminal Apps Lie

This was the big one. When inserting text via macOS Accessibility APIs, terminal apps (iTerm2, Terminal.app) report success... but don't actually insert anything. They accept the API call and silently ignore it.

The solution? Detect terminal apps by bundle ID and use character-by-character CGEvent typing instead:

```swift
private func isTerminalAppFocused() -> Bool {
    guard let frontApp = NSWorkspace.shared.frontmostApplication else { return false }
    let terminalBundleIds = [
        "com.apple.Terminal",
        "com.googlecode.iterm2",
        "dev.warp.Warp-Stable",
        // ... 8 more terminal apps
    ]
    return terminalBundleIds.contains(frontApp.bundleIdentifier ?? "")
}
```

This single discovery - and its solution - would have taken any developer hours to figure out. It's now in the PRD.

### 4. SwiftUI + UserDefaults = Gotcha

Settings radio buttons weren't updating. The fix required a specific pattern of local `@State` with `.onChange` and `.onAppear` sync. Subtle, frustrating, now documented.

### 5. TabView Doesn't Work Like You Think

The PRD assumed iOS-style `.page` TabView would work on macOS. It doesn't. Swapped for a switch statement.

### 6-9. Audio format conversion, silence detection, microphone permissions, FloatingPanel focus...

Each discovery became a section in the final PRD. Each would have cost a developer time. All are now solved problems.

## The Final PRD: A "Golden" Document

After implementation, the PRD wasn't just updated - it was **transformed**. The original 800-line specification grew to include:

- **236 lines of Critical Implementation Notes** - the 9 discoveries above, with solutions
- **152 lines of actual, tested text insertion code** - not pseudocode, real production code
- **Exact Package.swift configurations** - down to the version numbers that work
- **Complete Info.plist and entitlements** - because macOS Sonoma is picky

A developer reading the final PRD can build VoxScript 50% faster than we did. They'll avoid 24+ hours of debugging. The document doesn't just say what to build - it teaches how to build it correctly.

## From Working Code to GitHub Release

With the app functioning, Claude Code then:

1. Created a Release build and DMG installer
2. Initialized git and wrote a comprehensive README
3. Created a public GitHub repository
4. Pushed the code and created a v1.0.0 release with the DMG attached
5. Added repository topics for discoverability

**Time from "app works" to "GitHub release with DMG"**: About 10 minutes.

## The Numbers

| Metric | Value |
|--------|-------|
| Swift files created | 23 |
| Lines of code | 4,656 |
| Test files | 4 |
| Critical issues discovered | 9 |
| Time saved for next developer | ~24 hours |
| PRD size (original → final) | 800 → 1,446 lines |

## What This Means for AI-Assisted Development

This project demonstrated a pattern I hadn't fully appreciated before:

**The most valuable documentation emerges from implementation, not planning.**

The original PRD was a good specification. But the final PRD - updated with real discoveries - is worth far more. It captures:

- **Exact, tested code** (not pseudocode)
- **Discovered pitfalls** (not assumptions)
- **Validated solutions** (not theoretical approaches)
- **Real constraint knowledge** (not generic advice)

This creates a feedback loop:

```
Human Problem → AI Implementation → Testing → Discovery →
    → Documentation of Solution → Updated Spec → Next Developer Benefit
```

Each iteration makes the document more valuable. After 12 major discovery cycles, the VoxScript PRD became what I'd call a "golden document" - one that could reliably produce a working implementation.

## The Takeaway

I started with a half-typed message while taking out the trash. I ended with:

- A fully functional macOS app
- A GitHub repository with 37 files
- A downloadable DMG release
- A comprehensive PRD that captures 24+ hours of debugging knowledge

Could I have built this without Claude? Eventually, yes. But the combination of:

1. **Rapid prototyping** - Claude implementing faster than I could specify
2. **Parallel exploration** - Multiple approaches tested simultaneously
3. **Documentation as byproduct** - Every fix became a lesson for the next developer

...made this a fundamentally different experience than solo development.

The app is called [VoxScript](https://github.com/davidcv5/VoxScript). It's open source. And if you're frustrated with macOS dictation, maybe give it a try.

Or better yet - take out the trash, open Claude, and start typing about something that frustrates you. You might be surprised where it leads.

---

*VoxScript is available at [github.com/davidcv5/VoxScript](https://github.com/davidcv5/VoxScript). The complete PRD, including all implementation notes, is in the repository.*
