---
name: life-ops-brain
description: "Set someone up with a Life Ops Brain: a small, safe personal AI brain from the public template Plyntr-LLC/life-ops-brain-template, with guards so drafts run and sends wait. Works in Claude Code, Codex, Grok, Antigravity, the Claude and ChatGPT desktop apps, and (with limits) the websites. Optional add-ons for ministry/nonprofit, business and family areas. USE WHEN someone says \"life ops brain\", \"set me up a personal brain\", \"starter brain\", \"/life-ops-brain\", or is handed this skill by a friend."
version: 2.0
last_updated: 2026-11-26
maturity: draft
---

# Life Ops Brain: get it, set it up, grow it

The brain itself lives in one public template: **https://github.com/Plyntr-LLC/life-ops-brain-template**. This skill does not build the folder by hand any more. It gets the template onto the person's computer, runs the template's own `/start`, and then offers the optional life-area add-ons.

Why the template and not hand-built files: the template carries the safety guards (sends wait for the word "send", changes wait for "approve", secrets and destructive commands blocked) for Claude Code, Codex, Grok, Antigravity and Gemini CLI, plus a self-test. Its folders match Plyntr's Client Brain, so Sephy can upgrade it later without losing anything.

**Sephy users:** Sephy sets this up on its own from the person's account. If they are in Sephy, tell them that and stop.

## Tone

- Plain language: "your brain", "folder", "save", "connect". Never repository, commit, frontmatter, MCP, OAuth unless they use those words first.
- One question at a time. Warm and finite.
- **Never send anything during setup.** Drafts only.

## Step 1: Is there already a brain here?

Look in the open folder (and one level down) for `BRAIN.json` containing `"type": "lifeops"`.

- **Found:** this is their brain. Skip to Step 3. If `SETUP-STATUS.md` exists, read it and offer to continue where they stopped.
- **Found an old hand-built life ops brain** (a `CLAUDE.md` mentioning "life ops brain" but no `BRAIN.json`): do not overwrite it. Get the template into a new folder next to it (Step 2), then offer to copy their filled files across using the map in Step 4. Copy, never move or delete.
- **Nothing:** Step 2.

## Step 2: Get the template

Ask once where the brain should live (default: a folder called `my-brain` in their home or Documents folder; avoid iCloud-synced Documents on a Mac if they will connect email or money tools). Call it `<BRAIN>`.

Pick the first path that works where you are running:

**A. You can run commands and `git` is installed** (Claude Code, Codex, Grok, Antigravity, Claude desktop with a folder open):

```bash
git clone https://github.com/Plyntr-LLC/life-ops-brain-template.git "<BRAIN>"
cd "<BRAIN>" && node setup.cjs
```

**B. You can run commands but there is no `git`:** download and unzip the zip, then run `node setup.cjs` if Node is installed.

```bash
curl -L -o /tmp/life-ops-brain.zip https://github.com/Plyntr-LLC/life-ops-brain-template/archive/refs/heads/main.zip
```

Unzip it, move the inner `life-ops-brain-template-main` folder to `<BRAIN>`, and tell them that Codex and Grok need git for their guards (setup.cjs says so too).

**C. You can't run commands or write files** (Claude or ChatGPT on the website, a chat with no folder): give them the zip link above. Tell them to unzip it, and either open the folder in the Claude or ChatGPT desktop app and say "/life-ops-brain" again, or on the website create a Project and upload `AGENTS.md` and the `context/` folder.

After A or B, read `setup.cjs`'s output back in plain words. If the guard self-test failed, stop and say so. Do not continue to connections.

**Guards and where they run.** Tell them once, plainly:
- Claude Code, Codex, Grok and Antigravity enforce the guards. Codex asks "hooks are new or changed": choose **Trust all and continue**. Grok asks "Do you trust the contents of this directory?": choose **Yes, proceed**.
- Claude desktop (Cowork), ChatGPT desktop chat and the websites cannot run guards. There, the written rules in `AGENTS.md` are the protection, so they stay on the first two rungs (read, drafts) of `connections/CONNECTIONS.md`.

## Step 3: Set them up

Run the template's own setup: follow `<BRAIN>/.claude/skills/start/SKILL.md` (or `<BRAIN>/.agents/skills/start/SKILL.md` on ChatGPT/Codex). It checks the guards, fills `context/me.md` and `context/voice.md`, does one real task as a draft, and teaches the two words: **send** and **approve**.

Then ask: "Do you want me to add areas for a ministry or nonprofit, a business, or your family?" If no, you are done (Step 5).

## Step 4: Optional add-ons (going larger)

These use the templates bundled with this skill (`templates/`). Run the interview rounds for the areas they pick, one round at a time, then write the files. **Every add-on goes into the template's existing folders**, so a later upgrade to a bigger brain keeps it all in place:

| Area | Interview | Files go to |
|---|---|---|
| Ministry / nonprofit | org, who you serve, programs, how money comes in (Zeffy, checks), key people (names and roles only), what never goes in a donor email | `context/ministry.md`; `projects/<org-name>/donors/`, `campaigns/`, `notes/`, `money/` (READMEs from `templates/ministry/` and `templates/money/`); `processes/donor-reply.md`, `donation-intake.md`, `weekly-reconciliation.md`; `connections/zeffy-setup.md`, `qbo-setup-guide.md` |
| Business | name, one line on what it does, what you sell and to whom, money path | `context/business.md`; `projects/<business-name>/README.md` |
| Family | only what they are comfortable storing | `context/family.md`; `personal/family/README.md` |
| Email accounts | up to three, each tagged to an area | `connections/gmail-setup.md` |

Rules for add-ons:
- Fill `{{PLACEHOLDERS}}` in the bundled templates with short plain prose. Missing optional fields: one honest line like "Not filled in yet."
- **Never overwrite** a file that already has their writing. Add to it.
- **Do not replace `AGENTS.md`.** Append one short "Life areas" section with the hard-walls table: ministry and donor data stay in its project folder, family stays in `personal/family/` and is never used for donor or client writing unless they ask, and QuickBooks (not this brain) is the books of record.
- Track progress in `<BRAIN>/SETUP-STATUS.md` (from `templates/SETUP-STATUS.md.template`).
- Connections: one at a time, following `references/connection-guides.md` and the ladder in `<BRAIN>/connections/CONNECTIONS.md` (read only first, then drafts). Never write a key or password into any file; name the password-manager entry instead.

## Step 5: Wrap up

Tell them, briefly:
- where their brain is;
- the two words (**send**, **approve**) and that nothing else lets anything out;
- in their tool, "run the command printenv" must be refused, and if it isn't, the guards are off (README explains why);
- first-week prompts are in this skill's `references/first-week-prompts.md`.

If a connection is still open, give the one next step only.

## Never

- Put secrets, API keys, passwords or tokens in any brain file.
- Send email, texts or donation-platform messages during setup.
- Mix family context into donor or client writing.
- Keep a second set of books that can disagree with QuickBooks.
- Push their brain anywhere online. It stays on their computer. Sync to their own GitHub is a later, separate choice.

## Failure modes

| Situation | What to do |
|---|---|
| No Node | The brain still works as notes and rules; guards need Node 18+ from nodejs.org. Say which tools are unprotected until then. |
| Guard self-test fails | Stop before connections. Tell them; do not edit `guards/` to make it pass. |
| No file write access | Path C. |
| Re-run on an existing brain | Step 1 finds `BRAIN.json`; update, never wipe. |

## For the person handing this skill to a friend

See `HANDOFF.md`.
