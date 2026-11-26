# Life ops brain — bulletproof setup (Codex / ChatGPT)

**For anyone new to terminals.**  
Do **one path only**. Prefer Path A. Stop if something fails and send the person who set this up for you a screenshot + the step number.

| Path | What it is | Who should use it |
|------|------------|-------------------|
| **A — ChatGPT desktop (recommended)** | App with folders on your computer. Closest to Claude Cowork. | Almost everyone. No terminal required for daily use. |
| **B — Terminal Codex** | Black/white window where you type commands. | If Path A is broken or you already use Terminal. |

**Links you will need**

- Package (zip): https://github.com/joeprosynergy/life-ops-brain/archive/refs/heads/main.zip  
- Project page: https://github.com/joeprosynergy/life-ops-brain  
- ChatGPT desktop download: https://chatgpt.com/download/

**Hard rules**

1. Use **your own** ChatGPT / OpenAI login (not someone else’s).  
2. Never put passwords or API keys into brain files.  
3. Codex / ChatGPT should **draft** donor emails. **You** send them.  
4. Type commands **exactly** (spaces matter). Press **Enter** after each command.  
5. If you see an error: copy the full text → email joe@plyntr.com with the step number.

---

# Path A — ChatGPT desktop app (recommended, Cowork-like)

This is the same idea as Claude Cowork: a **local folder** on your machine that the AI can read and write, plus a **skill** that walks setup.

## A0 — What you need

- Mac or Windows computer  
- A ChatGPT account that can use **Codex** in the desktop app (Plus / Pro / Team / Enterprise / Edu typically; Free may have limits).  
  If the app says Codex is not available, tell the person who set this up for you your plan name.  
- About 30–45 minutes for first setup  

## A1 — Install the ChatGPT desktop app

1. Open https://chatgpt.com/download/  
2. Download for **Mac** or **Windows**.  
3. Install and open the app.  
4. Sign in with **your** ChatGPT account.  

**Note (July 2026):** The old “Codex app” merged into the **ChatGPT desktop app**.  
If you still have an old Codex app, update it; it becomes ChatGPT desktop.  
“ChatGPT Classic” is the older chat-only app — for this guide you want the **new** desktop app that has **ChatGPT / Work / Codex** in the top-left menu.

## A2 — Download and unzip the life-ops package

1. Open this link:  
   https://github.com/joeprosynergy/life-ops-brain/archive/refs/heads/main.zip  
2. Wait for download.  
3. Unzip:  
   - **Mac:** double-click the zip  
   - **Windows:** right-click → **Extract All**  
4. You should get a folder like `life-ops-brain-main`.  
5. Open it. Inside is a folder named **`life-ops-brain`** that contains **`SKILL.md`**.  
   That inner `life-ops-brain` folder is the skill. Do not lose it.

## A3 — Create an empty folder for *your* brain

This is where your real files will live (ministry, business, personal). Separate from the skill package.

**Mac**

1. Open **Finder**.  
2. Go to your home folder (or Documents).  
3. **File → New Folder**.  
4. Name it exactly: `my-life-ops`  

**Windows**

1. Open **File Explorer**.  
2. Go to Documents (or your user folder).  
3. Right-click → **New → Folder**.  
4. Name it exactly: `my-life-ops`  

Leave this folder empty for now.

## A4 — Install the skill (one time)

Skills live in a special place so Codex can find them.

### Mac (easiest: Terminal once)

1. Spotlight (**⌘ + Space**) → type `Terminal` → Enter.  
2. Paste this **whole block** and press Enter (it creates the skills folder and copies the skill if the zip is in Downloads):

```bash
mkdir -p ~/.agents/skills
cp -R "$HOME/Downloads/life-ops-brain-main/life-ops-brain" "$HOME/.agents/skills/life-ops-brain"
ls "$HOME/.agents/skills/life-ops-brain/SKILL.md"
```

3. You should see a line ending in `SKILL.md`.  
4. If you see “No such file”, the zip is not in Downloads. Fix the path:  
   - Finder → go into your unzipped folder → click `life-ops-brain` → right-click title bar icon → hold **Option** → **Copy “life-ops-brain” as Pathname**  
   - Then run:

```bash
mkdir -p ~/.agents/skills
cp -R "PASTE_YOUR_PATH_HERE" "$HOME/.agents/skills/life-ops-brain"
ls "$HOME/.agents/skills/life-ops-brain/SKILL.md"
```

