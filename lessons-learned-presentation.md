# Lessons Learned: Coding with AI Agents

## Presentation Details
- **Duration**: 30 minutes (~18 slides)
- **Audience**: Developers / SAs familiar with AI coding tools
- **Flow**: Simple → Complex (Brainstorm → Spec → Build → Feedback → Scale → Limits → Beyond Code)

---

## Slide 1 — Title

**"What I Learned Building Real Projects with AI Coding Agents"**

- Your name, role, date
- Illustration: A human + AI pair-programming visual

> **Speaker notes**: Set the tone — this is practitioner advice, not theory. You've shipped real projects with AI agents and you're sharing what actually works.

---

## Slide 2 — Setting the Scene: What I Built

- 3-4 bullet points listing your projects (name, tech stack, scope)
- For each: one-liner on what made it interesting for AI-assisted dev

> **Speaker notes**: Walk through each project briefly. Establish credibility — these aren't toy demos, they're real apps. Mention the range: small features, full apps, different languages/platforms.

---

## Slide 3 — The Journey: From Blank Page to Shipped Code

- Visual: A timeline/flow diagram showing the stages you'll cover
- Brainstorm → Spec → Build → Feedback → Ship
- "Each stage has its own lessons"

> **Speaker notes**: This is your roadmap slide. Tell the audience you'll walk them through the full lifecycle, from the very first idea to production code, and share what works and what doesn't at each step.

---

## PART 1: BEFORE YOU WRITE CODE

---

## Slide 4 — Start with Brainstorming, Not Coding

- Use the agent as a thinking partner: ideation, design, architecture
- Challenge the agent's proposals — and let it challenge yours
- The agent is great at surfacing assumptions you didn't know you had
- Illustration: A chat screenshot showing a back-and-forth design discussion

> **Speaker notes**: Most people jump straight to "write me code." The biggest unlock is using the agent upstream — for brainstorming, challenging your own design decisions, exploring alternatives. Ask it "what are the tradeoffs?" or "what am I missing?" before writing a single line.

---

## Slide 5 — Structure Before Speed: Specs, Not Prompts

- Large projects → use a structured SDLC methodology (BMAD, AI-SDLC)
- Smaller projects / features → Spec-driven development
- Every feature, every bug fix = its own spec
- Illustration: A spec document outline (requirements, acceptance criteria, design)

> **Speaker notes**: The single biggest lesson: don't just prompt the agent. Write specs. A spec forces you to think, and it gives the agent clear guardrails. For big projects, use a full methodology. For features, a lightweight spec is enough. The key is: always have a written contract before the agent starts coding.

---

## Slide 6 — Break It Down: One Spec at a Time

- Write multiple specs, not one giant one
- Each spec = one feature branch
- Do code reviews on specs themselves (use GitHub Copilot, a second agent, or a colleague)
- Illustration: A Git branch diagram — main → feature-1, feature-2, feature-3

> **Speaker notes**: Resist the temptation to put everything in one spec. Small, focused specs lead to small, focused PRs. You can review the spec before the agent even starts — catching design issues early is 10x cheaper. I use feature branches: one spec, one branch, one PR.

---

## PART 2: BUILDING

---

## Slide 7 — Pick the Right Model for the Job

- Auto / Sonnet: planning, iteration, quick tasks
- Opus: heavy lifting, complex refactors, large codebases
- Don't use a sledgehammer for a nail
- Illustration: A simple table — Task type → Recommended model

> **Speaker notes**: Model selection matters more than people think. For planning and iterative work, a fast model keeps you in flow. For complex multi-file changes or deep reasoning, switch to a heavier model. Think of it like choosing the right tool from a toolbox.

---

## Slide 8 — Use Specialized Skills for Specialized Tasks

- Web design, SEO, Swift/iOS, infrastructure — each has its own skill/power
- Don't ask a generalist prompt to do a specialist's job
- Illustration: Icons representing different specializations (web, mobile, infra, SEO)

> **Speaker notes**: AI agents can be configured with specialized skills or powers. When you're doing iOS work, load the Swift skill. When you're doing web design, load the web design skill. The quality difference is dramatic. It's like hiring a specialist vs. asking a generalist.

---

## Slide 9 — One Feature at a Time

- Design + basic scaffolding = your first "feature"
- Then: one feature per session, one feature per branch
- Resist the urge to do everything at once
- Illustration: A kanban board with one card in "In Progress"

> **Speaker notes**: This is discipline. The agent will happily try to do 5 things at once and make a mess. Treat scaffolding as feature zero. Then go feature by feature. Each one gets its own spec, its own branch, its own review. This keeps the codebase clean and the agent focused.

---

## PART 3: THE FEEDBACK LOOP

---

## Slide 10 — Feedback Loops: During a Session

- Compiler errors → immediate syntax feedback
- Tests → behavioral feedback (does it actually work?)
- Let the agent see the errors and self-correct
- Illustration: A cycle diagram: Code → Compile → Test → Fix → Code

