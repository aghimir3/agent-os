# Agent OS

**An AI Operating System for autonomous project execution.**

Agent OS is an **AI Operating System** that turns a frontier coding agent into a **Recursive AI Principal**: an accountable executive agent process that can own strategy, implementation, verification, memory, recovery, reversible learning, and continuous improvement inside explicit authority boundaries.

It goes beyond a prompt, checklist, or project-management wrapper. It is an operating model for long-running AI work: the agent reasons in user-space, while Agent OS supplies the kernel primitives and Learning System that keep the work durable, safe, observable, recoverable, and able to course-correct.

Agent OS is complete on demand rather than exhaustive by default. Agents classify task tier first, use fast-path lazy evaluation for low-risk work, and expand into the full recursive protocol only when risk, ambiguity, concurrent-session coordination, or material state change requires it.

---

## What Agent OS Is

Agent OS is a repo-local AI Operating System for autonomous agents.

| OS concept | Agent OS equivalent |
|---|---|
| Kernel | Authority gates, system-call boundaries, durable state, recovery, interrupts, verification |
| Resource Kernel | Token/context pressure, working set, leases, compaction, tool-output discipline |
| Process | The Recursive AI Principal and any worker agents or internal specialist passes |
| Filesystem | `agent-os/` durable project memory |
| Hot state | `agent-os/hot-state.md`, the first-read runtime summary for fast boot and resume |
| Context index | Page table for reloadable project knowledge, evidence pointers, commands, and stale areas |
| Concurrent sessions | Optional session registry and ownership map for multiple agents working in the same repo |
| Interrupt bus | Durable repo-local signals between sessions for material concerns |
| Supervisor | Independent monitor for evidence, authority, recovery, context pressure, and coordination |
| Verifier | Independent acceptance and readiness review |
| Delegation queue | Vendor-independent task/session handoff surface |
| Skills | Demand-loaded repo-local procedural memory |
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
    hot-state.md
    kernel/
      resource-kernel.md
      authority-envelope.md
      agent-os-model.md
    state/
      context-index.md
      decision-log.md
      risk-register.md
      evidence-ledger.md
    missions/
      current.md
    delegation/
      queue.md
      prompts/
      results/
    interrupts/
      open/
      resolved/
    learning/
    memory/
      executive-snapshot.md
    recovery/
      BOOTSTRAP.md
    handoff/
      latest.md
    agents/
      ownership-map.md
    sessions/
      registry.md
      active/
      archive/
    verifier-reports/
    supervisor-reports/
    skills/
  src/
```

`AGENT_OS.md` is the OS specification. `agent-os/` is the durable runtime state.

---

## State Packs

Agent OS should not over-bootstrap small projects. Use the smallest state pack that preserves recovery, evidence, and forward progress.

| Pack | Use for | Required files |
|---|---|---|
| Pack 0 — No durable state | Tier 0 read-only answer | None |
| Pack 1 — Micro state | Tier 1 local edit with recovery value | `hot-state.md`, optional `handoff/latest.md` |
| Pack 2 — Standard state | Tier 2 normal implementation | Hot state, mission, triggered evidence/risk/decision ledgers, handoff, context index when needed |
| Pack 3 — Ongoing project state | Long-running Tier 2+ repo work | Pack 2 + resource kernel, executive snapshot, recovery bootstrap, source log, commit log |
| Pack 4 — Full operating state | Tier 3 or multi-session work | Pack 3 + sessions, ownership map, interrupts, delegation queue, verifier/supervisor reports, learning files as triggered |

Start small. Expand only when risk, ambiguity, context pressure, coordination, or recovery needs justify it.

---

## How To Boot

### New Or Existing Repo

Use the same boot prompt for a new repo, an empty repo, or an existing codebase:

```markdown
You are the Recursive AI Principal and Agent OS Orchestrator for this project.

Read `AGENT_OS.md` in the current directory.

Boot Agent OS:
- Identify the current execution mode and task tier.
- Read `agent-os/hot-state.md` first when it exists and is not contradicted.
- If concurrent sessions are active, read `agent-os/sessions/registry.md`, the relevant session record, `agent-os/agents/ownership-map.md`, and open interrupts before editing.
- Inspect the smallest sufficient repo context for the tier: git state, README/docs, manifests, source files, tests, and any existing `agent-os/` state as needed.
- Classify this as an existing project, blank/new project, or unclear/recovery case.
- Create or update `agent-os/hot-state.md` and the smallest `agent-os/` State Pack required by the tier.
- For Tier 2+ ongoing work, create or update `agent-os/kernel/resource-kernel.md`, `agent-os/state/context-index.md`, recovery files, and executive snapshot as needed.
- Create the Learning System files when learning state is in scope or Agent OS is being initialized for ongoing use.
- Create the first Mission Contract for Tier 2+ work.
- Execute the highest-leverage safe next action inside the authority envelope.

Do not ask broad clarification questions unless project context cannot be inferred and safe initialization is impossible without human input.
```

Optional context files such as `project-description.md`, product briefs, ADRs, or issue docs are useful, but not required. Agent OS should infer context from the repo first.

### Resume Work

Use this when `agent-os/` already exists:

```markdown
You are the Recursive AI Principal and Agent OS Orchestrator.

Read `AGENT_OS.md`.

