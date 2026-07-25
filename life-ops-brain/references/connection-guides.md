# Connection guides (for Claude during Phase 5)

Read this when walking the owner through Gmail, Zeffy, or QBO. Use plain language
with them; keep technical labels only if they already use them.

**Never write secrets into the brain.** Password manager names only.

---

## Gmail (up to 3 accounts)

### Goal

Claude can read and **draft** on the owner's main accounts, each tagged to a life area.

### Paths (pick what their Claude surface supports)

**A — Claude desktop / Cowork connectors (simplest)**

1. Open Claude settings → connectors / integrations.
2. Connect Gmail for the first account; complete Google sign-in.
3. If the product only allows one Gmail connector: connect the **ministry** account first (highest stakes), document the others as "manual forward or switch account later."
4. Test: "List my unread from the last 3 days" (subjects only if privacy-sensitive).
5. Confirm draft: "Create a draft reply to myself saying connection test" — owner deletes it.

**B — Multi-account helper already on the machine**

Some setups (like a multi-account Gmail helper) support nicknames (`ministry`, `personal`, `business`). If that exists:

1. Add each account with a short nickname.
2. Sign in once per account when prompted.
3. Restart Claude / the helper so accounts appear.
4. Test search with an explicit account nickname.
5. Record nicknames in `connections/gmail-setup.md`.

**C — No connector available**

1. Document accounts and routing in `gmail-setup.md` anyway.
2. Owner pastes email threads when they want help.
3. Mark Gmail status `skipped` or `blocked (no connector)` and move on. The brain still works.

### Routing defaults

| Life area | Use account |
|-----------|-------------|
| Ministry / donors | ministry nickname |
| Business | business nickname |
| Personal / family | personal nickname |

If only one account is connected, say so in routing notes and be careful labeling.

### Done when

- Status is `connected` for at least one account, or consciously `skipped`
- Table in `gmail-setup.md` is filled
- Owner knows drafts ≠ sends

---

## Zeffy

### Goal

Donations flow into **QBO** for books; this brain gets enough donor context for thank-yous and tracking people.

### Step 1 — Native QBO (do this first)

1. Owner signs into Zeffy as admin.
2. Open **Finance → QuickBooks** (wording may be "Integrations" / "QuickBooks").
3. Connect the **ministry** QBO company (not a personal company).
4. Map campaigns/funds as Zeffy prompts.
5. Confirm a recent payout shows as expected (or wait for next payout).
6. Update `zeffy-setup.md` and `money/qbo-setup.md`.

Public docs (for the owner if they want to click through): Zeffy integrations and QuickBooks help on zeffy.com.

### Step 2 — Data for the brain

**Preferred long-term:** Zeffy public API (donations, contacts, campaigns). Free on Zeffy as of 2026 marketing — verify in their current admin UI.

1. Create/read API credentials in Zeffy admin.
2. Store the secret in a **password manager** under a name you write in `zeffy-setup.md` (e.g. `Zeffy API — ministry`).
3. If a Claude connector for Zeffy does not exist yet: set process to weekly export until one is built.

**Interim:** Export CSV of payments/donors on a schedule; owner drops file into a agreed folder or attaches in chat; Claude runs `processes/donation-intake.md`.

### Step 3 — Messaging donors on Zeffy

1. Check whether the owner actually uses in-platform messages vs email.
2. If email is the real channel: rely on Gmail drafts.
3. If Zeffy messages matter: draft text in chat or `ministry/notes/`; owner pastes into Zeffy until automation is proven.

### Done when

- QBO sync is `connected` or owner chose a clear alternative
- Active brain method is written (API / export / manual)
- No API key appears in any brain file

---

## QuickBooks Online

### Goal

One clear company per legal entity; ministry giving does not hit personal books.

### Steps

1. List every QBO company the owner has. Write them in `money/qbo-setup.md`.
2. Confirm ministry (nonprofit) company identity.
3. Finish Zeffy native link if applicable.
4. If Claude has a QBO integration on this machine: authorize **read** first; test by retrieving company name only.
5. Write access rules: no invoices/bills/journals without explicit yes.
6. Optional: note classes/locations/funds the owner cares about in `chart-of-accounts-notes.md`.

### If they have no QBO yet

- Recommend starting a QBO company for the ministry before heavy automation.
- Interim: bank + Zeffy exports only; mark QBO `not started` with next step "create ministry QBO company."
- Do not fake full bookkeeping in markdown.

### Done when

- Companies table is accurate
- Separation ministry vs personal is explicit
- Status reflects reality (`connected` / `in progress` / `skipped`)

---

## Order and pacing

Recommended order: **Gmail → Zeffy QBO sync → Zeffy export/API → QBO connector (if any)**.

One tool per sitting is fine. Always leave a single next step in `SETUP-STATUS.md`.
