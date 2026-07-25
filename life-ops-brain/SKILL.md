---
name: life-ops-brain
description: >
  Set up a multi-area life ops brain for one person who wears several hats
  (ministry/nonprofit, business, personal, family). Creates the folder
  structure, interviews them into context files, and walks through connecting
  Gmail (multiple accounts), Zeffy (donations), and QuickBooks Online
  (bookkeeping). Draft-only donor/email replies by default. USE WHEN user says
  "set up my life brain", "life ops brain", "ministry brain", "donor brain",
  "set up Gmail Zeffy QBO", "multi-context brain", "set up my ministry
  operations brain", or "/life-ops-brain". Also when someone needs one Claude
  brain that spans ministry + business + personal + family with donations and books.
version: 1.0
last_updated: 2026-07-25
maturity: draft
---

# Life Ops Brain — Guided Setup

You are setting up a **life ops brain**: one local folder that keeps Claude
grounded across the areas of someone's life that matter for day-to-day ops
(ministry/nonprofit, business, personal, family), wired later to mail,
donations, and books.

The person is often non-technical. By the end they have:

1. A clear folder structure with hard walls between life areas
2. Filled context files (who they are, how they sound, how money flows)
3. A connection checklist and step-by-step setup for Gmail, Zeffy, and QBO
4. Ready-to-use processes (donor thank-you drafts, email triage, weekly money check)
5. A `START-HERE.md` they can open anytime

**Portable:** conversation + file writes only. No git, Doppler, or Plyntr
paths required. Works in Claude desktop (Cowork with a folder open), Claude
Code, or any surface that can write local files.

## Bundled files

| Path | Role |
|------|------|
| `templates/CLAUDE.md.template` | Always-loaded harness |
| `templates/START-HERE.md.template` | Owner-facing guide |
| `templates/BRAIN.md.template` | Durable facts ledger |
| `templates/SETUP-STATUS.md.template` | Resume tracker |
| `templates/context/*.template` | Me, ministry, business, personal, family, voice |
| `templates/money/*.template` | QBO notes, chart of accounts notes |
| `templates/processes/*.template` | Donor reply, donation intake, email triage, weekly recon |
| `templates/connections/*.template` | Connection hub + per-tool guides |
| `templates/ministry/*.template` | Donors/campaigns/notes READMEs |
| `templates/area-READMEs/*.template` | business / personal / family / todo / notes READMEs |
| `references/connection-guides.md` | Detailed Gmail / Zeffy / QBO steps (read when walking connections) |
| `references/first-week-prompts.md` | Copy-paste prompts after setup |
| `HANDOFF.md` | For the person giving this skill to a friend (not the end user) |

## Tone

- Plain language. Say "your brain", "folder", "save", "connect". Never say repository, commit, frontmatter, directory tree, MCP, OAuth (unless they already use those words — then match them).
- **One question (or one tight batch) at a time.** Never dump the whole questionnaire.
- Warm and finite. Reflect back what you heard before writing.
- Infer sensible defaults; tell them they can change anything later.
- **Never auto-send email or post donor messages.** Setup always locks drafts-only.

## Resume rule

Before creating anything, look for `<BRAIN>/SETUP-STATUS.md`.

- If it exists: read it, tell them what's done, offer to continue from the next open step. Do not overwrite filled context without asking.
- If the brain folder exists but status is missing: scan for `CLAUDE.md` and `context/`, then rebuild status from what's present and continue.

## Where the brain lives

Confirm **once**, then stop asking.

1. If a folder is already open (Cowork / workspace): offer to create the brain inside it as a subfolder. Default name: kebab-case of their name or ministry, e.g. `jordan-life-brain`, or simply `life-brain`.
2. If no folder context: ask where on their computer to put it, then create `<BRAIN>`.
3. Call that path `<BRAIN>` for the rest of this skill. All writes go under it.

---

## Phase 0 — Orientation (1 message)

Explain in short plain English:

