# AGENTS.md — Agent Guidelines & Repository Architecture

Welcome to the **AvgEngineersAshu Portfolio & Content Hub** repository. This document defines the strict operating rules, engineering standards, privacy boundaries, and GitOps development workflows for all AI coding agents working on this project.

---

## 1. Project & Brand Entity Overview

### 1.1 The Entity: `AvgEngineersAshu`
- **Identity**: `AvgEngineersAshu` is an engineer and tech enthusiast running content across **YouTube** and **Instagram**.
- **Core Ethos**:
  > *"I am a tech enthusiast with passion in tech and hardware, so I do things like backend, frontend, devops, cloud, agents, AI, homelabbing, tinkering, etc. I am doing YouTube and Instagram as a passion to share my insights with others — nothing else is the motive here."*
- **Role of this Site**:
  - Serves as the official homepage and hub for `AvgEngineersAshu`.
  - Informs visitors who the creator is: **an engineer with a passion in tech**.
  - Hosts written notes, articles, and transcripts in blog format for topics explored on YouTube and Instagram.
  - Connects visitors to external community platforms: **YouTube, Instagram, X (Twitter), Reddit, GitHub**.

---

## 2. Strict Rules for AI Agents (Non-Negotiable)

All agents working on this codebase **MUST** strictly adhere to the following rules:

### Rule 1: Tech Stack Immutability
- **The stack is Hugo + PaperMod ONLY.**
- **DO NOT switch the tech stack** under any circumstances (no React, Next.js, Astro, Vue, Svelte, Tailwind CSS, Vite, Webpack, etc.).
- Do not introduce Node.js build steps, npm packages, or external frameworks unless explicitly directed by the user.
- Keep the site lightweight, fast, and reliant on native Hugo capabilities and PaperMod features.

### Rule 2: Strict Privacy & Zero Unapproved Personal Info
- **DO NOT share, invent, or assume any personal information** that the user has not explicitly provided in their prompts.
- Do NOT fabricate real names, employers, locations, education, or biographical backstories.
- The creator identity must strictly remain: an engineer with a passion in tech, exploring backend, frontend, devops, cloud, agents, AI, homelabbing, and tinkering, sharing insights on YouTube and Instagram purely out of passion.

### Rule 3: No Footer Copyright `@`
- Do not render copyright `@` symbols or notices in the site footer.
- Footer configuration must keep `hideCopyright: true` and rely on clean custom footer overrides in `layouts/_partials/footer.html`.

### Rule 4: Custom 404 Experience
- The 404 page must maintain a custom animation and feature the message:
  *"I am an engineer with a passion in tech."*
- Implemented declaratively via `layouts/404.html` with zero external dependencies.

### Rule 5: No Autonomous / Unilateral Decisions
- **DO NOT make architectural, stack, or significant design decisions on your own.**
- Follow the user's instructions and specifications strictly.
- When an instruction is ambiguous, present clear options or ask the user for clarification before acting.

### Rule 6: Strict No-Commit Rule (User-Gated Git Actions)
- **DO NOT execute `git commit` or `git push` autonomously.**
- Always leave changes in the working directory and ask the user to review and commit.
- Present a clear, concise summary of modified, added, or deleted files for the user's review.

### Rule 7: Follow GitOps Development Workflow
- **Declarative Configuration**: All site behavior, menus, social links, and parameters must be declaratively configured in `hugo.yaml`.
- **Infrastructure as Code / Content as Code**: Keep content structured under `content/` and static assets under `static/` or `assets/`.
- **Verification First**: Every agent must verify that the site builds cleanly using `hugo` before presenting work to the user.
- **Clean Diffs**: Make atomic, clean changes that are easy to review and revert if necessary.

---

## 3. Site Architecture

1. **Home (`/`)**:
   - PaperMod **Profile Mode** presenting `AvgEngineersAshu`.
   - Title, passion statement subtitle, social links, and quick navigation buttons.

2. **About (`/about/`)**:
   - Overview of the creator's passion: tech, hardware, backend, frontend, devops, cloud, agents, AI, homelabbing, and tinkering.
   - Connected platforms: YouTube, Instagram, X, Reddit, GitHub.

3. **Blog & Notes (`/blog/`)**:
   - Repository for written notes, write-ups, and transcripts corresponding to YouTube and Instagram topics.

4. **YouTube (`/youtube/`)**:
   - Channel hub highlighting video topics and how they connect to blog notes.

5. **404 (`/404.html`)**:
   - Custom animated radar/chip hardware visual displaying *"I am an engineer with a passion in tech."*

---

## 4. Agent Verification Checklist

Before reporting completion to the user, every agent must verify:

- [ ] **Privacy Check**: Zero unapproved personal details exist across any file.
- [ ] **Stack Check**: Only Hugo and PaperMod files were modified. No foreign frameworks were introduced.
- [ ] **Footer Check**: No `@` copyright text appears in the rendered footer.
- [ ] **404 Check**: Custom animation and *"I am an engineer with a passion in tech"* are present on the 404 page.
- [ ] **Build Validation**: Ran `hugo` with zero errors.
- [ ] **No Unsolicited Commits**: `git commit` was NOT executed.
- [ ] **Review Ready**: Provided the user with a concise overview of changes for review.
