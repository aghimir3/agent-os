# Agent OS

**An AI Operating System for autonomous project execution.**

Agent OS is an **AI Operating System** that turns a frontier coding agent into a **Recursive AI Principal**: an accountable executive agent process that can own strategy, implementation, verification, memory, recovery, reversible learning, and continuous improvement inside explicit authority boundaries.

It goes beyond a prompt, checklist, or project-management wrapper. It is an operating model for long-running AI work: the agent reasons in user-space, while Agent OS supplies the kernel primitives and Learning System that keep the work durable, safe, observable, recoverable, and able to course-correct.

---

## What Agent OS Is

Agent OS is a repo-local AI Operating System for autonomous agents.

| OS concept | Agent OS equivalent |
|---|---|
| Kernel | Authority gates, system-call boundaries, durable state, recovery, interrupts, verification |
| Process | The Recursive AI Principal and any worker agents or internal specialist passes |
| Filesystem | `agent-os/` durable project memory |
| Scheduler | Mission contracts, action portfolio, prioritization, and human action cards |
| Learning System | Learning ledger, failure modes, promotion candidates, correction log, quarantine, and demotion |
| Device drivers / adapters | Shell, git, browser, docs, web, MCP/tools, APIs, screenshots, human-actuator channel |
| System calls | File edits, shell commands, commits, tool calls, web/docs research, and human-actuator requests |
| Interrupts | Human changes, failed tests, unsafe actions, dirty git state, tool failures, context loss |
| Observability | Evidence logs, command outputs, test results, screenshots, source logs, verifier reports |

The goal is not to replace the agent's judgment with deterministic machinery. The goal is to give the agent the operating substrate it needs to stay alive, grounded, useful, and recoverable across real project work.

---

## Core Files

Save the full Agent OS prompt as:

```text
AGENT_OS.md
```

in the root of any project repository.

When bootstrapped, Agent OS creates durable state under:

```text
agent-os/
```

Example:

```text
my-project/
  AGENT_OS.md
  README.md
  agent-os/
    kernel/
    state/
    missions/
    learning/
    memory/
    recovery/
    handoff/
  src/
```

`AGENT_OS.md` is the OS specification. `agent-os/` is the durable runtime state.

---

## How To Boot

### New Or Existing Repo

Use the same boot prompt for a new repo, an empty repo, or an existing codebase:

```markdown
You are the Recursive AI Principal and Agent OS Orchestrator for this project.

Read `AGENT_OS.md` in the current directory.

Boot Agent OS:
- Identify the current execution mode.
- Inspect the repo, git state, README/docs, manifests, source files, tests, and any existing `agent-os/` state.
- Classify this as an existing project, blank/new project, or unclear/recovery case.
- Create or update the minimum viable `agent-os/` state.
- Create the Learning System files.
- Create the first Mission Contract.
- Execute the highest-leverage safe next action inside the authority envelope.

Do not ask broad clarification questions unless project context cannot be inferred and safe initialization is impossible without human input.
```

Optional context files such as `project-description.md`, product briefs, ADRs, or issue docs are useful, but not required. Agent OS should infer context from the repo first.

### Resume Work

Use this when `agent-os/` already exists:

```markdown
You are the Recursive AI Principal and Agent OS Orchestrator.

Read `AGENT_OS.md`.

Load `agent-os/handoff/latest.md` and `agent-os/memory/executive-snapshot.md`.

Resume the active mission if it is still valid. If not, reconstruct state, update the mission, and execute the next highest-leverage safe action.
```

### Recovery

Use this after crashes, compaction, interrupted work, unclear git state, or conflicting memory:

```markdown
Enter Recovery Mode.

Read `AGENT_OS.md`, then reconstruct state from `agent-os/recovery/BOOTSTRAP.md`, `agent-os/handoff/latest.md`, `agent-os/memory/executive-snapshot.md`, git status, recent commits, and current disk state.

Produce a recovery assessment before resuming material work.
```

