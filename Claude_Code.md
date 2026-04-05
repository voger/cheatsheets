# Claude Code — Solo User Cheatsheet

## The Right Mental Model

Claude Code is not a chatbot. It is a capable colleague sitting at your terminal who can read files, write code, and run commands. It wakes up with **amnesia every session** — it only knows what you tell it or what it can read from your project.

Your job: give it context, give it goals, review what it does. Not micromanage every step.

---

## The Golden Rules

1. **Plan before code** — for anything non-trivial, always get a plan first. Read it. Correct it. Then say go ahead.
2. **Give goals, not steps** — describe *what* and *why*, let Claude figure out *how*.
3. **Teach from mistakes** — when Claude gets something wrong, don't just fix it. Tell it *why* it was wrong and update CLAUDE.md so it never repeats.
4. **Keep context clean** — start fresh sessions for new tasks. Don't cram 5 different things into one long session.
5. **Never trust blindly** — always review what it produces. You are the supervisor, it is the worker.
6. **Don't babysit** — describe the outcome you want and let Claude figure out the path.

---

## CLAUDE.md — The Most Important File

A markdown file in your **project root** that Claude reads automatically at the start of every session. Your fix for the amnesia problem.

**What to put in it:**
- What the project is (2–3 sentences)
- Tech stack
- How you like code written (style rules, conventions)
- What is NOT allowed (e.g. no inline styles, no CDNs)
- Current status (what's done, what's next)

**What NOT to put in it:**
- Detailed style rules that belong in Skills
- Everything — keep it slim (~100 lines max)

**Example:**
```markdown
# Project: RSS Reader

## What this is
A personal CLI + web RSS reader. Fetches feeds from feeds.txt,
displays articles via a Flask web interface.

## Tech stack
- Python 3, Flask, feedparser
- Pico CSS served locally from static/

## Rules
- No inline styles or <style> blocks in HTML
- No CDNs — all assets must be in static/
- Small, readable functions
- Always handle exceptions — never let one bad feed crash everything

## Current status
Web interface done. Next: keyword filtering feature.
```

**Keep it updated.** At the end of sessions where decisions were made, tell Claude:
> *"Update CLAUDE.md to reflect what we built and any decisions we made."*

---

## Editing Modes (VS Code Panel)

| Mode | What it does | When to use |
|---|---|---|
| **Ask before edits** | Asks approval before every change | Sensitive files, delicate work |
| **Edit automatically** | Makes changes directly | Most of the time |
| **Plan mode** | Writes a plan, touches nothing | Before any non-trivial task |

**Workflow:** Plan mode → review → switch to Edit automatically → "go ahead."

---

## Slash Commands

Reusable prompt shortcuts. Type `/commandname` instead of writing the same instructions every session.

**Where they live:**
- `.claude/commands/` — project-level (only in this project)
- `~/.claude/commands/` — global (available in every project)

**How to create one:** just ask Claude:
> *"Create a slash command called `start` that reads CLAUDE.md and gives me a 5-line project summary plus 3 suggested next steps."*

Claude creates `.claude/commands/start.md` — a plain markdown file with the prompt inside.

**Restart the session** after creating commands — they only load at startup.

**Useful commands to build over time:**
- `/start` — session kickoff summary
- `/plan` — force plan mode for current task
- `/review` — review all changes made this session
- `/commit` — write a good git commit message for current changes

---

## Hooks

Scripts that fire automatically when Claude does something. You don't trigger them — they just run.

**Where they live:** `.claude/settings.json` in your project root (project-level) or `~/.claude/settings.json` (global).

**Triggers:**
- `PreToolUse` — before Claude uses a tool
- `PostToolUse` — after Claude uses a tool (most useful)
- `Stop` — when Claude finishes a task

**Most useful hook for beginners:** syntax check after every Python file edit:
```json
{
  "hooks": {
    "PostToolUse": [
      {
        "matcher": ".*\\.py$",
        "hooks": [
          {
            "type": "command",
            "command": "python -m py_compile $CLAUDE_FILE_PATHS"
          }
        ]
      }
    ]
  }
}
```

Ask Claude to create hooks for you — describe what you want in plain English.

---

## Skills

Context-aware reference files that load automatically when relevant. Like CLAUDE.md, but smarter — they only appear when Claude is working on the right file type.

**Where they live:** `.claude/skills/` in your project root.

**Why use them instead of CLAUDE.md:**
- CLAUDE.md loads every session, for everything
- Skills load only when relevant → cleaner context window
- Keeps CLAUDE.md slim

**Example split:**
- `python-style.md` — loads when editing `.py` files
- `frontend-style.md` — loads when editing `.html` / `.css` files

**Create them by asking Claude:**
> *"Create a skill called python-style that captures all our Python conventions. Configure it to load automatically when editing .py files."*

