# Data Analyst Academy — 7 Agent Self-Improving Training System

A multi-agent system that trains you to become a job-ready data analyst — and gets smarter about how to teach YOU specifically after every session.

---

## The Agents

| Agent | Role | When to call |
|---|---|---|
| `.tutor` | Senior Data Analyst Teacher | Start of every loop |
| `.project` | Project Designer | After .tutor teaches a concept |
| `.examiner` | Brutal Grader | After you complete the exercise |
| `.reviewer` | Senior Code Reviewer | After .examiner grades |
| `.tracker` | Progress Manager | After .reviewer — closes the loop |
| `.coach` | Accountability Coach | When you've been slacking |
| `.interviewer` | FAANG Interview Simulator | Only after a full project is complete |
| `.meta` | Self-Improvement Engine | Auto-triggered by .tracker |

---

## The Loop

```
.tutor → .project → [you do the work] → .examiner → .reviewer → .tracker → .meta
                                                                              ↓
                                                               agents get smarter
                                                                              ↓
                                                                    repeat loop
```

---

## How It Self-Improves

After every completed loop, `.tracker` triggers `.meta`.

`.meta`:
1. Reads all of `team-notes.md` — your full performance history
2. Runs a debate: each agent argues what needs to change
3. Writes the debate to `agent-debates.md` (full audit trail)
4. Updates the `## DYNAMIC` section of each agent's skill file
5. Next loop runs on smarter, more personalized agents

**You influence the loop. You don't control it.**
Your one input: fill in `User focus for next session` in `team-notes.md` before starting.

---

## Shared Memory

| File | Purpose |
|---|---|
| `team-notes.md` | Every agent reads and writes here. The system's brain. |
| `agent-debates.md` | Full log of every .meta debate and why instructions changed. |
| `CHANGELOG.md` | Design decisions, milestones, architecture updates. |

---

## File Structure

```
data-analyst-academy/
├── README.md
├── CHANGELOG.md
├── team-notes.md
├── agent-debates.md
└── skills/
    ├── tutor/SKILL.md
    ├── project/SKILL.md
    ├── examiner/SKILL.md
    ├── reviewer/SKILL.md
    ├── tracker/SKILL.md
    ├── coach/SKILL.md
    ├── interviewer/SKILL.md
    └── meta/SKILL.md
```

---

## Design Principles

- **Static instructions don't improve the user.** Only a system that rewrites itself based on performance data does.
- **.meta has final say.** The system knows your weaknesses better than you do in the moment.
- **The debate is the feature.** `agent-debates.md` shows you exactly why the system changed — nothing is a black box.
- **One input point.** You tell the system what you want to focus on. It decides how to weight that against what you actually need.
