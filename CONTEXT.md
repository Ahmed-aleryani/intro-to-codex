# Workshop Development Context

## Project
Internal company hackathon workshop — "Building with AI"

## Roles
- **Workshop Organizer:** Running the hackathon event
- **Ahmed:** Acting as mentor, preparing workshop content and slides

## Audience
Most attendees are beginners and non-technical. All content uses plain language, analogies, and avoids unexplained jargon.

## Workshop Structure (5 Parts)
1. **Laptop Setup** — Install Codex via Homebrew, set up Node.js/NVM/PNPM via AI prompt
2. **Introduction to Skills** — Agent Skills open standard, NPX installation, Superpowers demo, Anthropic Document Skills demo
3. **The AI Development Cycle** — Dual-loop model: outer human loop (Plan/Execute/Review) + inner AI loop (write/test/fix/repeat)
4. **Context Management** — AI's working memory, too much vs too little, keeping tasks focused
5. **agents.md** — Deep dive: history, cross-tool support, symlink approach, what goes inside, boundaries, live demo

## Key Research Findings

### agents.md
- Originated from OpenAI Codex (Aug 2025), donated to Linux Foundation (Dec 2025)
- Vendor-neutral open standard, adopted by 60,000+ repos
- Supported by: Codex, GitHub Copilot, Cursor, Gemini CLI, Windsurf, Aider, Devin, Zed
- Claude Code uses CLAUDE.md (Anthropic's variant)
- Modern practice: use one file per tool, OR symlink CLAUDE.md/GEMINI.md to AGENTS.md for multi-tool setups
- Six core sections from GitHub's 2,500-repo analysis: Commands, Testing, Project Structure, Code Style, Git Workflow, Boundaries
- Best practices: under 150 lines, specific over abstract, start lean, iterate
- Sources: agents.md (official site), github.com/agentsmd/agents.md, GitHub blog

### Superpowers Skills
- Open-source framework by Jesse Vincent (obra), NOT Anthropic — but in Claude Code marketplace since Jan 2026
- Install: `npx skills add obra/superpowers`
- Includes: brainstorming, writing-plans, test-driven-development, executing-plans, systematic-debugging, verification-before-completion, dispatching-parallel-agents, finishing-a-development-branch
- NPX Skills CLI by Vercel Labs
- Skills directory: skills.sh
- Skills installed to: ~/.claude/skills/ (global) or .claude/skills/ (project)

### Anthropic Document Skills
- First-party skills from Anthropic at github.com/anthropics/skills
- Install: `npx skills add anthropics/skills`
- Formats: PDF, DOCX, PPTX, XLSX, canvas-design, frontend-design
- Additional: brand-guidelines, theme-factory, webapp-testing, mcp-builder, skill-creator, doc-coauthoring, internal-comms
- PPTX skill manipulates raw XML (not python-pptx)

### AI Development Cycle (Dual Loop)
- Outer loop (human-driven): Plan -> Execute -> Review -> repeat
- Inner loop (AI-driven, during Execute): Write -> Test -> Observe -> Fix -> Repeat until working
- Sources: Anthropic "Building Effective Agents", OpenAI "Unrolling the Codex Agent Loop", Simon Willison "Designing Agentic Loops"
- Key insight: interrupting agents mid-task degrades output quality
- Plan mode available in Claude Code (Shift+Tab twice), Codex (/plan), Cursor (Plan mode)

### Dependency Safety
- Always install only well-known, highly-downloaded, highly-starred packages
- Avoid obscure or low-quality dependencies — security risk
- Add as a boundary rule in agents.md

## Key Decisions Made
1. agents.md section: Full deep dive with history, cross-tool comparison, live demo
2. Skills demos: Two separate sections (Superpowers + Anthropic Document Skills)
3. Symlink approach: Presented as optional trick for multi-tool teams, not the default
4. Output: Updated workshop outline + PPTX slides
5. Tone: Beginner-friendly, plain English, analogies over definitions

## Files
- `workshop_outline.md` — Complete workshop outline (source of truth for content)
- `CONTEXT.md` — This file (conversation context and research findings)
- `presentation.pptx` — Generated slide deck

## Date
March 27, 2026
