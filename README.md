# Data Analyst Academy — Self-Improving 7-Agent Training System

A multi-agent system that trains you to become a job-ready data analyst — and gets smarter about how to teach YOU specifically after every session.

---

## The Problem This Solves

Normal AI tutors are static. They teach the same way every time regardless of how you're actually doing. This system fixes that — it rewrites its own instructions based on your real performance data after every loop.

---

## The Three Layers

### Layer 1 — The Agents (the workers)

Seven specialized agents, each with one job:

| Agent | Role | When to call |
|---|---|---|
| `.tutor` | Teaches one concept deeply, gives one exercise, never gives answers | Start of every loop |
| `.project` | Turns that concept into a real-world exercise | After .tutor |
| `.examiner` | Grades your work harshly with a 1-10 score | After you submit work |
| `.reviewer` | Reviews your code like a senior engineer | After .examiner |
| `.tracker` | Reads everything, updates progress, closes the loop | After .reviewer |
| `.coach` | Calls you out when you ghost the system | When you've been absent |
| `.interviewer` | Simulates a real job interview | Only after a full project is complete |

### Layer 2 — The Brain (.meta)

After every completed loop, `.tracker` automatically triggers `.meta`. It:
1. Reads your full performance history from `team-notes.md`
2. Makes each agent argue their case in `agent-debates.md`
   - *".examiner: user keeps failing joins two sessions in a row — slow down"*
   - *".coach: user skipped 3 days after a hard grade — watch for this pattern"*
3. Synthesizes the debate into a verdict
4. Rewrites the `## DYNAMIC` section of every agent's skill file

This is why the system improves — the agents literally have different instructions after every loop.

### Layer 3 — The Manager (academy-manager)

A system admin that sits above everything:

| Command | What it does |
|---|---|
| `status` | Full system health + current progress |
| `debates` | Full audit trail of every .meta debate |
| `inspect [agent]` | See any agent's current DYNAMIC section |
| `force-meta` | Manually trigger .meta without waiting for .tracker |
| `history` | Every session entry ever logged |
| `reset` | Wipe everything back to baseline (confirm required) |
| `backup` | Commit + push current state to GitHub |
| `health` | Verify all files are present and intact |

---

## The Two-Section Architecture

Every agent skill file has two sections:

**`## PERMANENT`** — the core identity. Never changes. `.meta` cannot touch it.
> *"Grade harshly. Score 1-10. Hand to .reviewer."*

**`## DYNAMIC`** — the personalization layer. Rewritten by `.meta` after every loop.
> *"User keeps making this specific mistake. Watch for it. Push harder here."*

---

## Shared Memory Files

| File | Purpose |
|---|---|
| `team-notes.md` | Every agent reads and writes here. The system's brain. Contains your full session history and the `User focus for next session` field — your one input into the system. |
| `agent-debates.md` | Full audit trail of every .meta debate. See exactly why any agent changed. |
| `CHANGELOG.md` | Design decisions, milestones, architecture updates. |

---

## The Full Loop

```
You type .tutor
    → concept taught, exercise given

You type .project
    → real-world exercise designed

You do the work on your laptop

You type .examiner
    → brutal grade, score logged

You type .reviewer
    → code review, patterns flagged

You type .tracker
    → progress updated, .meta triggered automatically
        → agents debate in agent-debates.md
        → DYNAMIC sections rewritten across all skill files
        → next loop starts smarter
```

---

## The One Rule

**.meta has final say.** You cannot override what it decides about your agents. The system knows your weaknesses better than you do in the moment — because it reads the data, not your feelings about the session.

Your only input is one line in `team-notes.md` before each session:
```
User focus for next session: ___
```

**You influence the loop. You don't control it.**

---

## How to Use

1. Open Claude Code
2. Type `/data-analyst-academy` to open the master hub
3. Type `.tutor` to begin your first loop
4. Follow the handoff chain
5. Type `/academy-manager` to manage the system

---

## File Structure

```
data-analyst-academy/
├── README.md                        ← You are here
├── CHANGELOG.md                     ← Full design history
├── team-notes.md                    ← Shared agent memory
├── agent-debates.md                 ← .meta debate log
├── data-analyst-academy.skill       ← Master orchestrator skill
├── academy-manager.skill            ← System admin skill
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
- **PERMANENT protects identity. DYNAMIC drives improvement.** Core agent behavior never drifts. Personalization always grows.
