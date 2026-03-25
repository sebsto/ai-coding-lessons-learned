# What I Learned Building Real Projects with AI Coding Agents

A 30-minute talk sharing practical lessons from building real production projects with AI coding agents — from brainstorming to shipped code.

## Abstract

AI coding agents are everywhere, but most advice stops at "write better prompts." This talk goes further. Drawing from real-world experience shipping production applications with AI agents, it covers the full development lifecycle: brainstorming and design with the agent, spec-driven development, model and skill selection, feedback loops (compiler, tests, steering docs), context management at scale (subagents, CLI, git worktrees), code review practices, and knowing when MCP helps vs. when a shell script is better. Attendees walk away with a concrete, actionable cheat sheet they can apply to their next project.

## Speaker

Sébastien Stormacq  
✉️ stormacq@amazon.com  
🏗️ [github.com/sebsto](https://github.com/sebsto)  
🖇️ [linkedin.com/in/sebastienstormacq](https://linkedin.com/in/sebastienstormacq)  
🦋 [@sebsto.bsky.social](https://bsky.app/profile/sebsto.bsky.social)

## Running the presentation

### Install presenterm

```bash
# macOS
brew install presenterm

# Cargo
cargo install presenterm

# Other options: https://github.com/mfontanini/presenterm
```

### Launch

```bash
git clone https://github.com/sebsto/ai-coding-lessons-learned.git
cd ai-coding-lessons-learned
presenterm presentation.md
```

Use arrow keys or `hjkl` to navigate. Press `?` for all key bindings.

## License

This project is licensed under the Apache License, Version 2.0. See [LICENSE](LICENSE) for details.
