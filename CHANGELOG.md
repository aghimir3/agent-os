# Changelog

This file records meaningful changes to Agent OS.

Agent OS does not use formal product releases. The core product is `AGENT_OS.md`; updates land on the main branch as the operating specification evolves. Changelog entries are organized by date and theme rather than version number.

Use this file to explain material changes to `AGENT_OS.md` and its public companion docs: what changed, why it matters, what behavior was preserved or restored, and how the change was checked.

## 2026-05-30 - Operating Model Update

### Added

- Added context/resource management as a first-class Agent OS concern, including context pressure states, working sets, context leases, tool-output discipline, compaction policy, and no-progress guards.
- Added `agent-os/kernel/resource-kernel.md` and `agent-os/state/context-index.md` to the minimum ongoing state model for serious work.
- Added a vendor-independent concurrent-session model with session registry, active session records, ownership map, interrupt bus, supervisor/verifier/worker roles, delegation queue, and conflict-resolution policy.
- Added Agent OS self-hosting mode for edits to `AGENT_OS.md`, kernel rules, state schemas, recovery behavior, learning policy, and related boot behavior.
- Added self-hosting, resource-kernel, context-index, ownership-map, and interrupt coverage to the landing page and README boot guidance.

### Changed

- Reworked task-tier, execution-mode, recovery, and persistence guidance to account for context pressure, session coordination, and resource constraints.
- Expanded mission contracts, action portfolio entries, evidence checks, principal reports, and handoff templates with context/resource and session-coordination fields.
- Updated boot, resume, and recovery instructions to load hot state first, then context index, handoff, executive snapshot, session registry, ownership map, and open interrupts when relevant.
- Updated the landing page metadata, runtime-state tree, copyable boot prompt, architecture descriptions, capability cards, and system-call trace to reflect the newer Agent OS model.

### Restored

- Restored worker/session packet guidance, specialist perspective roster, verifier report template, supervisor report template, ownership map template, latest handoff template, commit examples, preferred commit command shape, and commit log template so the new structure does not lose functionality from the last committed version.

### Verification

- Ran `git diff --check`; only Windows LF-to-CRLF warnings were reported for markdown/HTML files.
- Confirmed VS Code diagnostics report no errors for `AGENT_OS.md`, `README.md`, and `index.html`.
