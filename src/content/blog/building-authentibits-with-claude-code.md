---
title: "From Empty Repo to Production Blog in One Conversation"
description: "How I built Authentibits using Claude Code - from zero to a fully deployed Astro blog with CI/CD, all without leaving the terminal."
pubDate: "Dec 22 2025"
heroImage: "../../assets/hero-image.jpg"
---

What you're reading right now was built in a single Claude Code session.

I started with an empty Git repository and a simple request: create a personal blog where I can post about coding, AI, and technology. I wanted it built with Astro, hosted on Firebase, with automatic deployments. Two hours later, I had a production-ready blog with CI/CD that deploys on every push.

Here's how it happened.

---

## The Starting Point

My project folder contained exactly two things: a `.git` directory and a `.claude` folder. That's it. No `package.json`, no source files, no configuration. Just an empty canvas.

I told Claude Code what I wanted:

> "Create a comprehensive plan to kickstart the site. I want it to have CI/CD so I can simply add a new post and it will build and deploy to Firebase hosting."

Before writing any code, Claude searched for the latest information on Astro 5, Firebase Hosting, and GitHub Actions to ensure the approach was current. Then it proposed an architecture:

```
Write Post → Git Push → GitHub Actions → Firebase Hosting
                              ↓
                    PR? → Preview Channel
                    Main? → Production
```

Simple. Exactly what I needed.

---

## What Got Built

With a single "yes, create it" from me, Claude Code executed:

**1. Project Initialization**

- Astro 5 with the official blog template
- Tailwind CSS 4 integration
- MDX support for interactive posts
- TypeScript with strict mode

**2. Firebase Configuration**

- `firebase.json` with optimized caching headers for static assets
- `.firebaserc` pointing to my project

**3. CI/CD Pipeline**

- `firebase-hosting-merge.yml` - deploys to production on push to main
- `firebase-hosting-pull-request.yml` - creates preview URLs for every PR

**4. Content Structure**

- Blog posts in `src/content/blog/` as Markdown or MDX
- Content collections with typed frontmatter schema
- Automatic RSS feed and sitemap generation

**5. Documentation**

- README with architecture diagrams
- CLAUDE.md so future AI sessions understand the codebase

The entire setup was done programmatically. Claude created files, ran `npm install`, executed `npm run build` to verify everything worked, and fixed issues as they appeared.

---

## The Workflow in Practice

After the initial setup, I ran `firebase init hosting:github` to connect GitHub Actions with my Firebase project. That command auto-generated the service account secret in my repo.

Then I pushed to GitHub. Within minutes, the site was live.

Now my workflow is:

1. Create a new `.md` file in `src/content/blog/`
2. Write the post
3. `git add . && git commit && git push`
4. Done. CI/CD handles the rest.

No manual builds. No deployment commands. Just write and push.

---

## The Meta Moment

Here's where it gets interesting: I'm using the blog that Claude built to write about Claude building the blog.

After the initial setup, I asked Claude to review a post I'd written about another project (VoxScript). It caught two typos I'd missed, fixed them, and committed the changes. Same session, same conversation context.

Then I asked it to write this very post, based on our conversation history. It had full context of everything we'd done together - every file created, every command run, every decision made.

---

## What This Means

The barrier to starting a project has never been lower.

I didn't need to:

- Read Astro documentation to set up a new project
- Figure out Firebase Hosting configuration
- Write GitHub Actions workflows from scratch
- Debug CI/CD pipeline issues

Claude Code handled the infrastructure so I could focus on what matters: writing content.

This isn't about AI replacing developers. It's about AI handling the setup overhead that stops people from starting. The "I'll build a blog someday" project that never happens because configuring everything feels like too much work.

That excuse is gone now.

---

## Try It Yourself

If you want to see the source:

- [Authentibits on GitHub](https://github.com/davidcv5/authentibits)

The entire codebase is there - every file Claude generated, the CI/CD workflows, the content structure. Fork it, modify it, or just use it as a reference for your own project.

The tools are here. The friction is gone. What will you build?

---

_This post was written with assistance from Claude Code, which had full context of the conversation where this blog was created._