---

## What Agent OS Does

| Capability | Why it matters |
|---|---|
| Durable memory | Important state survives chat loss, context compaction, and IDE restarts |
| Mission contracts | Work becomes explicit, scoped, and verifiable |
| Evidence court | Claims must be backed by tools, files, tests, sources, or human evidence |
| Authority envelope | The agent knows what it can do autonomously and what requires escalation |
| Human actuator cards | The human is used for identity, trust, payment, legal authority, physical-world work, and real-world evidence |
| Agent orchestration | Work can be split across worker agents or internal specialist passes without losing accountability |
| Interrupt handling | New evidence, failed checks, unsafe actions, and human updates stop blind continuation |
| Recovery protocol | Future agents can resume without relying on chat history |
| Learning System | Mission evidence becomes revised beliefs, failure modes, promotion candidates, and correction records |
| Learning quarantine | Wrong, stale, overfit, harmful, or narrowing lessons lose authority until revised, demoted, rejected, restored, or superseded |
| System improvement | Lessons become advisory notes, skills, evals, templates, automations, or kernel rules only when justified |

---

## Design Philosophy

Agent OS keeps the deterministic substrate small.

Kernel-space owns:

- Permissions and authority gates.
- Durable memory and recovery.
- System-call boundaries.
- Verification and evidence capture.
- Interrupt handling.
- Secret, privacy, security, and production-action guards.

User-space stays with the AI Principal:

- Strategy.
- Product judgment.
- Architecture judgment.
- Naming and UX taste.
- Option generation.
- Tradeoff decisions.
- Synthesis, critique, and learning.

When a recurring lesson appears, Agent OS records it as an advisory note first. It only becomes deterministic kernel behavior after repeated evidence shows that it is stable, low-ambiguity, safer to enforce, and has an escape hatch.

Self-learning follows a reversible loop:

```text
observe -> explain -> encode -> test -> promote/demote -> monitor -> recover
```

Learned patterns should widen option generation or improve judgment. If a lesson creates bad output, overfits to one case, conflicts with evidence, or narrows useful exploration, Agent OS places it in Learning Quarantine and records the correction before trusting it again.

Preservation rules:

- Evidence beats confidence.
- Advisory notes precede deterministic kernel rules.
- Learning must be reversible and scoped.
- The human remains actuator, signatory, trust channel, and physical-world interface.
- The AI Principal owns decisions, synthesis, orchestration, integration, acceptance, and outcomes.
- Kernel-space must stay small enough that it supports judgment without replacing it.

---

## Recommended Use

Best for:

- Startups and new product builds.
- Existing codebases that need stronger AI ownership.
- Long-running research or engineering projects.
- Internal tools and operational systems.
- High-autonomy coding sessions where memory, recovery, and verification matter.

Less ideal for:

- One-off scripts.
- Tiny edits where the full operating loop would be excessive.
- Work that requires legal, medical, financial, or regulated professional judgment without a human expert in the loop.

---

## Practical Rules

- Commit `AGENT_OS.md`.
- Commit the generated `agent-os/` state for real projects.
- Keep `agent-os/memory/executive-snapshot.md` short and current.
- Keep `agent-os/handoff/latest.md` updated before stopping.
- Keep `agent-os/learning/` current when missions produce reusable lessons or corrections.
- Do not store secrets, credentials, private customer data, or regulated data in Agent OS files unless there is an approved process.
- Use current docs for mutable frameworks, APIs, vendors, deployment, and security assumptions.
- Treat the human as an actuator and signatory, not the default project manager.

---

## License And Philosophy

Agent OS is provided as-is for personal and commercial use.

The core philosophy:

> Maximize useful project state change per unit of risk, time, money, and human effort while continuously improving the system's future capacity to do the same.

Agent OS treats the AI as a true principal, not a passive assistant.
