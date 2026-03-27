# Hackathon Workshop: Building with AI

## Overview
A practical, hands-on workshop on how to develop projects using AI coding agents. You'll learn how to set up your laptop, teach your AI new abilities, work in a structured cycle, and keep your projects organized — even if you've never coded before.

---

## Part 1: Laptop Setup (Mac)

### 1.1 Install Codex
Open your Terminal app and paste this command:
```
brew install codex
```
> **What this does:** Installs Codex, an AI coding assistant that runs directly in your terminal. Think of it as hiring a developer that lives inside your computer.

### 1.2 Setup Prompt: Install Your Development Environment
Once Codex is running, paste this prompt:

> "Install NVM on my machine, then install the latest LTS version of Node.js and configure it, and set up PNPM to work properly in my terminal."

Codex will handle everything automatically — no manual steps needed.

> **Why Node.js?** Node.js is the engine that powers the Skills system we'll use in Part 2. Without it, we can't install skills. Think of it like installing an app store before you can download apps.

---

## Part 2: Introduction to Skills

### 2.1 What are Skills?
Skills are ready-made instruction packages that teach your AI assistant how to do new things. Instead of explaining the same thing to your AI every time, you install a skill once and it just knows.

**Think of it like this:** If your AI assistant is a new employee, skills are the training manuals you hand them on day one.

- Written in a simple text format (Markdown)
- Work across different AI tools — not locked to one product
- Installed with a single command

### 2.2 How to Install Skills
Skills are installed using a tool called NPX — it comes bundled with Node.js (which we set up in Part 1).

The basic command pattern:
```
npx skills add <skill-name>
```

That's it. One command, and your AI gains new abilities.

### 2.3 Types of Skills
- **Community Skills** — Built by developers around the world, shared openly for anyone to use
- **Official Skills** — Built by the companies behind the AI tools (like Anthropic)
- **Personal Skills** — Custom skills you create for your own team or workflow

### 2.4 The Agent Skills Standard
Agent Skills is an open standard — meaning it's not owned by any single company. It was originally created by Anthropic (the company behind Claude) and is now supported across the industry.

**What this means for you:** A skill you install works the same way whether you're using Codex, Claude Code, Cursor, GitHub Copilot, or Gemini CLI. Write once, works everywhere.

### 2.5 Where to Find Skills
- **skills.sh** — The main directory for browsing and discovering skills
- **github.com/VoltAgent/awesome-agent-skills** — A curated collection of 1,000+ skills

---

## Part 2B: Demo — Installing Superpowers

### What is Superpowers?
Superpowers is a popular skills collection that teaches your AI assistant professional development habits. Instead of just writing code, your AI will learn to plan first, test its work, debug properly, and verify before declaring "done."

> **Analogy:** If regular AI coding is like having a fast but careless intern, Superpowers turns it into a methodical senior developer.

**Who made it:** Created by Jesse Vincent (an open-source developer), and it's been accepted into the official Claude Code marketplace — so it's trusted and well-maintained.

### How to Install
```
npx skills add obra/superpowers
```

One command. That's all it takes.

### What You Get
After installation, your AI assistant gains these structured workflows:

| What It Does | Skill Name | In Plain English |
|---|---|---|
| Thinks before coding | brainstorming | Asks you questions to refine your idea before writing any code |
| Creates a step-by-step plan | writing-plans | Breaks your project into small, manageable tasks |
| Tests its own work | test-driven-development | Writes tests first, then writes code to pass them |
| Follows the plan | executing-plans | Works through the plan with checkpoints for your review |
| Finds bugs properly | systematic-debugging | Investigates the root cause instead of guessing |
| Double-checks before finishing | verification-before-completion | Runs verification before claiming the work is done |
| Works on multiple things at once | dispatching-parallel-agents | Handles independent tasks simultaneously |
| Knows when it's done | finishing-a-development-branch | Guides you through wrapping up and merging work |

### Where Do Skills Live on Your Computer?
When you install skills, they go into a hidden folder:
- **For all projects:** `~/.claude/skills/`
- **For one specific project:** `your-project/.claude/skills/`

Each skill is just a folder containing a text file (SKILL.md) with instructions the AI reads automatically.

---

## Part 2C: Demo — Installing Anthropic's Document Skills

### What are Document Skills?
These are official skills built by Anthropic (the makers of Claude) that give your AI assistant the ability to create and edit real documents — PDFs, Word files, PowerPoint presentations, spreadsheets, and more.

> **Why this matters:** Without these skills, your AI can only write code and text. With them, it can generate full business documents, slide decks, and reports.

