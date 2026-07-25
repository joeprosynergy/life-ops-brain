# Life Ops Brain

A setup skill for Claude or Codex that builds a personal multi-area ops brain:

- Ministry / nonprofit, business, personal, and family (with hard walls)
- Guided interview into context files
- Connection walkthroughs for Gmail (up to 3 accounts), Zeffy, and QuickBooks Online
- Draft-only donor and email replies by default

Nothing in this package is private to any one person. It is a blank setup kit.

## Quick start — Claude (easiest)

1. Download this repo as a ZIP (green **Code → Download ZIP**), or use the link someone sent you.
2. Unzip it. You want a folder named `life-ops-brain` that contains `SKILL.md`.
3. In the **Claude** desktop app: **Settings → Skills** (or Capabilities) → add / upload that `life-ops-brain` folder.
4. Start **Cowork**, open any empty folder on *your* computer.
5. Type: **Set up my life ops brain**
6. Answer the questions. Connections (Gmail / Zeffy / QBO) can be a second session.

If Claude asks for Project Instructions, paste the line it gives you so it always reads `CLAUDE.md` first.

## Quick start — Codex

```bash
# Install the skill (user-wide)
mkdir -p ~/.agents/skills
# If you downloaded the repo zip, the skill is inside as life-ops-brain/
cp -R /path/to/unzipped/life-ops-brain ~/.agents/skills/life-ops-brain

# Run setup in a folder you own
mkdir -p ~/my-ops && cd ~/my-ops
codex
```

Then type `$life-ops-brain` or: **Set up my life ops brain**

After setup, open the new brain folder and make Codex load the harness:

```bash
cd ~/path/to/your-new-brain
cp CLAUDE.md AGENTS.md
codex
```

## What you get

A local folder on **your** machine with structure, context, processes (donor thank-yous, donation intake, email triage, weekly money check), and connection checklists. QuickBooks stays the books of record; the brain holds people, notes, and drafts.

## Privacy

- Never put passwords or API keys in the brain folder.
- Family content stays under `family/` and is not used for donor messages unless you ask.
- External messages are **draft only** until you say send.

## Support

If something fails, tell the person who shared this with you which step broke (install, interview, or connections).