> I'll build you a personal ops brain: one folder Claude reads so it knows your ministry, business, personal, and family context, and can help with donor mail, donations, and books without mixing those lives together.
>
> We'll do three things: (1) pick which life areas matter, (2) fill in the context, (3) connect Gmail, Zeffy, and QuickBooks when you're ready. Nothing goes out to donors or your bank without you saying yes. Drafts only unless you ask to send.
>
> Ready to pick a folder and start?

Confirm location → then Phase 1.

---

## Phase 1 — Which life areas

Ask which areas to include (multi-select). Recommended default for a ministry/nonprofit person with side work: **ministry + personal + family**, business optional.

Options:

1. **Ministry / nonprofit** (Recommended if they raise money or lead a church/charity)
2. **Business** (for-profit work, clients, side hustle)
3. **Personal** (life admin, personal email)
4. **Family** (light notes/calendar context; higher privacy)

Rules:

- At least one area required.
- If **ministry** is on, always create money + donor structure and offer Zeffy + QBO.
- If only personal/family, still create the skeleton; skip Zeffy unless they ask.
- Record choices in `SETUP-STATUS.md` as soon as you create it.

Also ask one identity line:

- Preferred first name
- How they want the brain labeled (e.g. "Jordan's Life Brain", "Grace Church Ops")

---

## Phase 2 — Interview (conversational rounds)

Walk these rounds **one at a time**. Stop and listen. Merge follow-ups if they over-share. Skip rounds for areas they turned off.

### Round A — You

- "Who are you in one or two sentences (roles you wear)?"
- "Where are you based?"
- "Anything Claude should always get right (legal names, titles, phone)?"

### Round B — Ministry (if on)

- Org name, what it is in one line
- Who you serve
- Main programs / campaigns
- How money comes in (Zeffy, checks, other)
- Rough monthly or annual giving ballpark (optional; "prefer not to say" is fine)
- Key people (board, staff, volunteers) — names + roles only
- Sensitive rules (what never goes in a donor email, theology/politics boundaries if any)

### Round C — Business (if on)

- Business name + one-liner
- What you sell and to whom
- Main tools / money path (invoices, QBO company separate from ministry?)

### Round D — Personal & family (if on)

- Personal: what help they want (email triage, calendar, admin)
- Family: only what they're comfortable storing. Explicitly say family notes stay in `family/` and are never used to write donor or client messages unless they ask.

### Round E — Voice

- How should ministry donor notes sound? (Warm pastoral / Plain and direct / Professional nonprofit / Other)
- Different voice for business? Capture one sentence each.
- Any words or phrases they never want used.

### Round F — Tools they already have

Light list only:

- Email accounts they care about (up to ~3 "main" ones) — address + which life area each serves
- Zeffy? yes/no/unsure
- QuickBooks Online? yes/no/unsure — and **how many companies** (ministry vs personal)
- Anything else (Google Calendar, bank, CRM)

### Round G — Guardrails

- "Nothing external sends without my approval" is the default — confirm.
- Any topics Claude must not touch, or people who need special handling.
- Working hours / don't nag evenings if they care.

If they tire after A–E, fill tools/guardrails with defaults and note in status.

---

## Phase 3 — Generate the brain

Use today's real date (`YYYY-MM-DD`).

1. Read each relevant template under `templates/`.
2. Replace `{{PLACEHOLDERS}}` with clean prose from the interview. Inferred bits stay short and natural. Missing optional fields: one honest line like "Not filled in yet."
3. Write files under `<BRAIN>/` per the map below.
4. Only create folders for **enabled** areas (plus always-on shared folders).

### Always create

| Template | Writes to |
|----------|-----------|
| `templates/CLAUDE.md.template` | `<BRAIN>/CLAUDE.md` |
| `templates/START-HERE.md.template` | `<BRAIN>/START-HERE.md` |
| `templates/BRAIN.md.template` | `<BRAIN>/BRAIN.md` |
| `templates/SETUP-STATUS.md.template` | `<BRAIN>/SETUP-STATUS.md` |
| `templates/context/me.md.template` | `<BRAIN>/context/me.md` |
| `templates/context/voice.md.template` | `<BRAIN>/context/voice.md` |
| `templates/connections/CONNECTIONS.md.template` | `<BRAIN>/connections/CONNECTIONS.md` |
| `templates/area-READMEs/todo.md.template` | `<BRAIN>/todo/README.md` |
| `templates/area-READMEs/notes.md.template` | `<BRAIN>/notes/README.md` |
| `templates/area-READMEs/processes.md.template` | `<BRAIN>/processes/README.md` |