### How to Install

Install the full collection:
```
npx skills add anthropics/skills
```

Or install just the ones you need:
```
npx skills add anthropics/skills --skill pdf
npx skills add anthropics/skills --skill pptx
npx skills add anthropics/skills --skill docx
npx skills add anthropics/skills --skill xlsx
```

### What Document Types Are Supported?

| Skill | What It Creates | Example Use |
|---|---|---|
| pdf | PDF documents | Generate reports, extract text from existing PDFs, fill forms |
| docx | Word documents | Write proposals, add tracked changes and comments |
| pptx | PowerPoint slides | Create presentations, add speaker notes, edit layouts |
| xlsx | Excel spreadsheets | Build spreadsheets with formulas, charts, and data analysis |
| canvas-design | Images and visual art | Create posters, designs, and visual content |
| frontend-design | Web pages and components | Build professional-looking websites and dashboards |

### Bonus Skills in the Collection
The Anthropic skills package also includes:
- **brand-guidelines** — Apply company branding to any document
- **theme-factory** — Style your documents with professional themes
- **webapp-testing** — Test web applications in a browser
- **mcp-builder** — Build integrations with external services
- **skill-creator** — Create your own custom skills

> **Source:** All of these are available at github.com/anthropics/skills

---

## Part 3: The AI Development Cycle

### Two Loops, Not One
When building with AI, there are actually **two cycles** happening — one you control, and one the AI runs on its own. Understanding both is the key to working effectively.

---

### The Outer Loop (You Drive This)
This is the big-picture cycle between you and the AI:

**Step 1: Plan**
Describe what you want to build. The AI creates a detailed plan — breaking it into tasks, identifying files, and outlining steps. You review, ask questions, and refine until you're happy.

> **Tip:** The better your description, the better the plan. Be specific about what you want.

**Step 2: Execute**
Once you approve the plan, the AI starts building. **Let it work** — don't interrupt unless something goes clearly wrong. This is important: research shows that interrupting the AI mid-task actually makes the output worse. Let it finish, then review.

**Step 3: Review**
Check what was built. Does it look right? Does it work?
- **If yes:** Move to the next feature and start the cycle again
- **If no:** Go back to planning and describe what needs to change

> **Key point:** This is a continuous loop — not a one-time process. Every feature, every bug fix, every improvement goes through its own Plan → Execute → Review cycle.

---

### The Inner Loop (The AI Drives This)
Here's what most people don't realize: during Step 2 (Execute), the AI doesn't just write code once and hand it to you. It runs **its own internal cycle** — writing, testing, finding problems, fixing them, and testing again — until the result is solid.

Think of it like hiring a craftsman to build a shelf. You don't see every measurement, every cut, every sanding pass. You see the finished shelf. The AI works the same way:

1. **Write** — The AI writes the code
2. **Test** — It runs the code or tests to see if it works
3. **Observe** — It reads the error messages or test results
4. **Fix** — It figures out what went wrong and makes changes
5. **Repeat** — It tests again... and keeps looping until things work

This inner loop can run many times before the AI presents you with the final result. That's why execution sometimes takes a minute — the AI is iterating internally, steering itself toward a working solution.

> **Analogy:** When you ask a chef to make dinner, they taste the sauce, adjust the seasoning, taste again, adjust again. You only see the final plate. The AI's inner loop is the same — it self-corrects behind the scenes.

---

### The Complete Picture

```
YOUR LOOP (the outer cycle):
┌──────────────────────────────────────────────────────────┐
│                                                          │
│   ┌──────┐                                  ┌────────┐  │
│   │ PLAN │ ── You describe ──────────────→  │ REVIEW │  │
│   └──┬───┘   what you want                  └───┬────┘  │
│      │                                          │        │
│      │        AI'S LOOP (the inner cycle):      │        │
│      │       ┌─────────────────────────┐        │        │
│      └─────→ │  Write code             │        │        │
│              │     ↓                   │        │        │
│              │  Run & test             │        │        │
│              │     ↓                   │        │        │
│              │  See what failed        │        │        │
│              │     ↓                   │        │        │
│              │  Fix & try again        │        │        │
│              │     ↓                   │        │        │
│              │  Keep going until       │        │        │
│              │  it works ──────────────┼──────→ │        │
│              └─────────────────────────┘        │        │
│                                                  │        │
│      Looks good? ──Yes──→ Next feature (back to PLAN)    │
│           │                                              │
│          No ──→ Back to PLAN with feedback               │
│                                                          │
└──────────────────────────────────────────────────────────┘
```

