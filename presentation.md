---
title: What I Learned Building Real Projects with AI Coding Agents
author: Sébastien Stormacq
event: AI SDLC Geneva
date: 2026-03-31
theme:
  name: dark
  override:
    default:
      margin:
        percent: 4
    footer:
      style: template
      left: "{event}"
      right: "{current_slide} / {total_slides}"
---

![image:w:80%](images/Gemini_Generated_Image_nka3wbnka3wbnka3(0).png)

<!-- end_slide -->

Setting the Scene: What I Built
===

- Real projects, real production code — not toy demos
- Range of scope: small features to full applications
- Multiple languages, platforms, and tech stacks
- Each project taught different lessons about AI-assisted development

![image:w:50%](images/Gemini_Generated_Image_nka3wbnka3wbnka3(1).png)

<!-- end_slide -->

The Journey: From Blank Page to Shipped Code
===

**Brainstorm → Spec → Build → Feedback → Ship**

Each stage has its own lessons.

![image:w:50%](images/Gemini_Generated_Image_nka3wbnka3wbnka3(2).png)

<!-- end_slide -->

<!-- jump_to_middle -->

PART 1: Before You Write Code
===

<!-- end_slide -->

Start with Brainstorming, Not Coding
===

- Use the agent as a **thinking partner**
- Challenge the agent's proposals — and let it challenge yours
- The agent surfaces assumptions you didn't know you had
- Ask _"what are the tradeoffs?"_ before writing a single line
- Ask to save a summary for the discussion

![image:w:50%](images/Gemini_Generated_Image_nka3wbnka3wbnka3(3).png)

<!-- end_slide -->

Structure Before Speed: Specs, Not Prompts
===

- Large projects → structured SDLC methodology (BMAD, AI-DLC)
- Smaller projects / features → spec-driven development
- Every feature, every bug fix = its own spec
- A spec forces you to think and gives the agent clear guardrails

![image:w:50%](images/Gemini_Generated_Image_nka3wbnka3wbnka3(4).png)

<!-- end_slide -->

Break It Down: One Spec at a Time
===

- Write **multiple specs**, not one giant one
- Each spec = one feature branch
- Review specs before the agent starts coding
- One spec → one branch → one PR

![image:w:50%](images/Gemini_Generated_Image_nka3wbnka3wbnka3(5).png)

<!-- end_slide -->

<!-- jump_to_middle -->

PART 2: Building
===

<!-- end_slide -->

Pick the Right Model for the Job
===

- **Auto / Sonnet** → planning, iteration, quick tasks
- **Opus** → heavy lifting, complex refactors, large codebases
- Don't use a sledgehammer for a nail

![image:w:50%](images/Gemini_Generated_Image_nka3wbnka3wbnka3(6).png)

<!-- end_slide -->

Use Specialized Skills for Specialized Tasks
===

- Web design, SEO, Swift/iOS, infrastructure — each has its own skill
- Don't ask a generalist prompt to do a specialist's job
- The quality difference is **dramatic**
- It's like hiring a specialist vs. asking a generalist

![image:w:50%](images/Gemini_Generated_Image_nka3wbnka3wbnka3(7).png)

<!-- end_slide -->

One Feature at a Time
===

- Design + basic scaffolding = your first "feature"
- Then: one feature per session, one feature per branch
- Resist the urge to do everything at once
- This keeps the codebase clean and the agent focused

![image:w:50%](images/Gemini_Generated_Image_nka3wbnka3wbnka3(8).png)

<!-- end_slide -->

<!-- jump_to_middle -->

PART 3: The Feedback Loop
===

<!-- end_slide -->

Feedback Loops: During a Session
===

**Code → Compile → Test → Fix → Code**

- Compiler errors → immediate syntax feedback
- Tests → behavioral feedback
- Let the agent see the errors and self-correct
- Without feedback, the agent is flying blind

![image:w:50%](images/Gemini_Generated_Image_nka3wbnka3wbnka3(9).png)

<!-- end_slide -->

Feedback Loops: Between Sessions
===

- When the agent makes repetitive mistakes → **build memory**
- Add instructions to your steering docs / system prompts / CLAUDE.md
- Your steering docs are a **living document**
- Update them after every session

![image:w:50%](images/Gemini_Generated_Image_nka3wbnka3wbnka3(10).png)

<!-- end_slide -->

<!-- jump_to_middle -->

PART 4: Working at Scale
===

<!-- end_slide -->

Context Management: Your Secret Weapon
===

- Context windows are finite — manage them deliberately
- Use **subagents** for isolated tasks
- **CLI** — run multiple agents in parallel
- **Git worktrees** — multiple branches, multiple agents, simultaneously

![image:w:50%](images/Gemini_Generated_Image_nka3wbnka3wbnka3(11).png)

<!-- end_slide -->

Code Reviews: Trust but Verify
===

- Always review AI-generated code — **all code deserves review**
- Use a second agent or tool for automated review
- Code review / re-alignment cycles
- Ask agent to identify :
  - Security issues
  - Edge cases
  - Deprecated APIs
  - Unnecessary complexity / Duplicate code

![image:w:50%](images/Gemini_Generated_Image_nka3wbnka3wbnka3(12).png)

<!-- end_slide -->

<!-- jump_to_middle -->

PART 5: Know Your Tools' Limits
===

<!-- end_slide -->

MCP Is Not Always the Answer
===

- MCP servers **bloat the context window**
- Too many tools **confuse the agent**
- Better alternatives:
  - Ad-hoc tool (shell + scripting)
  - Well-crafted skill with clear instructions
  - CLI with good `--help` docs
- **Keep your toolset lean**

![image:w:50%](images/Gemini_Generated_Image_nka3wbnka3wbnka3(13).png)

<!-- end_slide -->

Beyond Code: AI Agents for Everything
===

- Preparing podcast recordings, blog posts, talk outlines
- Research, summarization, content planning
- The same principles apply: **spec it, break it down, iterate**
- If you can work with an agent for code, you can work with it for anything

![image:w:50%](images/Gemini_Generated_Image_nka3wbnka3wbnka3(14).png)

<!-- end_slide -->

The Cheat Sheet
===

- 🧠 Brainstorm first, code second
- 📝 Spec everything — one spec, one feature, one branch
- 🔧 Right model + right skill for the job
- 🔄 Feedback loops are everything
- 🧩 Manage context: subagents, CLI, worktrees
- 👀 Always review — all code deserves scrutiny
- 🎯 MCP when you need interop, scripts when you don't

![image:w:50%](images/Gemini_Generated_Image_nka3wbnka3wbnka3(15).png)

<!-- end_slide -->

Call to Action
===

- **Today** — Pick one project and try spec-driven development
- **This week** — Set up steering docs and start building agent memory
- **This month** — Run a full feature cycle: spec → build → review → ship

_"The best way to learn is to ship something."_

![image:w:50%](images/Gemini_Generated_Image_nka3wbnka3wbnka3(16).png)

<!-- end_slide -->

Thank You — Questions?
===

✉️ stormacq@amazon.com  
🏗️ github.com/sebsto  
🖇️ linkedin.com/in/sebastienstormacq  
🦋 @sebsto.bsky.social  

![image:w:50%](images/Gemini_Generated_Image_nka3wbnka3wbnka3(17).png)
