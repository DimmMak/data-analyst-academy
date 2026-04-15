# CHANGELOG — Data Analyst Academy

Every meaningful change to this system is logged here.
Includes: design decisions, agent instruction updates, architecture changes, and session milestones.

---

## [2026-04-15] — v1.0 — Initial Build

### System designed and built in collaboration with Claude Code

**Architecture decisions made:**
- 7 agents: .tutor, .project, .examiner, .reviewer, .tracker, .coach, .interviewer
- 1 meta-agent: .meta — the self-improvement engine
- Shared memory via `team-notes.md`
- Debate log via `agent-debates.md`
- Each agent has PERMANENT (never changes) + DYNAMIC (updated by .meta) sections

**Key design principles agreed on:**
- .meta has final say on all agent updates — user cannot override
- User has one input point: "User focus for next session" in team-notes.md
- The system improves itself — each loop produces smarter agents
- agent-debates.md gives full transparency into WHY instructions changed
- .tracker always triggers .meta at end of every loop
- .interviewer only activates after a full project is complete

**Files created:**
- skills/tutor/SKILL.md
- skills/project/SKILL.md
- skills/examiner/SKILL.md
- skills/reviewer/SKILL.md
- skills/tracker/SKILL.md
- skills/coach/SKILL.md
- skills/interviewer/SKILL.md
- skills/meta/SKILL.md
- team-notes.md
- agent-debates.md

**Origin conversation summary:**
Started from a user-designed multi-agent training system concept. Evolved through design discussion into a self-improving feedback loop architecture. Core insight: static agent instructions don't improve the user — only a system that rewrites its own instructions based on performance data does.

---

<!-- New entries go above this line -->
