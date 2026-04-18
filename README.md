# Next Level Web Development — Programming Hero (Level 2, Batch 7)

A personal learning repository tracking my journey through the **Next Level Web Development** course by Programming Hero. This repo contains my code experiments, practice projects, and detailed Markdown notes organized by mission and module.

## Table of Contents

- [About](#about)
- [Repository Structure](#repository-structure)
- [Curriculum Roadmap](#curriculum-roadmap)
- [Current Progress](#current-progress)
- [How I Use This Repo](#how-i-use-this-repo)
- [AI Assistant Configuration](#ai-assistant-configuration)
- [Commit Convention](#commit-convention)
- [License](#license)

## About

This is a **structured learning environment**, not a production codebase. Every folder represents a step in the curriculum, and every `README.md` inside a topic folder holds my personal notes, mental models, and interview-style Q&A for that concept.

**Learning philosophy:** comprehension over quick fixes — explanations, analogies, and the "why" behind each pattern are prioritized over pasted solutions.

## Repository Structure

```
PH-Level2-B7/
├── AGENT.md                 # Single source of truth for AI assistant rules
├── CLAUDE.md                # Pointer stub → AGENT.md
├── GEMINI.md                # Pointer stub → AGENT.md
├── README.md                # You are here
└── mission-<n>/             # Sequential missions (0 → 7)
    └── <topic>/             # Topic area (e.g. critical-thinking-in-javascript)
        └── module-<n>-<name>/
            └── <lesson>/    # Individual lessons with code + README.md notes
```

Each lesson folder typically contains:

- Code experiments (`.js`, `.ts`, `.html`, etc.)
- A `README.md` with structured notes, cheat sheets, and interview questions

## Curriculum Roadmap

| Mission   | Focus Area                      | Status      |
| --------- | ------------------------------- | ----------- |
| mission-0 | Critical Thinking in JavaScript | In Progress |
| mission-1 | —                               | Not Started |
| mission-2 | —                               | Not Started |
| mission-3 | —                               | Not Started |
| mission-4 | —                               | Not Started |
| mission-5 | —                               | Not Started |
| mission-6 | —                               | Not Started |
| mission-7 | —                               | Not Started |

> Roadmap will be updated as each mission is unlocked in the course.

## Current Progress

**Active mission:** [mission-0 — Critical Thinking in JavaScript](mission-0/critical-thinking-in-javascript/)

**Active module:** [module-1 — Mindset over Syntax](mission-0/critical-thinking-in-javascript/module-1-mindset-over-syntax/)

Lessons covered so far:

- 1.1 — Intro
- 1.2 — Mindset foundations
- 1.3 — Problem-solving approach
- 1.4 — What is an algorithm, and why web development needs it
- 1.5 — Abstract idea of Big O notation
- 1.6 — Visual comparison of time complexities
- 1.7 — Array methods and their time complexities
- 1.8 — In progress

See the full [commit log](https://github.com/souravxdev/ph-level2-b7) for granular updates.

## How I Use This Repo

1. **Watch the lesson** on the Programming Hero platform.
2. **Code along** inside the corresponding lesson folder.
3. **Take notes** in the folder's `README.md` using clean Markdown (tables, code blocks, diagrams).
4. **Self-quiz** — append 5–6 interview-style questions with answers at the bottom of each module's `README.md`.
5. **Commit frequently** using versioned messages (see convention below).

## AI Assistant Configuration

This repo is configured to work efficiently with multiple AI coding assistants:

- **[AGENT.md](AGENT.md)** — the single source of truth containing persona, learning rules, slash commands, and token-efficiency guidelines.
- **[CLAUDE.md](CLAUDE.md)** and **[GEMINI.md](GEMINI.md)** — thin stubs pointing back to `AGENT.md` to avoid duplication.

Custom slash commands available during AI sessions (defined in `AGENT.md`):

| Command     | Behavior                                                         |
| ----------- | ---------------------------------------------------------------- |
| `/explain`  | Line-by-line breakdown of selected code                          |
| `/note`     | Format the current topic into a `README.md`-ready cheat sheet    |
| `/quiz`     | 3 MCQ/short-answer questions on the open file (answers withheld) |
| `/refactor` | Suggest cleaner alternatives with the reasoning                  |

## Commit Convention

Commits follow a lightweight versioned format:

```
<mission>.<module>.<lesson> <past-tense verb> <concise description>
```

Examples from the log:

- `0.1.7 learned array methods and their time complexities`
- `0.1.5 learned abstract idea of big o notation`
- `0.1.4 learned what is algorithm and why we need it in webdevelopment`

## License

This repository is for personal learning. Course content and curriculum belong to **Programming Hero**.
