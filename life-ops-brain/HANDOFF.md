# Handoff: giving someone a Life Ops Brain

For **you**, the person handing it out, not the end user.

## The short version

Send them this, matched to the app they use:

**Claude Code, Codex, Grok or Antigravity (a terminal):**

> 1. Install Node from https://nodejs.org if you don't have it.
> 2. Run:
>    `git clone https://github.com/Plyntr-LLC/life-ops-brain-template.git my-brain`
>    `cd my-brain && node setup.cjs`
> 3. Open the folder in your AI tool and say **/start**.
> 4. Codex: at "hooks are new or changed" choose **Trust all and continue**. Grok: at "Do you trust the contents of this directory?" choose **Yes, proceed**.

**Claude desktop or ChatGPT desktop (no terminal):**

> 1. Download https://github.com/Plyntr-LLC/life-ops-brain-template/archive/refs/heads/main.zip and unzip it.
> 2. Open the folder in the app (Claude: Cowork, pick the folder. ChatGPT: open it as a local project).
> 3. Say **/start**.

**Sephy users:** nothing. Sephy sets it up from their account.

## What they get

The template: rules in `AGENTS.md`, guards so sends wait for "send" and changes wait for "approve", a self-test, `context/` for who they are and how they sound, a connection ladder, and folders that match the Client Brain (`projects/`, `personal/`, `todo/`). Optional add-ons through this skill: ministry or nonprofit (donors, campaigns, Zeffy, QuickBooks), business, family.

## Where the guards run

| App | Guards |
|---|---|
| Claude Code, Codex, Grok, Antigravity | Enforced |
| Claude desktop (Cowork), ChatGPT desktop chat, the websites | Not possible. Written rules only, so keep connections to read and drafts. |

`references/CODEX-FOR-BEGINNERS.md` has click-by-click steps for ChatGPT desktop.

## Design choices baked in

- Single person. No Owner, Scout or Team.
- QuickBooks is the books of record; the brain holds people, notes and drafts.
- Drafts only for anything outgoing.
- Hard walls between ministry, business, personal and family.
- Secrets never in the folder.
- Local only. Syncing to their own GitHub is a later choice.

## Maintaining

- The brain's shape lives in the template repo, `Plyntr-LLC/life-ops-brain-template`. Change it there.
- This skill's `templates/` are only the add-on areas.
- Edit `references/connection-guides.md` when Zeffy or QuickBooks labels change.