---

### When Should You Intervene?

**Let the AI keep working when:**
- It's making progress (even if slow)
- It's running tests and fixing errors on its own
- The task has clear success criteria

**Step in when:**
- The AI seems stuck on the same error repeatedly
- The output is going in a completely wrong direction
- You realize the original plan needs to change

> **Golden rule:** You are the architect. The AI is the builder. You decide *what* to build, the AI figures out *how* to build it — including fixing its own mistakes along the way.

---

## Part 4: Context — The AI's Working Memory

### What is Context?
Context is everything the AI can "see" and remember during a conversation. Think of it as the AI's desk — it can only work with what's currently on its desk.

### Why It Matters

**Too little context:**
- The AI forgets what it was doing
- It makes decisions that contradict earlier work
- It breaks things it built before

**Too much context:**
- The AI gets overwhelmed with irrelevant information
- Responses become slower and more expensive
- Quality actually goes down — like trying to write an essay with 50 reference books open at once

### The Golden Rule
> **Keep each task focused on one clear thing.**

Feed the AI just enough information to do the current job well:
- The relevant files it needs to see
- The current plan
- Recent decisions that affect this task
- Nothing more

> **Analogy:** If you're asking a contractor to fix your kitchen faucet, you don't hand them the blueprints for the entire building. You show them the kitchen.