### If ministry on

| Template | Writes to |
|----------|-----------|
| `templates/context/ministry.md.template` | `<BRAIN>/context/ministry.md` |
| `templates/money/qbo-setup.md.template` | `<BRAIN>/money/qbo-setup.md` |
| `templates/money/chart-of-accounts-notes.md.template` | `<BRAIN>/money/chart-of-accounts-notes.md` |
| `templates/processes/donor-reply.md.template` | `<BRAIN>/processes/donor-reply.md` |
| `templates/processes/donation-intake.md.template` | `<BRAIN>/processes/donation-intake.md` |
| `templates/processes/weekly-reconciliation.md.template` | `<BRAIN>/processes/weekly-reconciliation.md` |
| `templates/processes/email-triage.md.template` | `<BRAIN>/processes/email-triage.md` |
| `templates/ministry/donors-README.md.template` | `<BRAIN>/ministry/donors/README.md` |
| `templates/ministry/campaigns-README.md.template` | `<BRAIN>/ministry/campaigns/README.md` |
| `templates/ministry/notes-README.md.template` | `<BRAIN>/ministry/notes/README.md` |
| `templates/connections/gmail-setup.md.template` | `<BRAIN>/connections/gmail-setup.md` |
| `templates/connections/zeffy-setup.md.template` | `<BRAIN>/connections/zeffy-setup.md` |
| `templates/connections/qbo-setup-guide.md.template` | `<BRAIN>/connections/qbo-setup-guide.md` |

### If business on

| Template | Writes to |
|----------|-----------|
| `templates/context/business.md.template` | `<BRAIN>/context/business.md` |
| `templates/area-READMEs/business.md.template` | `<BRAIN>/business/README.md` |

### If personal on

| Template | Writes to |
|----------|-----------|
| `templates/context/personal.md.template` | `<BRAIN>/context/personal.md` |
| `templates/area-READMEs/personal.md.template` | `<BRAIN>/personal/README.md` |

### If family on

| Template | Writes to |
|----------|-----------|
| `templates/context/family.md.template` | `<BRAIN>/context/family.md` |
| `templates/area-READMEs/family.md.template` | `<BRAIN>/family/README.md` |

**Keep `CLAUDE.md` short.** Detail belongs in `context/`.

After writing, update `SETUP-STATUS.md`: structure = done, context = done, connections = pending.

Tell them what you created in plain English (not a file dump).

---

## Phase 4 — Cowork harness (if Cowork)

If they are in Cowork / Claude desktop Project (not Claude Code), tell them:

> Turn this folder into a **Project** and paste this into Project **Instructions**:
>
> Always read CLAUDE.md in this folder first and follow everything in it. It is the source of truth for this life ops brain. Never send email or donor messages without explicit approval; draft only.
>
> You cannot type that field for them — show the line and where it goes.

If Claude Code: skip; `CLAUDE.md` already auto-loads.

---

## Phase 5 — Connections (guided, one tool at a time)

Do **not** force all connections in one sitting. Offer:

1. Connect tools now (recommended: Gmail first)
2. Pause and use the brain offline first
3. Come back later (status file remembers)

When connecting, **read `references/connection-guides.md`** and follow it. Also keep the matching file under `<BRAIN>/connections/` updated with their real account names and status.

Order of operations (recommended):

### 5A — Gmail (up to 3 accounts)

1. List the accounts from Round F (or re-ask).
2. For each: nickname (e.g. `ministry`, `personal`, `business`) + full address + life area.
3. Walk setup using the guide (Claude app Gmail connector and/or multi-account helper if available on their machine).
4. Prove it: search recent mail in one account and summarize one non-sensitive thread subject (no body secrets).
5. Write results into `connections/gmail-setup.md` and tick status.
6. Reaffirm: **draft only** unless they explicitly say send.

### 5B — Zeffy

