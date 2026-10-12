---
name: memory-bank-autopilot
description: Low-friction persistent project memory workflows for Codex. Use when the user mentions Memory Bank, persistent memory, project memory, VAN, PLAN, THINK, CREATIVE, DO, BUILD, LOG, STATUS, REFLECT, ARCHIVE, asks to initialize memory bank, set up memory bank, continue a workspace memory system, says the equivalent in another language such as "инициализируй мемори банк", wants Cursor-memory-bank-like automation, or wants Codex to quietly manage tasks, decisions, progress, and project context for coding or non-coding projects.
---

# Memory Bank Autopilot

## Core Intent

Use this skill to make Memory Bank feel like quiet infrastructure. The user should be able to write naturally while Codex reads, updates, and maintains project memory with minimal ceremony.

Prefer action from context over asking the user to fill templates. Ask at most 1-2 questions only when a reasonable assumption would be risky.

Keep the workflow usable without optional client features. Treat the workspace Memory Bank as project-owned, reviewable state rather than a replacement for Codex memories or live task controls.

## Startup

When this skill triggers in a workspace:

1. Look for `AGENTS.md`, `INIT_THIS_MEMORY_BANK.md`, and `memory-bank/system.md` in the current workspace.
2. If `memory-bank/system.md` exists, treat the workspace as an existing Memory Bank. Read `AGENTS.md` when present, then `memory-bank/system.md`, then `memory-bank/activeContext.md` when present.
3. Follow project-local Memory Bank instructions and workflows before generic rules in this skill, unless they conflict with higher-priority instructions.
4. Read `memory-bank/tasks.md`, `memory-bank/progress.md`, and `memory-bank/decisions.md` only as needed.
5. Infer the workflow from the user's message and update only the memory files that need to change.

If the workspace has no Memory Bank and the user asks to initialize one, create the scaffold described in `references/scaffold.md`. Do not install or copy a skill as a side effect of initialization. If the workspace contains a bundled skill, leave it unchanged and mention explicit installation only when the user asks about installation.

## Backward Compatibility

Preserve existing Memory Bank projects:

- Treat a project with `memory-bank/system.md` as compatible even when it has no schema or version marker.
- Continue supporting the existing file roles and natural commands defined below.
- Do not rename, delete, relocate, reformat, or bulk-rewrite memory files unless the user explicitly asks to migrate them.
- Preserve unknown files, sections, metadata, and project-specific conventions.
- Never replace an existing `AGENTS.md`. Follow it and add Memory Bank guidance only during explicit initialization or migration, preserving all existing content.
- Never migrate a project merely because this skill changed. Apply a new scaffold only to a new Memory Bank.
- If a project-local rule differs from this skill, use the project-local rule and note the difference only when it affects the requested work.

## Workflow Detection

Map natural language to workflows:

- `VAN`, `START`, `INIT`, "initialize memory bank", "set up memory bank", "memory bank init", "инициализируй мемори банк", "new project", "begin", "continue this workspace": initialize or understand current work.
- `PLAN`, "plan", "roadmap", "steps": create or revise a practical plan.
- `THINK`, `CREATIVE`, "options", "compare", "which approach": explore choices and record decisions.
- `DO`, `BUILD`, "make", "update", "execute", "next step": perform the next useful action.
- `LOG`, "remember", "record", "save this", "decision": store a note, fact, or decision.
- `STATUS`, `CHECK`, "what now", "where are we": summarize current state and next action.
- `REFLECT`, "what did we learn": capture lessons after meaningful work.
- `ARCHIVE`, "close", "done", "finish this phase": close and archive completed work.

## Memory Files

Use these roles consistently:

- `memory-bank/activeContext.md`: current focus, assumptions, next action.
- `memory-bank/tasks.md`: active tasks and task state.
- `memory-bank/inbox.md`: raw incoming notes and unsorted ideas.
- `memory-bank/decisions.md`: durable decisions with short rationale.
- `memory-bank/progress.md`: completed work and meaningful changes.
- `memory-bank/research.md`: findings, links, open questions.
- `memory-bank/projects/`: project-specific memory for larger efforts.
- `memory-bank/archive/`: completed phases or projects.
- `memory-bank/reflection/`: retrospectives and lessons.
- `memory-bank/workflows/`: local workflow definitions. Prefer these over generic assumptions when present.

## Client Integration

Keep each state layer distinct:

- Treat workspace Memory Bank files as the durable source for project decisions, handoffs, progress history, and project-specific context.
- Treat Codex memories as an optional recall and personalization layer. Do not depend on them for required project rules, and do not read or edit generated Codex memory files directly.
- When Goal mode or an equivalent live task control is active, treat it as the live execution state. Record only durable checkpoints in Memory Bank instead of mirroring transient goal progress.
- When no live task control is active, continue using `activeContext.md` and `tasks.md` as before.
- Do not require Goal mode or Codex memories; the Memory Bank workflow must remain portable across clients.

## Update Rules

Update memory when:

- a project or task starts;
- active focus changes;
- the user makes or asks to record a decision;
- meaningful progress is completed;
- a plan changes;
- work is paused, resumed, reflected, or archived.

Do not log every conversational turn. Keep entries compact and future-useful.

Before writing, re-read each target file if other chats or agents may be working in the same workspace. Preserve concurrent changes and merge narrowly. If the intended merge is ambiguous, stop rather than overwrite.

## Initialization Behavior

When initializing a new Memory Bank:

1. Inspect existing `AGENTS.md`, `INIT_THIS_MEMORY_BANK.md`, and `memory-bank/` content before writing.
2. Create missing scaffold files without replacing existing files or sections.
3. If `AGENTS.md` exists, append a concise Memory Bank section only when equivalent guidance is absent. Preserve all existing instructions.
4. Create `INIT_THIS_MEMORY_BANK.md` only as a portable fallback note; do not imply that Codex loads it automatically.
5. Seed `activeContext.md` with the current goal and `tasks.md` with immediate project tasks when those files are new or the user asks to update them.
6. Record the setup decision in `decisions.md` and add a short progress entry.
7. Do not copy, install, upgrade, or remove skills during project initialization.

Read `references/scaffold.md` for the exact recommended file list and starter contents.

## Response Style

Be brief and operational. Tell the user what changed and what is next. Avoid exposing internal bookkeeping unless it helps the user trust the state.
