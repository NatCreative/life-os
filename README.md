# Life OS

A whole-life operating system run by Claude (Cowork) with GitHub as the source of truth.

**Win the Morning, Win the Day. Healthy Mind, Healthy Body, Healthy Business.**

## Structure

- `config.json` — workspaces, working hours, protected morning block, principles
- `tasks.json` — every task across all workspaces (single source of truth)
- `context/people.md` — who's who, who owns what
- `context/projects.md` — active projects, dependencies, things to watch
- `context/checkins.md` — standing nudges Claude surfaces proactively
- `context/health.md` — health rules and targets (paired with Roots)

## Task schema

```json
{
  "id": "t1", "title": "...", "workspace": "desktop-ops",
  "project": "...", "status": "todo|in_progress|waiting|done",
  "priority": "P1|P2|P3", "estimate_mins": 30,
  "due": "YYYY-MM-DD|null", "scheduled": "YYYY-MM-DD|null",
  "waiting_on": "name|null", "notes": "...", "created": "YYYY-MM-DD"
}
```

## The three surfaces

1. **Dashboard artifact** (Cowork) — live board + auto-planned Today view, reads/writes this repo
2. **Life OS skill** — teaches Claude the system: estimates, scheduling, proactive check-ins
3. **Morning briefing** — scheduled daily plan built from this repo

## Instance this for someone else

1. Fork (or copy) this repo, make it private
2. Edit `config.json` (workspaces, hours) and clear out `context/` + `tasks.json`
3. In their Cowork: connect the GitHub connector, install the `life-os.skill`, and ask Claude to "set up my Life OS dashboard and morning briefing pointing at <their-repo>"