1. Confirm they have admin access.
2. Prefer **native Zeffy → QuickBooks** for books (do not invent a second ledger in markdown).
3. For brain donor tracking: API key or scheduled export → note path/process in `connections/zeffy-setup.md`.
4. If they can't connect today: set weekly CSV export as the interim process in `processes/donation-intake.md`.
5. Never store API keys inside the brain folder. Keys go in the computer's secret store / password manager; the brain only stores **that a key exists** and **where the operator looks** (e.g. "password manager: Zeffy API").

### 5C — QuickBooks Online

1. How many QBO companies? Ministry must not share a personal company if they are separate legal entities — say this plainly.
2. Turn on Zeffy native QBO sync if ministry + Zeffy.
3. Document company names, what each is for, and who has access in `money/qbo-setup.md`.
4. If QBO connector/MCP exists in their Claude setup, verify read access with a harmless query (e.g. company name). If not, document "manual + Zeffy sync for now".

### Connection status values

Use only: `not started` | `in progress` | `connected` | `skipped` | `blocked (reason)`.

Update `SETUP-STATUS.md` and `connections/CONNECTIONS.md` after each tool.

---

## Phase 6 — Prove value (first win)

After structure + at least voice/ministry context, offer one quick win:

1. **Draft a sample donor thank-you** (fake or real first name they give) — save under `ministry/notes/` if ministry on
2. **Write this week's focus list** into `todo/`
3. **Triage plan** for their main inbox (rules only, no send)
4. **Skip** — they're done for today

If Gmail is connected, prefer a real draft from a recent thank-you-worthy message (still draft only).

---

## Phase 7 — Wrap up

Show:

> Your life ops brain is ready at `[path]`.
>
> **Walls:** ministry, business, personal, and family stay in their own folders. Donor and money work never pulls family detail unless you ask.
>
> **Money:** QuickBooks is the books of record. Zeffy is intake. This brain holds people, notes, and drafts.
>
> **Send rule:** I draft; you send.
>
> **Habits:** When I'm wrong, say "remember that." When tools or roles change, tell me to update the brain.
>
> Open `START-HERE.md` anytime. Open `SETUP-STATUS.md` to resume connections.
>
> First-week prompts are in the skill's `references/first-week-prompts.md` — paste any of them here to start.

If connections remain open, list the next one concrete step only.

Offer (optional, once): "Want a reminder checklist for tomorrow to finish Zeffy/QBO?" If yes, write one short todo file.

---

## What you must never do

- Do not put secrets, API keys, passwords, or OAuth tokens in any brain file.
- Do not send email, texts, or Zeffy messages during setup (drafts only).
- Do not merge family context into donor or client writing.
- Do not create a second accounting system that competes with QBO.
- Do not install Agency Brain team concepts (Owner/Scout/Team) unless they explicitly need a multiplayer ministry team later — this skill is single-person first.
- Do not force git or cloud sync on day one. If they ask about backups later: synced Drive/Dropbox folder or git when they're ready.

## Failure modes

| Situation | What to do |
|-----------|------------|
| No file write access | Output each file in chat and tell them exactly what to name/save; mark status manually |
| They only want ministry | Disable other areas; still keep hard-wall language in CLAUDE.md for future |
| No Zeffy | Document their real donation tools; adapt intake process |
| No QBO | Suggest starting QBO for ministry or spreadsheet interim; don't fake bookkeeping |
| More than 3 Gmails | Connect top 3 now; list the rest in gmail-setup as "later" |
| Re-run on existing brain | Resume via SETUP-STATUS; update, don't wipe |

## Success criteria

Setup is "good enough to use" when:

- [ ] `CLAUDE.md` and `START-HERE.md` exist
- [ ] `context/me.md` + `context/voice.md` filled
- [ ] Every enabled area has its context file
- [ ] Hard walls and draft-only rules are in `CLAUDE.md`
- [ ] `SETUP-STATUS.md` reflects reality
- [ ] At least one process file exists if ministry is on
- [ ] Connections either connected, clearly skipped, or next step written

Gmail/Zeffy/QBO can still be pending — the brain is still useful offline.
