# Agent Skills

Small, install-once skills that keep Claude Code sharp where it matters — planning, review, staying in budget, and reading the docs before it guesses.

A skill is a small instruction file you drop into Claude Code. It teaches your agent one good habit. You install the ones you want and leave the rest.

Curated for **The Agentic AI Cohort** by Andreas Horn.

---

## Install a skill

Each skill is a folder with a `SKILL.md` inside. To install one:

1. Download the skill's folder from this repo.
2. Drop it into your `.claude/skills/` folder.
3. Start a new Claude Code session — the skill's `/command` is now available.

New here? Start with `/visual-plan` and `/quick-recap`. They pay off on day one. Add more once you see how they change your sessions.

---

## The skills

### Plan and review the work

| Skill | What it does | Use when |
|---|---|---|
| `/visual-plan` | Turns a text plan into a visual one — diagrams, file maps, annotated code, open questions. | You want to approve the approach before the agent touches a file. |
| `/visual-recap` | Turns a branch, commit, or PR into a visual recap — annotated diffs, diagrams, review notes. | You need to review finished work without drowning in raw code. |
| `/plan-arbiter` | Compares competing plans and returns a decision memo: the winner, the rejects, the checks to run. | You have more than one strategy on the table. |
| `/agent-watchdog` | Audits another agent's work from a transcript, PR, or branch; reports gaps and can fix them. | One agent hands off to another and you want a second set of eyes. |

### Keep the agent disciplined

| Skill | What it does | Use when |
|---|---|---|
| `/plow-ahead` | Converts routine questions into sensible assumptions, then recaps every decision it made. | You want autonomy: get it done, then tell me what you decided. |
| `/quick-recap` | Adds a one-line status to every response — green (done), yellow (do one thing), red (blocked). | You want every reply to end with a clear signal. |
| `/read-the-damn-docs` | Forces a web search of the real, current docs before acting on installs, APIs, limits, deploys. | Anything touches an external tool that changes often. |
| `/stay-within-limits` | Checks usage before big work and pauses near the limit, leaving a clean plan to resume. | You run long or parallel sessions and don't want to hit a wall mid-task. |

### Spend the expensive model wisely

| Skill | What it does | Use when |
|---|---|---|
| `/efficient-fable` | Keeps the top model as orchestrator and final judge; lighter agents do the token-heavy lifting. | You're on a premium model and want its attention on decisions. |
| `/efficient-frontier` | The same orchestration pattern applied to any high-cost frontier model. | The work can be split and you don't want your priciest model doing every scan. |

---

## A word of caution

Skills are instructions you're handing your agent — read what each one does before you install it. Start with two, see how they change your sessions, then add more. You don't need all ten.

---

*Part of the Agentic AI Cohort resource vault · Andreas Horn · Human in the Loop*