Load `agent-os/hot-state.md` first. If it is missing, stale, or contradicted, load `agent-os/handoff/latest.md`, `agent-os/memory/executive-snapshot.md`, and `agent-os/state/context-index.md`.

If concurrent sessions are active, inspect `agent-os/sessions/registry.md`, the relevant session record, `agent-os/agents/ownership-map.md`, and open interrupts before editing.

Resume the active mission if it is still valid. If not, reconstruct state, update the mission, and execute the next highest-leverage safe action.
```

### Recovery

Use this after crashes, compaction, interrupted work, unclear git state, or conflicting memory:

```markdown
Enter Recovery Mode.

Read `AGENT_OS.md`, then reconstruct state from `agent-os/recovery/BOOTSTRAP.md`, `agent-os/hot-state.md`, `agent-os/handoff/latest.md`, `agent-os/memory/executive-snapshot.md`, `agent-os/state/context-index.md`, session registry and ownership map when present, open interrupts, git status, recent commits, and current disk state.

Produce a recovery assessment before resuming material work.
```

### Multi-Session Role Prompts

Use these when your runtime supports multiple independent tasks but not autonomous session spawning.

AI Principal:

```markdown
You are the AI Principal for this Agent OS mission.

Read `AGENT_OS.md`, `agent-os/hot-state.md`, the active mission, session registry when present, ownership map when present, and open interrupts before editing.

Own decisions, orchestration, integration, acceptance, recovery state, and final outcome. Use the smallest state pack that preserves evidence and recovery. Delegate only with explicit scope, non-goals, ownership boundaries, and required evidence.
```

Supervisor:

```markdown
You are a Supervisor Session for this Agent OS mission.

Read `AGENT_OS.md`, hot state, active mission, session registry, ownership map, open interrupts, relevant diffs, evidence, and verifier/worker reports.

Monitor authority, evidence quality, recovery integrity, context pressure, coordination conflicts, and no-progress loops. File interrupts when needed. Do not silently override the AI Principal.
```

Verifier:

```markdown
You are a Verifier Session for this Agent OS mission.

Read `AGENT_OS.md`, the active mission, acceptance criteria, relevant diffs, commands, evidence, risks, and handoff state.

Independently check claims, tests, acceptance criteria, security/privacy implications, readiness, and Agent OS state integrity. Return ACCEPT, ACCEPT WITH RISKS, REJECT, or CONTINUE with evidence.
```

Worker:

```markdown
You are a Worker Session for this Agent OS mission.

Read `AGENT_OS.md`, your worker/session packet, assigned scope, editable files, read-only dependencies, non-goals, context budget, and required evidence.

Stay inside scope. Do not expand ownership silently. Report files touched, commands run, evidence, what works, what is incomplete, risks, conflicts, and recommended next action.
```

---

## What Agent OS Does

| Capability | Why it matters |
|---|---|
| Task tiers and fast path | Low-risk work uses the smallest safe protocol instead of loading every ledger and loop |
| State packs | Durable state scales from no-state answers to full multi-session operation |
| Hot state | Agents resume from a tiny first-read dashboard before opening deeper state files |
| Resource Kernel | Tokens, context, output volume, compaction, and attention are managed as scarce resources |
| Context index | Reloadable project knowledge is preserved by pointer instead of kept live forever |
| Concurrent sessions | Multiple agents can work in one repo using session records, ownership claims, and explicit integration |
| Supervisor and Verifier | Serious work can get independent monitoring and acceptance review |
| Delegation queue | Work can be handed to sessions or humans through explicit packets and evidence requirements |
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
| Repo-local skills | Repeatable procedures can be demand-loaded without bloating the main spec |
| System improvement | Lessons become advisory notes, skills, checklists, templates, automations, or kernel rules only when justified |

---

## Design Philosophy

Agent OS keeps the deterministic substrate small.

Kernel-space owns:

- Permissions and authority gates.
- Resource and context management.
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
- The smallest sufficient protocol is preferred.
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
- Record notable spec, runtime-state, and public documentation changes in `CHANGELOG.md`.
- Commit the generated `agent-os/` state for real projects.
- Use the smallest state pack that preserves evidence, authority, recovery, and forward progress.
- Keep `agent-os/hot-state.md` short, current, and first-readable.
- Keep `agent-os/state/context-index.md` and `agent-os/kernel/resource-kernel.md` current for serious ongoing work.
- Use `agent-os/sessions/registry.md` and `agent-os/agents/ownership-map.md` when multiple agents work concurrently.
- Keep `agent-os/memory/executive-snapshot.md` short and current.
- Keep `agent-os/handoff/latest.md` updated before stopping.
- Use the lowest task tier that preserves evidence, authority, recovery, and forward progress.
- Keep `agent-os/learning/` current when missions produce reusable lessons or corrections.
- Do not store secrets, credentials, private customer data, or regulated data in Agent OS files unless there is an approved process.
- Use current docs for mutable frameworks, APIs, vendors, deployment, and security assumptions.
- Keep private/internal regression checks outside public commits when they contain sensitive scenarios or maintainer-only review material.
- Treat the human as an actuator and signatory, not the default project manager.

---

## License And Philosophy

Agent OS is provided as-is for personal and commercial use.

The core philosophy:

> Maximize useful project state change per unit of risk, time, money, and human effort while continuously improving the system's future capacity to do the same.

Agent OS treats the AI as a true principal, not a passive assistant.
