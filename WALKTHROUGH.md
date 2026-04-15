# How Danny Uses the System — Full Walkthrough

---

## First Time Setup

Danny opens Claude Code and types `/data-analyst-academy`

The hub opens and shows:
```
Overall Progress: 0%
Sessions completed: 0
No history yet.

Type .tutor to begin.
```

---

## Loop 1

**Danny types `.tutor`**

.tutor reads `team-notes.md` — nothing there yet, starts from baseline DYNAMIC instructions.

> "Before we touch any data, you need to understand what a DataFrame is. Think of it like a spreadsheet in memory — rows are observations, columns are variables. Here's your exercise: load this CSV, print the first 5 rows, and tell me how many rows and columns it has."

Danny does it on his laptop. Comes back.

---

**Danny types `.project`**

.project reads what .tutor just logged. Gives a real exercise:

> "You're a junior analyst at a retail company. Your manager just handed you a CSV of 10,000 sales transactions. Load it, inspect it, and answer: what's the date range of the data and which product category has the most transactions?"

Danny works on it. Submits his code.

---

**Danny types `.examiner`**

.examiner reads the exercise requirements and Danny's code. Tears it apart:

> "6/10. You answered both questions but you used a for loop to count categories instead of `.value_counts()`. You also hardcoded the filename instead of using a variable. Both are real mistakes in a production environment."

---

**Danny types `.reviewer`**

.reviewer goes deeper:

> "The for loop isn't just inefficient — it signals you don't know pandas idioms yet. Any senior analyst seeing that in a PR would flag it immediately. Also: no comments, magic numbers, and your variable is called `x`. Fix these three things before the next session."

---

**Danny types `.tracker`**

.tracker reads everything, updates `team-notes.md`:

```
Overall Progress: 8%
Sessions completed: 1
Strongest area: DataFrame basics
Weakest area: Pandas idioms
Last active: today
```

Then: *"Triggering .meta to update agent instructions."*

---

**.meta runs automatically**

Reads all session data. Opens the debate in `agent-debates.md`:

```
.tutor says: User understood DataFrames conceptually but doesn't
know pandas idioms. Next concept should be Series methods —
.value_counts(), .groupby(), .agg() — before moving on.

.examiner says: For loop instead of .value_counts() is a red flag.
Watch for this pattern — it means he's thinking in Python, not pandas.

.reviewer says: Code hygiene is bad. Variable names, no comments,
hardcoded values. This needs to be flagged every session until fixed.

.coach says: First session, showed up. No pattern yet. Standard pressure.

.meta VERDICT:
- .tutor: focus next concept on pandas idioms specifically
- .examiner: watch for Python-style loops as a recurring pattern
- .reviewer: add code hygiene as a standing critique item
- .coach: no adjustment needed yet
```

All DYNAMIC sections updated. Loop 1 done.

---

## Loop 2 — Danny comes back 4 days later

**Danny types `.tutor`**

.tutor's DYNAMIC now says *"user thinks in Python not pandas — teach idioms"*

> "Last time you used a for loop where pandas had a one-liner. Today we're fixing that. `.value_counts()`, `.groupby()`, `.agg()` — here's one exercise using all three."

Danny completes the loop again. .meta runs. Sees improvement on idioms, still flags code hygiene. Updates accordingly.

---

## Danny disappears for 9 days

**Danny types `.coach`**

> "You did nothing for 9 days. You got a 6/10, a code review that told you exactly what to fix, and then you vanished. That's not a busy schedule — that's avoidance. Your next session is pandas groupby. You have no excuse not to do it today."

---

## 3 Loops later — Project 1 Complete

.tracker marks Project 1 done in `team-notes.md`.

**Danny types `.interviewer`**

> "Walk me through your project. Start from the first decision you made."

Danny explains.

> "Why did you use `.groupby()` there instead of a pivot table?"

Danny answers.

> "You said the data was clean. How did you verify that? What would missing values have done to your `.agg()` result?"

Danny sweats.

At the end:

> "No Hire — yet. Your technical execution is solid but you can't explain your decisions under pressure. You knew the answer, you just couldn't defend it. That's what we fix in Project 2."

---

## Danny types `/academy-manager` → `debates`

Reads every debate .meta has run. Sees exactly how the agents evolved — why .tutor slowed down on idioms, why .examiner started flagging a specific pattern, why .coach escalated pressure after the 9-day gap.

Full transparency. Nothing hidden.

---

## 6 Months Later

Danny has completed 3 projects. Every agent knows his exact weak spots, his avoidance patterns, his code habits. The system on loop 18 looks nothing like loop 1 — completely different DYNAMIC instructions, tuned entirely to him.

He types `.interviewer` on Project 3.

> "Strong Hire."
