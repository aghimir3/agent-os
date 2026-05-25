# Recursive AI Principal Harness
**Turn any AI into a true autonomous project owner and execution engine.**

This is a complete operating system for AI-driven projects. It transforms your AI (Claude, Cursor, Grok, etc.) into the **Recursive AI Principal** — a strategic control plane that owns strategy, execution, memory, verification, recovery, and continuous improvement.

It is designed for serious, long-running projects where you want the AI to behave like a co-founder or principal engineer rather than a helpful assistant.

---

## Where to Save This File

### Recommended Location

Save the **full harness** (the long prompt you received) as:

**`AI_PRINCIPAL.md`**  
in the **root** of your project folder.

**Example project structure:**

```
my-project/
├── AI_PRINCIPAL.md               ← The full harness (paste everything here)
├── README.md                     ← This file (optional but recommended)
├── agency-os/                    ← Created automatically by the AI
│   ├── kernel/
│   ├── state/
│   ├── missions/
│   ├── memory/
│   └── ...
├── src/
└── ...
```

### Why the root?

- The AI needs easy access to read it at the start of every session.
- It keeps everything self-contained in one folder.
- It makes the harness portable — you can copy the entire project folder and it still works.

---

## How to Use the Harness

### Step 1: First-Time Setup (New Project)

1. Create your project folder.
2. Save the **entire harness content** as `AI_PRINCIPAL.md` in the root.
3. Open your AI (Cursor, Claude, Grok, etc.).
4. Paste this **initial bootstrap prompt**:

```markdown
You are the Recursive AI Principal for this project.

Read the complete harness from `AI_PRINCIPAL.md` in the current directory.

Then read section 0 ("Project I Want To Build") from the same file.

Operate exactly according to the Prime Directive, Authority Envelope, Recursive Agency Loop, and all protocols defined in the harness.

Begin by:
- Identifying the current execution mode
- Creating the minimum viable Agency OS state in `agency-os/`
- Creating the first Mission Contract
- Executing the highest-leverage first action

Do not ask broad clarification questions unless the project description is completely missing or impossible to initialize safely.
```

5. (Strongly recommended) Also create a file called `project-description.md` containing your Section 0 content. This makes future sessions cleaner.

### Step 2: Every Future Session

Use this shorter, powerful prompt:

```markdown
You are the Recursive AI Principal.

Load the full harness from `AI_PRINCIPAL.md`.

Read the latest handoff from `agency-os/handoff/latest.md` and the executive snapshot from `agency-os/memory/executive-snapshot.md`.

Resume operation under the current mission. Execute the next highest-leverage action according to the harness rules. Create a new mission if needed.
```

---

## How to Add This Harness to an Existing Project

You can bring the full power of the Recursive AI Principal to projects that are already underway.

### Recommended Approach

1. Copy `AI_PRINCIPAL.md` into the **root** of your existing project.
2. (Optional but recommended) Create an empty `agency-os/` folder so the AI can populate it cleanly.
3. Start a new AI session with this **existing-project prompt**:

```markdown
You are the Recursive AI Principal for this project.

Read the complete harness from `AI_PRINCIPAL.md` in the current directory.

**This is an existing project.** Do not treat it as a blank slate.

First actions:
1. Inspect the current directory, git status, and key files.
2. Check if `agency-os/` already exists. If it does, read the latest handoff and executive snapshot.
3. If `agency-os/` does not exist or is incomplete, create the minimum viable state.
4. Run a quick recovery assessment to understand the current state of the project.
5. Identify the highest-leverage next action based on what already exists.

Then operate fully according to the Prime Directive, Authority Envelope, and all rules in the harness.
```

### What the AI Will Do on Existing Projects

- Respect your current codebase, tech stack, and architecture
- Create `agency-os/` state on top of what you already have
- Generate a recovery report if the project state is unclear
- Propose improvements, refactors, or new features with full evidence-based reasoning
- Gradually bring the project under the same rigorous memory, verification, and self-improvement system

**Pro tip**: The first session on an existing project is often the most valuable — the AI will give you a clear "State of the Union" report and a prioritized action plan.

---

## What This Harness Actually Does

| Capability                    | What It Replaces                  | Benefit |
|------------------------------|-----------------------------------|-------|
| Durable memory (`agency-os/`) | Chat history                      | Survives context loss & crashes |
| Evidence-based execution      | "I think this works"              | Real verification + proof |
| Recursive self-improvement    | Static prompts                    | Gets smarter every session |
| Built-in recovery             | Manual state reconstruction       | Resume after any interruption |
| Clear authority boundaries    | Vague "don't do X" rules          | Safe high-autonomy operation |
| Mission contracts             | Vague to-do lists                 | Precise, verifiable objectives |
| Tech Stack Council            | Personal preference               | Evidence-based stack decisions |
| Human Actuator Cards          | "Can you do this for me?"         | Clear delegation to you |

---

## Pro Tips for Maximum Leverage

1. **Never start a session without reading the handoff**
   - Always include the short prompt above.

2. **Let the AI create `agency-os/`**
   - Do not create the folder manually. The harness knows how to bootstrap it.

3. **Use it for the right kind of work**
   - Best for: Startups, internal tools, research projects, complex features, long-term initiatives.
   - Less ideal for: One-off scripts or tiny tasks (you can temporarily relax rules).

4. **Keep your project description fresh**
   - Update section 0 / `project-description.md` as your vision evolves.

5. **Review the executive snapshot regularly**
   - It's designed to be read in under 2 minutes and tells any future AI exactly where you are.

6. **Commit the `agency-os/` folder**
   - It contains your project's real memory and should be version-controlled.

---

## Quick Reference Commands

| Goal                              | Prompt to Use |
|-----------------------------------|-------------|
| Start fresh project               | Full bootstrap prompt (see above) |
| Resume existing project           | Short "You are the Recursive AI Principal" prompt |
| Add harness to existing project   | "Existing project" prompt (see section above) |
| Force recovery after crash        | Add: "Enter Recovery Mode and reconstruct state from disk" |
| Create new mission                | "Create a new Mission Contract for [objective]" |
| Review current state              | "Show me the current executive snapshot and active mission" |

---

## License & Philosophy

This harness is provided as-is for personal and commercial use.

The core philosophy is simple:

> **"Maximize useful project state change per unit of risk, time, money, and human effort — while continuously improving the system's future capacity to do the same."**

It treats the AI as a true principal, not a tool.

---

**Now go build something great.**

*Save `AI_PRINCIPAL.md` → Start a new AI session → Watch it take ownership.*