> **Speaker notes**: The agent is only as good as the feedback it gets. Always have the compiler running. Always have tests. When the agent sees a test failure, it can reason about the fix. Without feedback, it's flying blind. This is the single most impactful practice.

---

## Slide 11 — Feedback Loops: Between Sessions

- When the agent makes repetitive mistakes → build memory
- Add instructions to your steering docs / system prompts / CLAUDE.md
- Your steering docs are a living document — update them after every session
- Illustration: A "memory" icon with arrows pointing to a config file

> **Speaker notes**: This is the meta-lesson. If the agent keeps making the same mistake — wrong import style, wrong test framework, wrong naming convention — don't just fix it each time. Write it down in your steering docs. Next session, the agent won't make that mistake again. Your steering docs are your institutional memory.

---

## PART 4: WORKING AT SCALE

---

## Slide 12 — Context Management: Your Secret Weapon

- Context windows are finite — manage them deliberately
- Use subagents for isolated tasks
- CLI: run multiple agents in parallel
- Git worktrees: multiple branches, multiple agents, simultaneously
- Illustration: A diagram showing main agent delegating to subagents, each on its own worktree

> **Speaker notes**: As projects grow, context management becomes critical. You can't dump your entire codebase into one prompt. Use subagents for independent tasks. Use the CLI to run multiple sessions. Git worktrees let you have multiple branches checked out simultaneously — one agent per worktree, working in parallel. This is how you scale.

---

## Slide 13 — Code Reviews: Trust but Verify

- Always review AI-generated code — all code deserves review, no matter who or what wrote it
- Use a second agent or tool (GitHub Copilot) for automated review
- Look for: security issues, edge cases, unnecessary complexity, hallucinated APIs
- Illustration: A PR review screenshot with comments

> **Speaker notes**: AI-generated code is not automatically correct. Apply the same review standards you'd apply to any collaborator's code. Better yet, use a second agent to review the first agent's output. Look specifically for hallucinated APIs, missing error handling, and security issues. The agent is fast but not infallible.

---

## PART 5: KNOW YOUR TOOLS' LIMITS

---

## Slide 14 — MCP Is Not Always the Answer

- MCP servers bloat the context window — every tool description eats tokens
- Too many tools confuse the agent — it struggles to pick the right one
- Alternatives that often work better:
  - Ask the agent to generate an ad-hoc tool with shell + a scripting language
  - Write a well-crafted skill / power with clear instructions
  - Point the agent at a CLI with good `--help` documentation
- Illustration: A scale/balance — one side overloaded with MCP servers, the other side lean with a shell script and a CLI

> **Speaker notes**: There's a reflex to reach for MCP for everything. But each MCP server adds tool descriptions to the context window, and when the agent has 30+ tools to choose from, it gets confused and picks the wrong one. In practice, I've found that asking the agent to write a quick shell script on the fly, or writing a focused skill, is faster and more reliable. And sometimes the best "integration" is just a well-documented CLI — the agent can read `--help` and figure it out. Keep your toolset lean.

---

## Slide 15 — Beyond Code: AI Agents for Everything

- Preparing podcast recordings, blog posts, talk outlines
- Research, summarization, content planning
- The same principles apply: spec it, break it down, iterate
- Illustration: Icons for podcast, blog, presentation alongside code icons

> **Speaker notes**: One last lesson — AI agents aren't just for code. I use the same workflow to prepare podcast recordings, write blog posts, plan talks (including this one!). The principles are identical: start with a spec, break it down, iterate with feedback. If you've learned to work with an agent for code, you already know how to work with it for everything else.

---

## Slide 16 — Summary: The Cheat Sheet

- 🧠 Brainstorm first, code second
- 📝 Spec everything — one spec, one feature, one branch
- 🔧 Right model + right skill for the job
- 🔄 Feedback loops are everything (compiler, tests, steering docs)
- 🧩 Manage context: subagents, CLI, worktrees
- 👀 Always review — all code deserves scrutiny
- 🎯 MCP when you need interop, scripts when you don't

Illustration: A clean one-page cheat sheet visual

> **Speaker notes**: This is your takeaway slide. Pause here. Let people take a photo. These are the 7 principles that will make you dramatically more effective with AI coding agents.

---

## Slide 17 — Call to Action

- **Today**: Pick one project and try spec-driven development with an agent
- **This week**: Set up steering docs and start building agent memory
- **This month**: Run a full feature cycle — spec → build → review → ship
- "The best way to learn is to ship something."
- Illustration: A rocket launch or "start" button

> **Speaker notes**: Don't try to adopt everything at once. Start with one thing: write a spec for your next feature and let the agent implement it. Then add feedback loops. Then add steering docs. Build the muscle incrementally. The goal is to ship — not to have a perfect process.

---

## Slide 18 — Thank You / Q&A

- Your contact info
- Links to tools mentioned (Kiro, BMAD, etc.)
- "Questions?"

> **Speaker notes**: Open the floor. Expect questions about model selection, context limits, and "does this really work for production code?" Have a concrete example ready for each.