### Windows (Command Prompt once)

1. Start → type `cmd` → **Command Prompt**.  
2. Paste:

```text
mkdir %USERPROFILE%\.agents\skills
xcopy /E /I "%USERPROFILE%\Downloads\life-ops-brain-main\life-ops-brain" "%USERPROFILE%\.agents\skills\life-ops-brain"
dir %USERPROFILE%\.agents\skills\life-ops-brain\SKILL.md
```

3. You should see `SKILL.md` listed.  
4. If not found, open the unzipped folder in Explorer, click the address bar, copy the path to the **inner** `life-ops-brain` folder, and run:

```text
mkdir %USERPROFILE%\.agents\skills
xcopy /E /I "PASTE_YOUR_PATH_HERE" "%USERPROFILE%\.agents\skills\life-ops-brain"
```

**Check (either OS):** You must have a file at:

- Mac: `~/.agents/skills/life-ops-brain/SKILL.md`  
- Windows: `C:\Users\YOURNAME\.agents\skills\life-ops-brain\SKILL.md`

## A5 — Open a local project (this is the Cowork-like part)

1. Open the **ChatGPT desktop app**.  
2. Top-left menu: choose **Codex** (not only Chat).  
   - If you only see Chat/Work, still try **Projects** and “open local folder” / “local project”.  
3. Create or open a **local project** that points at `my-life-ops`:  
   - Look for **Projects** → **New project** / **Add folder** / **Open folder**.  
   - Select your **`my-life-ops`** folder.  
   - If asked for a **primary** folder, choose `my-life-ops`.  
4. Approve file access when the Mac/Windows permission popup appears.  
5. Start a **new chat** inside that project.

**What “Cowork-like” means here**

| Claude Cowork | ChatGPT desktop (Path A) |
|---------------|---------------------------|
| Open a folder | Local project → attach `my-life-ops` |
| Skill runs setup | Skill `$life-ops-brain` or “Set up my life ops brain” |
| Project instructions | After setup: `AGENTS.md` (copy of `CLAUDE.md`) auto-loads |
| Files stay on your Mac | Files stay on your computer |

Web ChatGPT alone **cannot** write a full brain to your disk. You need the **desktop app** for local folders.

## A6 — Run setup

In the chat box, type **exactly one** of these:

```text
$life-ops-brain
```

or

```text
Set up my life ops brain
```

Then:

1. Answer questions one at a time (name, ministry, businesses, emails, etc.).  
2. When it asks to create/write files in `my-life-ops`, **allow** / **yes**.  
3. You can stop anytime. Later say: `Continue life ops setup`  
4. Connections (Gmail / Zeffy / QuickBooks) can wait for a second session.

## A7 — Lock in the rules file (do not skip)

After the first setup pass finishes, your folder should contain `CLAUDE.md` (and `START-HERE.md`, `SETUP-STATUS.md`, etc.).

Codex loads **`AGENTS.md`** as standing rules. Make a copy:

### Mac Terminal

```bash
cd ~/Documents/my-life-ops 2>/dev/null || cd ~/my-life-ops
cp CLAUDE.md AGENTS.md
ls CLAUDE.md AGENTS.md
```

(If your folder is only in Documents, use that path. If `CLAUDE.md` is missing, list files with `ls` and `cd` into the subfolder Codex created.)

### Windows Command Prompt

```text
cd %USERPROFILE%\Documents\my-life-ops
copy CLAUDE.md AGENTS.md
dir CLAUDE.md AGENTS.md
```

If the folder is under your user home instead of Documents:

```text
cd %USERPROFILE%\my-life-ops
copy CLAUDE.md AGENTS.md
```

Restart the chat (new chat in the same local project). Codex should now always respect draft-only and ministry/family walls.

## A8 — Every day (Path A)

1. Open ChatGPT desktop.  
2. Open your **my-life-ops** local project.  
3. New chat (or continue an old one).  
4. Talk in plain English, for example:

```text
What should I focus on this week?
```

```text
Draft a donor thank-you for Sarah who gave to the building fund. Do not send.
```

```text
Continue life ops setup. Connect Gmail, then Zeffy, then QuickBooks. One step at a time.
```

---