### Practical Tips
1. **Start fresh conversations** for new features (don't let old context pile up)
2. **Reference specific files** instead of saying "look at everything"
3. **Break big tasks into smaller ones** — each gets its own focused cycle
4. **Use agents.md** (Part 5) to give persistent context without repeating yourself

---

## Part 5: agents.md — Teaching AI Your Project's Rules

### 5.1 What is agents.md?
`agents.md` is a simple text file you place at the root of your project. It's like a **rulebook written for AI assistants** — telling them how your project works, what conventions to follow, and what not to touch.

> **Analogy:** Imagine onboarding a new team member. Instead of explaining the same rules every morning, you write them down once. That's what agents.md does — but for AI.

- It's just a regular text file (Markdown format)
- No special software needed to create it
- Adopted by over 60,000 projects worldwide

### 5.2 A Brief History
- **August 2025:** OpenAI introduced the standard alongside their Codex tool
- **December 2025:** Donated to the Linux Foundation (a neutral organization) so no single company controls it
- **Today:** A collaborative effort backed by OpenAI, Google, GitHub, Cursor, and many others

> **Why this matters:** Because it's governed by a neutral foundation, you can trust that it's not going to disappear or get locked behind a paywall.

### 5.3 Which AI Tools Support It?
Nearly every major AI coding tool reads agents.md (or its own version of it):

| AI Tool | What It Reads | Status |
|---|---|---|
| OpenAI Codex | AGENTS.md | Created the standard |
| GitHub Copilot | AGENTS.md | Full support |
| Cursor | AGENTS.md | Full support |
| Google Gemini CLI | GEMINI.md + AGENTS.md | Full support |
| Claude Code | CLAUDE.md | Anthropic's version |
| Windsurf | AGENTS.md | Full support |
| Aider, Devin, Zed | AGENTS.md | Full support |

> **Note:** Some tools use their own filename (like `CLAUDE.md` for Claude Code), but they all serve the same purpose. You can have multiple files for different tools in the same project.

### 5.4 Which File Should You Use?
It depends on your situation:

**If you only use one AI tool** — just use that tool's file:
- Only using Claude Code? → Create `CLAUDE.md` and you're done
- Only using Gemini CLI? → Create `GEMINI.md` and you're done
- Only using Codex or Copilot? → Create `AGENTS.md` and you're done

That's the simplest approach. No need to overthink it.

**If your team uses multiple AI tools** — some people use a neat trick: write one `AGENTS.md` file and create shortcuts (called symlinks) so the other tools read from it too. This way you maintain one file instead of keeping several in sync.

```bash
# Write your rules once in AGENTS.md
touch AGENTS.md

# Create shortcuts so Claude and Gemini read the same file
ln -s AGENTS.md CLAUDE.md
ln -s AGENTS.md GEMINI.md
```

Your project would look like this:
```
your-project/
├── AGENTS.md     ← The real file (your rules live here)
├── CLAUDE.md     → shortcut to AGENTS.md
├── GEMINI.md     → shortcut to AGENTS.md
```

> **What's a symlink?** It's like a shortcut on your desktop. `CLAUDE.md` doesn't contain anything itself — it just points to `AGENTS.md`. When Claude Code opens `CLAUDE.md`, it actually reads `AGENTS.md`.

> **Bottom line:** Use one file for one tool. Use the symlink trick only if you're juggling multiple AI tools and want to keep things tidy.

### 5.5 What Should You Put Inside?
Based on an analysis of 2,500+ real projects by GitHub, the most effective agents.md files include six things:

**1. Commands**
The exact commands to run your project — copy-paste ready:
```
npm run dev       # Start the project
npm test          # Run tests
npm run build     # Build for production
```

**2. Testing Rules**
How tests are organized and how to run them.

**3. Project Structure**
A map of where things live in your project:
```
src/
├── components/   # UI pieces
├── pages/        # App screens
├── utils/        # Helper functions
└── api/          # Backend connections
```

**4. Code Style**
Naming conventions, formatting rules, and patterns your team follows.

**5. Git Workflow**
How branches are named, how commits are formatted, and the review process.

**6. Boundaries — The Three Tiers**
This is the most important section. Tell the AI what it's allowed to do:

```
ALWAYS DO (no permission needed):
- Read and analyze files
- Run linting and formatting
- Write tests

ASK FIRST (needs my approval):
- Install new packages
- Create new files
- Change the database

NEVER DO:
- Delete files without asking
- Push code without review
- Modify environment variables or secrets
- Install low-quality or untrusted dependencies
```

> **Important safety rule:** When the AI needs to install a package or library, tell it to only use **well-known, highly-downloaded, and highly-starred** projects. Avoid obscure or low-quality dependencies — they can introduce security risks or break your project. Add this to your AGENTS.md boundaries.

### 5.6 Best Practices
- **Keep it short** — under 150 lines. The AI loads this into memory, so shorter is better
- **Be specific** — "Use camelCase for variables" is better than "follow best practices"
- **Show examples** — actual code snippets beat abstract descriptions
- **Start simple** — begin with just commands and boundaries, add more over time
- **Iterate** — when the AI makes a mistake, add a rule to prevent it next time

### 5.7 Live Demo: Let's Create One Together
We'll walk through creating an agents.md for a sample hackathon project:

**Step 1:** Create the file at your project root
```
touch AGENTS.md
```

**Step 2:** Add your commands
```markdown
## Commands
npm install       # Install dependencies
npm run dev       # Start development server
npm test          # Run tests
```

**Step 3:** Add your project structure
```markdown
## Project Structure
src/
├── components/   # Reusable UI components
├── pages/        # App pages/screens
└── styles/       # CSS and styling
```

**Step 4:** Add boundaries
```markdown
## Boundaries

ALWAYS DO:
- Read files before modifying them
- Run tests after making changes

ASK FIRST:
- Installing new dependencies
- Creating new files

NEVER DO:
- Delete existing files
- Modify .env or secret files
- Push directly to the main branch
- Install unvetted, low-download, or low-star dependencies
```

**Step 5:** Create symlinks so all AI tools read the same file
```bash
ln -s AGENTS.md CLAUDE.md
ln -s AGENTS.md GEMINI.md
```

**Step 6:** Save and test — open your AI tool and ask it to do something. Watch how it follows your rules automatically.

### 5.8 Key Resources
- **Official website:** agents.md
- **GitHub repository:** github.com/agentsmd/agents.md
- **Best practices guide:** GitHub blog — "How to write a great agents.md" (lessons from 2,500+ repos)

---

## Summary: The Modern AI Development Workflow

| Step | What You Do | What the AI Does |
|---|---|---|
| **Setup** | Install tools, run setup commands | Configures your environment |
| **Skills** | Install relevant skills | Loads specialized knowledge |
| **agents.md** | Write your project rules once | Follows them every session |
| **Plan** | Describe the task | Breaks it into steps |
| **Execute** | Review and approve the plan | Builds the feature |
| **Review** | Check the output | Waits for your feedback |
| **Repeat** | Move to the next task | Starts the cycle again |

> **Remember:** The cycle never stops. Every feature, every fix, every improvement goes through Plan → Execute → Review. And with agents.md and skills in place, your AI gets better at understanding your project with every session.

---

## Quick Reference: Commands You'll Use Today

```bash
# Install Codex
brew install codex

# Install Superpowers (development workflow skills)
npx skills add obra/superpowers

# Install Anthropic Document Skills (PDF, slides, etc.)
npx skills add anthropics/skills

# Browse installed skills
npx skills list

# Create your project rules file
touch AGENTS.md
```
