# Handoff: giving `life-ops-brain` to a friend

This skill sets up a **multi-area life ops brain** (ministry/nonprofit, business,
personal, family) with guided context interview and connection walkthroughs for
Gmail, Zeffy, and QuickBooks Online. This note is for **you** (the person handing
it out), not the end user.

## What they get

A local folder with:

- `CLAUDE.md` harness (hard walls between life areas, draft-only sends)
- Context files for each area they enable
- `ministry/donors`, money notes, processes (thank-yous, intake, triage, weekly recon)
- `connections/` checklists for Gmail / Zeffy / QBO
- `SETUP-STATUS.md` so they can pause and resume
- `START-HERE.md` in plain English

## The one hard requirement

Claude must be able to **write files** on their computer.

| Surface | Fit |
|---------|-----|
| Claude desktop + Cowork with a folder open | Best for non-technical people |
| Claude Code | Best if they're technical |
| Plain claude.ai chat, no files | Interview only — they'd have to paste files by hand |

## How to hand it over

1. **Zip the skill folder**  
   Zip `.claude/skills/life-ops-brain/` (this whole folder: `SKILL.md`, `templates/`, `references/`, `HANDOFF.md`).

2. **They install it once**  
   Claude desktop: Settings → Skills (or Capabilities) → add/upload the skill.  
   Or you pre-install it for them.

3. **They open a folder in Cowork** (empty parent folder is fine) and say:  
   **"Set up my life ops brain"** or **"Set up my ministry brain."**

4. Answer questions (~15–25 minutes for structure + context). Connections can be another session.

### Quickstart to paste into a handoff message

> 1. Install the skill (open the zip in Claude → Settings → Skills).  
> 2. Open Claude, start Cowork, pick a folder on your computer.  
> 3. Type: **Set up my life ops brain.**  
> 4. Answer the questions. When it asks about Gmail/Zeffy/QuickBooks, you can do those now or later.  
> 5. If you use Cowork Projects, paste the Project Instructions line it gives you so it always reads CLAUDE.md first.

## Cowork Project line (they must paste this themselves)

> Always read CLAUDE.md in this folder first and follow everything in it. It is the source of truth for this life ops brain. Never send email or donor messages without explicit approval; draft only.

## Design choices baked in

- **Not Agency Brain.** Single person, no Owner/Scout/Team. If a church staff later needs shared ops, split ministry into its own shared brain later — don't merge family into a team repo.
- **QBO = books of record.** Zeffy native QBO sync preferred. Brain tracks people and drafts, not a second ledger.
- **Draft only** for external messages.
- **Hard walls** between ministry / business / personal / family.
- **Secrets never in the folder.**

## Optional: you operate it for them (Plyntr)

If this is a paid build rather than a friend favor:

1. Run the skill with them (or for them on a machine they own).
2. Finish Gmail + Zeffy→QBO in a live session.
3. First week: daily triage + thank-you drafts only.
4. Later: custom Zeffy connector skill if exports get old.

That maps cleanly to an AI Opportunity Map → setup → light retainer, without selling "autonomous donor email."

## Maintaining this skill

- Keep it portable: no Plyntr paths, no required shell, no Doppler.
- Edit `templates/` to change every new brain's shape.
- Edit `references/connection-guides.md` when Zeffy/QBO UI labels change.
- Keep generated `CLAUDE.md` short; detail stays in `context/`.
