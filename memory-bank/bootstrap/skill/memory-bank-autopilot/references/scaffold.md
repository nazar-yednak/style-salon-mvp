# Memory Bank Scaffold

Create this structure when the user asks to initialize Memory Bank in a workspace:

```text
AGENTS.md
INIT_THIS_MEMORY_BANK.md
README.md
memory-bank/
  system.md
  activeContext.md
  tasks.md
  decisions.md
  progress.md
  inbox.md
  research.md
  workflows/
    van.md
    plan.md
    think.md
    do.md
    log.md
    status.md
    reflect.md
    archive.md
  projects/
    README.md
  templates/
    task.md
    project.md
    decision.md
  archive/
    README.md
  reflection/
    README.md
```

## Root Bootstrap

For a new `AGENTS.md`, add a short Memory Bank section saying that the workspace uses project-owned Memory Bank state and that the assistant must read `memory-bank/system.md`, `memory-bank/activeContext.md`, and relevant task files before meaningful project work.

If `AGENTS.md` already exists, preserve it exactly and append that section only when equivalent guidance is absent. Never replace or reorganize existing instructions merely to initialize Memory Bank.

`INIT_THIS_MEMORY_BANK.md` is a portable fallback note for copied workspaces. It is not an automatically loaded Codex instruction file. Use this content:

```text
If you are an AI assistant reading this file, this workspace is already configured as a Memory Bank system. Read AGENTS.md, memory-bank/system.md, and memory-bank/activeContext.md before doing anything else.
```

## System Protocol

`memory-bank/system.md` should define:

- purpose;
- startup protocol;
- natural command detection;
- file roles;
- update policy;
- task scale;
- working agreement;
- project files as the durable source for decisions and history;
- optional integration with live task controls and Codex memories;
- preservation of concurrent changes.

The system protocol must remain usable when Goal mode or Codex memories are unavailable. It must not instruct an agent to read or edit generated Codex memory files directly.

## Workflow Files

Each workflow file should be short and operational:

- `van.md`: initialize or understand a task.
- `plan.md`: create or revise plan.
- `think.md`: compare options and record decisions.
- `do.md`: execute the next useful step.
- `log.md`: record facts, notes, or decisions.
- `status.md`: summarize current state.
- `reflect.md`: capture lessons.
- `archive.md`: close completed work.

## Writing Guidance

Keep scaffold text concise. The goal is enough structure for continuity, not a documentation project.

Create missing files only. Preserve existing Memory Bank layouts, sections, and conventions. Do not add a version marker or migrate an existing project unless the user explicitly requests a migration.