# Path B — Terminal only (fallback)

Use this if the desktop app will not open local folders, or you prefer CLI.

## B1 — Open Terminal / Command Prompt

- **Mac:** ⌘ + Space → `Terminal` → Enter  
- **Windows:** Start → `cmd` → Command Prompt  

## B2 — Install Codex CLI

### Mac (preferred)

```bash
brew install --cask codex
```

If `brew: command not found`, install Homebrew from https://brew.sh (one install line), then run the brew line again.

### Alternative (Mac/Windows with Node already installed)

```bash
npm install -g @openai/codex
```

### Check

```bash
codex --version
```

You need a version number. If `command not found`, install failed — stop and message the person who set this up for you.

## B3 — Login (your account)

```bash
codex login
```

Sign in in the browser with **your** ChatGPT account.  
If login fails on a “Go” or free plan, tell the person who set this up for you your plan name; Codex may need Plus or higher.

## B4 — Install the skill

Same as **A2 + A4** (download zip, then copy into `~/.agents/skills/life-ops-brain`).

**Mac check:**

```bash
ls ~/.agents/skills/life-ops-brain/SKILL.md
```

**Windows check:**

```text
dir %USERPROFILE%\.agents\skills\life-ops-brain\SKILL.md
```

## B5 — Create brain folder and start

**Mac**

```bash
mkdir -p ~/my-life-ops
cd ~/my-life-ops
codex
```

**Windows**

```text
mkdir %USERPROFILE%\my-life-ops
cd %USERPROFILE%\my-life-ops
codex
```

Then type:

```text
$life-ops-brain
```

or

```text
Set up my life ops brain
```

## B6 — AGENTS.md (same as A7)

**Mac**

```bash
cd ~/my-life-ops
cp CLAUDE.md AGENTS.md
codex
```

**Windows**

```text
cd %USERPROFILE%\my-life-ops
copy CLAUDE.md AGENTS.md
codex
```

## B7 — Every day (Path B)

**Mac**

```bash
cd ~/my-life-ops
codex
```

**Windows**

```text
cd %USERPROFILE%\my-life-ops
codex
```

---

# Connecting Gmail, Zeffy, QuickBooks

Do this **after** the interview and folder exist.

Say:

```text
Continue life ops setup. Help me connect Gmail, then Zeffy, then QuickBooks. One tool at a time. I am new to this.
```

| Tool | What happens |
|------|----------------|
| **Gmail** | Desktop may offer connectors; if not, you paste emails and get drafts. |
| **Zeffy** | Mostly browser clicks; native Zeffy → QuickBooks sync is preferred for books. |
| **QuickBooks** | Books of record. Brain holds people and drafts, not a second ledger. |

Never store API keys in the brain folder. Password manager only.

---

# If something goes wrong

| Problem | Fix |
|---------|-----|
| Codex not in app / greyed out | Plan may not include Codex. Message the person who set this up for you with your plan name (Plus, Pro, etc.). |
| Login failed / wrong account | Sign out, use **your** account only. |
| `$life-ops-brain` does nothing | Type `Set up my life ops brain`. Restart app. Re-check skill path (A4). |
| Skill not found | Repeat A4; confirm `SKILL.md` exists. Restart ChatGPT desktop / Terminal. |
| `command not found: codex` | Path B install again; close and reopen Terminal. |
| No `CLAUDE.md` after setup | You may be in the wrong folder. List files; open the folder that has `START-HERE.md`. |
| Afraid you broke something | Stop. This does not touch bank accounts. Send the person who set this up for you the error text. |
| “Go plan” / shared login issues | Each person needs their **own** paid plan that includes Codex. |
| **Apple “Hide My Email” login fails in Terminal** | See **Apple Hide My Email / Sign in with Apple** section below. Very common. |

---

# Apple Hide My Email / Sign in with Apple (common CLI failure)

If ChatGPT was created with **Sign in with Apple** and **Hide My Email** (a random address like `xxxx@privaterelay.appleid.com`), **browser chat can work** while **`codex login` in Terminal fails**. That is a known pain point: the CLI needs a browser login to hand a token back to Terminal, and Apple’s relay + password flow often breaks that handoff.

Try these **in order**. Stop when one works.

## Fix 1 — Prefer ChatGPT desktop (skip Terminal login)

You do **not** need Terminal login if desktop works.

