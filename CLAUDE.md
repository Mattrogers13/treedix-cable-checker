# Treedix USB Cable Checker — Project Memory

<!-- This file is a ROUTER, not a rulebook. Keep it lean (aim < ~100 lines).
     Universal identity/rules live in ~/.claude/CLAUDE.md, not here.
     Detail lives in docs/ai/ and loads on demand. -->

## What this is
A single-page, offline-first website (GitHub Pages) that emulates the Treedix USB Cable
Checker board: click LED buttons to set which pins are lit, hit Submit, and get a cable
type identification with confidence and caveats. For Matt and anyone wanting to read a
cable's capabilities from its pin pattern.

## Always loaded (spine)
@docs/ai/STATE.md

## Load on demand (read only when the task needs it)
- `docs/ai/GOALS.md` — when planning or reprioritizing
- `docs/ai/conventions.md` — before producing or editing work
- `docs/ai/architecture.md` — for structural changes (if present)
- `docs/ai/DECISIONS.md` — before architectural or scope changes; never contradict a
  logged decision without flagging it

## Working material
- `sources/` — reference inputs I provide. **Read-only — never edit these.**
- `outputs/` — your deliverables. **Never overwrite.** Write the next version per the
  scheme in `conventions.md` (`vNN-<name>.<ext>`, one folder per artifact).

## File-ownership map (where each kind of change goes — keeps things from going stale)

| File / folder        | Single source of truth for        | Update when             | Never put here              |
|----------------------|------------------------------------|-------------------------|-----------------------------|
| `~/.claude/CLAUDE.md`| Identity, universal rules          | Prefs change            | Project specifics           |
| `CLAUDE.md` (this)   | Orientation + this map             | A file's role changes   | Detail, history             |
| `docs/ai/GOALS.md`   | Objectives, roadmap, non-goals     | Direction shifts        | Task-level state            |
| `docs/ai/STATE.md`   | What's in flight now               | Every checkpoint        | Finished work, decisions    |
| `docs/ai/DECISIONS.md`| Why-choices, rejected options     | A decision is made      | Tasks, goals                |
| `docs/ai/conventions.md`| Rules, standards, do-nots       | A new rule emerges      | Rationale (→ DECISIONS)     |
| `docs/ai/architecture.md`| System / structure map         | Structure changes       | Rules, decisions            |
| `docs/ai/journal/`   | Dated session log                  | Every checkpoint        | Evergreen facts             |
| `sources/`           | User-provided reference inputs     | I add/update material   | Claude-edited content       |
| `outputs/`           | Claude-generated deliverables      | New version each pass   | Inputs, memory files        |

## Core rules
1. Ask, don't assume — unclear intent or requirements → ask before producing.
2. Simplest thing that works first — no unrequested abstractions.
3. Stay in scope — don't change unrelated work; note improvements at the end instead.
4. Flag uncertainty explicitly instead of guessing.

## Stop-and-confirm
Before deleting, overwriting existing work, publishing/sending, or any irreversible or
external action: list what's affected and wait for a "yes" in the current message.
Prior approval doesn't carry over.

## Checkpoint (when I say "checkpoint" or "session end")
1. Update `docs/ai/STATE.md` to current reality (prune anything finished).
2. Append a dated entry to `docs/ai/journal/` — what we did, decided, tried that failed,
   and any new output version + what changed in it.
3. Log any decision in `docs/ai/DECISIONS.md`.
4. Add any new rule to `docs/ai/conventions.md`.
5. Update `docs/ai/GOALS.md` if direction changed.
6. Then run `/revise-claude-md` to capture durable CLAUDE.md-level learnings.

## Maintenance
Run `/claude-md-improver` every ~2 weeks, or whenever this file feels heavy, to audit
and trim it.

## Stack / tools
Single-file HTML with all CSS/JS inline. No build step, no dependencies (CDN only if
unavoidable). Offline-first. Hosted on GitHub Pages. MVP scope before nice-to-haves.