**After creating skills:** remove the overlapping content from CLAUDE.md. One source of truth per topic.

---

## The Hidden Memory Folder

Claude Code quietly creates its own memory files at:
```
~/.claude/projects/-home-yourname-yourproject/memory/
```

These are **outside your project folder** and accumulate silently. Claude writes to them automatically based on what it observes.

**Check it periodically:**
```bash
ls ~/.claude/projects/*/memory/
```

**What to do with files you find there:**
- If the content is good and not already in your skills → copy it into the right skill, delete the memory file
- If it duplicates your skills → delete it
- If it's wrong → delete it

**Goal:** one source of truth. Your skill files, not hidden folders.

---

## Chrome Integration

Lets Claude open Chrome, see what's rendered on screen, click things, and report back. Useful for UI work.

**Supported browsers:** Google Chrome and Microsoft Edge only (officially). Brave/Chromium: community workaround available but not official. Firefox: not supported.

**How to enable:** in the terminal Claude session, type:
```
/chrome
```

Select "Enable by default" or "Reconnect extension."

**The workflow:**
1. Start your local server (`python app.py`)
2. Run Claude in terminal (`claude`)
3. Type `/chrome` to connect
4. Ask: *"Open localhost:5000 in Chrome, tell me what you see, suggest improvements"*
5. Act as art director: *"Do suggestions 1 and 3, skip 2, also make the font larger"*

**Note:** Chrome integration works best from the terminal session, not the VS Code panel.

---

## VS Code Panel vs Terminal — When to Use Each

| Task | VS Code Panel | Terminal `claude` |
|---|---|---|
| Editing code while looking at it | ✅ | |
| Quick file changes | ✅ | |
| Chrome integration | | ✅ |
| Running commands, tests | | ✅ |
| Long agentic tasks | | ✅ |
| Hooks and complex workflows | | ✅ |

Both operate on the same files. They don't share context between them — if you switch, give brief context.

---

## Project File Structure

A well-organised Claude Code project looks like this:

```
your-project/
├── CLAUDE.md                  ← project memory (you write this)
├── .claude/
│   ├── commands/
│   │   └── start.md           ← slash commands
│   ├── skills/
│   │   ├── python-style.md    ← loads on .py files
│   │   └── frontend-style.md  ← loads on .html/.css files
│   └── settings.json          ← hooks and permissions
├── your actual code...
```

**Commit everything in `.claude/` to git.** Commands, skills, and hooks should be version-controlled — they're part of your project's workflow, not throwaway config.

The memory folder (`~/.claude/projects/...`) is outside the project and never touched by git. That's fine — manage it manually as described above.

---

## Context Window — The Hidden Constraint

Claude has a limited "working memory" per session. When it fills up, Claude starts losing track of earlier decisions.

**Signs your context is getting bloated:**
- Claude forgets things you told it earlier in the session
- It starts making decisions that contradict earlier ones
- Responses get slower and less precise

**How to manage it:**
- Keep CLAUDE.md slim — use Skills for detail
- Start fresh sessions for new tasks, don't chain everything in one session
- For long tasks, split into phases: Research → Plan → Implement → Validate, with `/clear` between phases if needed
- Never exceed ~60% of the context window on any single task

---

## Useful Habits

**At the start of every session:**
- Run `/start` (once you have that command set up)
- Or just say: *"Read CLAUDE.md and tell me where we are"*

**Before any non-trivial task:**
- Use Plan mode, or say: *"Before writing anything, give me a plan"*

**When Claude makes a mistake:**
- Don't just fix it — say *"That's wrong because [reason]. Add a rule to CLAUDE.md / the relevant skill so you don't repeat this"*

**At the end of productive sessions:**
- *"Update CLAUDE.md with any decisions we made and update the current status"*
- Commit everything including `.claude/`

**Periodically:**
- Check `~/.claude/projects/*/memory/` for accumulated files
- Review your skills — keep them accurate as the project evolves

---

## What NOT to Do

- Don't micromanage steps — give goals, not instructions
- Don't let Claude jump into code without a plan on complex tasks
- Don't dump everything into CLAUDE.md — it bloats context
- Don't ignore what Claude builds — always review
- Don't let the hidden memory folder accumulate unchecked
- Don't keep making the same correction — make it a rule in CLAUDE.md or a skill
- Don't run one giant session for a whole day — fresh sessions for fresh tasks

---

## Quick Reference — Key Locations

| Thing | Location |
|---|---|
| Project memory | `./CLAUDE.md` |
| Project commands | `./.claude/commands/` |
| Project skills | `./.claude/skills/` |
| Project hooks/settings | `./.claude/settings.json` |
| Global commands | `~/.claude/commands/` |
| Global hooks/settings | `~/.claude/settings.json` |
| Claude's own memory | `~/.claude/projects/[project]/memory/` |
