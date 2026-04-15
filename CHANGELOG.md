# CHANGELOG — Data Analyst Academy

Every meaningful change to this system is logged here.
Includes: design decisions, agent instruction updates, architecture changes, and session milestones.

---

## [2026-04-15] — v1.2 — Academy Manager + Full Documentation

### Added
- `academy-manager.skill` — system admin skill with full command suite:
  - `status` — system health check + current progress
  - `debates` — full agent debate audit trail
  - `inspect [agent]` — view any agent's current DYNAMIC section
  - `force-meta` — manually trigger .meta
  - `history` — full session history
  - `reset` — wipe to baseline (confirm required)
  - `backup` — commit + push to GitHub
  - `health` — verify all files are present

### Updated
- `README.md` — complete rewrite with full system explanation:
  - Three-layer architecture documented
  - Two-section (PERMANENT/DYNAMIC) architecture explained
  - Full loop walkthrough
  - Design principles

---

## [2026-04-15] — v1.1 — Master Orchestrator Skill

### Added
- `data-analyst-academy.skill` — master hub that routes to all 7 agents
  - Reads `team-notes.md` on every invocation
  - Routes `.tutor`, `.project`, `.examiner`, `.reviewer`, `.tracker`, `.coach`, `.interviewer`, `.meta` commands
  - Shows system status when invoked without a command
  - `status` command for quick progress check

---

## [2026-04-15] — v1.0 — Initial Build

### System designed and built in collaboration with Claude Code

**Architecture decisions made in design conversation:**

1. **7 agents + 1 meta-agent** — each with a single focused job
2. **Shared memory via `team-notes.md`** — every agent reads and writes to the same file
3. **PERMANENT + DYNAMIC section architecture** — core identity never changes, personalization always grows
4. **.meta has final say** — user cannot override agent updates; prevents defensive self-sabotage
5. **One user input point** — `User focus for next session` in `team-notes.md`; user influences the loop but doesn't control it
6. **agent-debates.md audit trail** — full transparency into why agents changed, not just what changed
7. **.tracker always triggers .meta** — the improvement loop is automatic, not manual
8. **.interviewer gates on project completion** — keeps interviews meaningful and high-stakes
9. **GitHub as persistent backup** — system state can be restored from repo at any time

**Key insight that drove the architecture:**
> "Static instructions don't improve the user. Only a system that rewrites its own instructions based on performance data does."

**Files created:**
- `skills/tutor/SKILL.md`
- `skills/project/SKILL.md`
- `skills/examiner/SKILL.md`
- `skills/reviewer/SKILL.md`
- `skills/tracker/SKILL.md`
- `skills/coach/SKILL.md`
- `skills/interviewer/SKILL.md`
- `skills/meta/SKILL.md`
- `team-notes.md`
- `agent-debates.md`

---

<!-- New entries go above this line -->