1. Install/open ChatGPT desktop: https://chatgpt.com/download/  
2. Sign in with **Continue with Apple** the same way you use chatgpt.com.  
3. Use **Path A** (local project on `my-life-ops`).  
4. Only come back to Terminal if you specifically need the CLI.

Many people get fully set up this way and never run `codex login`.

## Fix 2 — Device code login (best Terminal fix)

This avoids the “browser → localhost callback” step that often fails with Apple.

1. On the computer, open **https://chatgpt.com** and sign in (Apple is fine).  
2. Open **Settings → Security** (or **Settings → Account / Data controls** if labels differ).  
3. Turn on **Device code login** / **Sign in with device code** if you see it.  
4. In Terminal:

```bash
codex logout
codex login --device-auth
```

5. Terminal will show a **URL** and a **one-time code**.  
6. Open the URL on **this same Mac** (Safari or Chrome), sign in with Apple if asked, enter the code.  
7. Wait until Terminal says login succeeded. Check:

```bash
codex login status
```

If device code is missing from settings, your plan or region may not show it yet — go to Fix 3.

## Fix 3 — Give the OpenAI account a real email + password

Hide My Email is for privacy; OpenAI’s developer tools often need a **normal** login path.

1. Sign in at https://chatgpt.com with Apple.  
2. Open **Settings → Account** (or profile → **Personalization / Account**).  
3. Look for **Email**, **Add email**, or **Password**.  
4. Add a **real email you can open** (Gmail, etc.) and verify it if asked.  
5. Set an **OpenAI password** (this is separate from your Apple password).  
6. Sign out of chatgpt.com completely.  
7. Sign back in with **email + OpenAI password** (not “Continue with Apple”).  
8. In Terminal:

```bash
codex logout
codex login
```

9. In the browser window that opens, choose **email/password**, not Apple.

### If you cannot find “add email”

Apple controls the Hide My Email address:

1. On iPhone/Mac: **Settings → [your name] → Sign in with Apple** → find **OpenAI / ChatGPT**.  
2. See whether it says **Hide My Email** or **Share My Email**.  
3. If possible, switch to **Share My Email** with a real address, or stop using Apple for this app and use email login after adding one in ChatGPT settings.  
4. Do **not** delete the Hide My Email address until you can still open the ChatGPT account another way (real email/password). Deleting the relay first can lock you out.

## Fix 4 — Login on desktop, then use CLI with shared auth cache

Sometimes desktop can sign in when Terminal’s browser flow fails. After desktop is signed into **Codex**, CLI often reuses the same local credentials.

1. Open ChatGPT desktop → top-left **Codex** → sign in successfully.  
2. Quit Terminal completely, open a new Terminal window.  
3. Run:

```bash
codex login status
```

4. If it already shows logged in, you are done.  
5. If not, try:

```bash
codex login --device-auth
```

again (Fix 2).

## Fix 5 — Last resort: new ChatGPT account with a normal email

Only if the Apple-only account cannot be fixed:

1. Create a **new** ChatGPT account with a normal email + password (no Hide My Email).  
2. Move any Plus/Pro subscription to that account if needed.  
3. Use that account for Codex and life ops.

Do this only after Fix 3 fails, so you do not lose paid access.

## What not to do

- Do not paste passwords into Terminal as random commands.  
- Do not share anyone else’s ChatGPT login.  
- Do not use a Platform **API key** unless you understand it bills **separately** from ChatGPT Plus (pay-per-use). Prefer subscription ChatGPT login for Codex.

---

# Cheat sheet

**Desktop daily (Path A)**  
ChatGPT app → Codex → open `my-life-ops` project → chat.

**Terminal daily (Path B)**

```bash
cd ~/my-life-ops && codex
```

**Resume setup**

```text
Continue life ops setup
```

**Re-run skill**

```text
$life-ops-brain
```

---

# For the person handing this out

1. Prefer Path A (desktop = Cowork analogue).  
2. Confirm his ChatGPT plan can run **Codex** on desktop before he starts.  
3. Package: https://github.com/joeprosynergy/life-ops-brain  
4. After first session, verify he has both `CLAUDE.md` and `AGENTS.md` in `my-life-ops`.  
5. Second session: Gmail → Zeffy → QBO only.

Questions → joe@plyntr.com with step number + exact error.
