# Codex for complete beginners

This guide assumes you have **never used a terminal** before.  
Go step by step. Do not skip ahead. If something looks different on your screen, stop and reply to Joe with a screenshot.

You will:

1. Open a small program called Terminal (Mac) or Command Prompt (Windows)
2. Install Codex (if it is not already installed)
3. Download the life-ops-brain package
4. Put it where Codex can find it
5. Run the setup
6. Use it day to day

---

## Words you will see

| Word | What it means |
|------|----------------|
| **Terminal** | A plain window where you type commands and press Enter. No mouse menus. |
| **Command** | A short line of text you type, then press **Enter** / **Return**. |
| **Folder** | Same as a directory. A place that holds files. |
| **Codex** | OpenAI’s coding assistant that runs in the terminal. |
| **Cursor** | The blinking line that shows where your typing goes. |

**Rules that save you:**

- Type commands **exactly** as written (spaces matter).
- Press **Enter** after each command.
- If you see an error, **copy the full error text** and send it to Joe. Do not guess.
- Never paste passwords into random websites. For this guide you only use Terminal + your browser + Codex login.

---

## Step 0 — What computer are you on?

- **Mac** (Apple laptop/desktop) → use the **Mac** steps.
- **Windows** PC → use the **Windows** steps.
- If you are not sure: look at the logo key on the keyboard (⌘ Command = Mac, Windows logo = Windows).

---

## Step 1 — Open the terminal

### Mac

1. Click the **magnifying glass** (Spotlight) in the top-right of the screen.  
   Or press **Command (⌘) + Space**.
2. Type: `Terminal`
3. Press **Enter** when **Terminal** appears.
4. A white or black window opens. That is Terminal. Leave it open.

### Windows

1. Click the **Start** button (Windows logo).
2. Type: `cmd`
3. Click **Command Prompt**.
4. A black or blue window opens. Leave it open.

---

## Step 2 — Install Codex (skip if you already use Codex)

Still in Terminal / Command Prompt.

### Mac

Copy this **whole line**, paste into Terminal, press **Enter**:

```bash
brew install --cask codex
```

- If it says `brew: command not found`, install Homebrew first from https://brew.sh (follow only their one install line), then run the line above again.
- If `brew` works but you prefer another method, this also works:

```bash
npm install -g @openai/codex
```

(Only if you already have Node/npm. If you do not, stick with `brew`.)

### Windows

Easiest path for most people:

1. Open https://github.com/openai/codex/releases in your browser.
2. Or install via npm if you already have Node.js:

```text
npm install -g @openai/codex
```

If you get stuck on install, message Joe before continuing.

### Check that Codex is installed

In the same window, type:

```bash
codex --version
```

Press **Enter**.

- If you see a version number (like `0.something`), you are good.
- If it says `command not found` / `not recognized`, Codex is not installed yet. Stop and tell Joe.

---

## Step 3 — Log in to Codex (first time only)

Type:

```bash
codex login
```

Press **Enter**.

- A browser window may open. Sign in with the ChatGPT / OpenAI account you use for Codex.
- When it says you are logged in, return to the terminal window.
- You only do this once (or when it expires).

---

## Step 4 — Download the life-ops-brain package

### Easiest way (browser)

1. Open this link in your browser:  
   **https://github.com/joeprosynergy/life-ops-brain/archive/refs/heads/main.zip**
2. Wait for the download to finish.
3. Find the file (usually in **Downloads**). Name is something like `life-ops-brain-main.zip`.
4. **Unzip it**  
   - **Mac:** double-click the zip. A folder `life-ops-brain-main` appears.  
   - **Windows:** right-click the zip → **Extract All** → Extract.
5. Open that folder. Inside you should see another folder named **`life-ops-brain`**.  
   That inner folder is the one that matters (it contains a file called `SKILL.md`).

### Find the full path of that inner folder

You need the “address” of the `life-ops-brain` folder for the next step.

**Mac**

1. Open **Finder**.
2. Go into `life-ops-brain-main`, then click once on the **`life-ops-brain`** folder (do not open it yet).
3. Right-click (or Control-click) → **Get Info**.
4. Look at **Where:** — that is the parent path.  
   Or: open the folder, then right-click the title bar icon → hold **Option** → **Copy “life-ops-brain” as Pathname**.
5. Write it down. Example shape (yours will differ):  
   `/Users/YourName/Downloads/life-ops-brain-main/life-ops-brain`

**Windows**

1. Open the extracted folder in File Explorer.
2. Click in the address bar at the top.
3. Copy the path (Control+C). Example shape:  
   `C:\Users\YourName\Downloads\life-ops-brain-main\life-ops-brain`

---

## Step 5 — Install the skill so Codex can see it

Go back to Terminal / Command Prompt.

### Mac

Type this **first** line, then Enter:

```bash
mkdir -p ~/.agents/skills
```

That creates a home for skills. (If it already exists, nothing bad happens.)

Then install the skill. **Replace the path** with *your* real path from Step 4:

```bash
cp -R "/Users/YourName/Downloads/life-ops-brain-main/life-ops-brain" ~/.agents/skills/life-ops-brain
```

Example if your Mac username is `manoj` and the zip landed in Downloads:

```bash
cp -R "/Users/manoj/Downloads/life-ops-brain-main/life-ops-brain" ~/.agents/skills/life-ops-brain
```

### Windows (Command Prompt)

```text
mkdir %USERPROFILE%\.agents\skills
```

Then (fix the path with yours):

```text
xcopy /E /I "%USERPROFILE%\Downloads\life-ops-brain-main\life-ops-brain" "%USERPROFILE%\.agents\skills\life-ops-brain"
```

### Check it landed

**Mac:**

```bash
ls ~/.agents/skills/life-ops-brain/SKILL.md
```

You should see a path printed ending in `SKILL.md`.

**Windows:**

```text
dir %USERPROFILE%\.agents\skills\life-ops-brain\SKILL.md
```

You should see `SKILL.md` listed.

If not found, the copy path was wrong. Fix the path and try Step 5 again.

---

## Step 6 — Make a folder for your new brain

This is an **empty** folder on *your* computer where Codex will build your life ops brain.

### Mac

```bash
mkdir -p ~/my-life-ops
cd ~/my-life-ops
```

### Windows

```text
mkdir %USERPROFILE%\my-life-ops
cd %USERPROFILE%\my-life-ops
```

You are now “inside” that folder. Leave the terminal window open.

---

## Step 7 — Start Codex and run setup

Type:

```bash
codex
```

Press **Enter**.

- Codex may take a few seconds to start.
- You may need to approve access the first time. Choose the safe / recommended options if asked.
- When you can type to Codex, type **exactly**:

```text
$life-ops-brain
```

Press **Enter**.

**If `$life-ops-brain` does nothing**, try typing this instead:

```text
Set up my life ops brain
```

Then:

1. Answer Codex’s questions one at a time (name, ministry, emails, etc.).
2. Let it create folders and files. Say yes when it asks to write files in this folder.
3. You can pause anytime. Later say: `Continue life ops setup`

When it finishes the first pass, it will tell you the brain is ready.

---

## Step 8 — Make the brain load every time (important)

After setup, your brain is a folder (for example `~/my-life-ops` or a subfolder inside it that Codex named).

1. **Quit Codex** for a moment if you need a clean start (type `/exit` or quit as the app shows you).
2. In Terminal, go into the brain folder. If everything was created *in* `my-life-ops`, this is enough:

**Mac:**

```bash
cd ~/my-life-ops
cp CLAUDE.md AGENTS.md
codex
```

**Windows:**

```text
cd %USERPROFILE%\my-life-ops
copy CLAUDE.md AGENTS.md
codex
```

- If `CLAUDE.md` is not found, the brain may be in a subfolder. List files:

**Mac:** `ls`  
**Windows:** `dir`

Then `cd` into the subfolder that contains `CLAUDE.md`, and run the `cp` / `copy` line there.

`AGENTS.md` is how Codex remembers your rules (draft only, walls between ministry/family, etc.).

---

## Step 9 — How you use it every day

1. Open Terminal (Step 1).
2. Go to your brain folder:

**Mac:**

```bash
cd ~/my-life-ops
codex
```

**Windows:**

```text
cd %USERPROFILE%\my-life-ops
codex
```

3. Ask in plain English. Examples:

```text
What should I focus on this week?
```

```text
Draft a donor thank-you for Sarah who gave to the building fund. Do not send.
```

```text
Walk me through connecting Zeffy to QuickBooks. One step at a time.
```

```text
Continue life ops setup
```

**Important:** Codex should **draft** emails and donor messages. **You** send them.  
If it ever offers to send, say **no** unless you mean it.

---

## Connecting Gmail, Zeffy, and QuickBooks

Do this **after** the folder and interview exist.

Say to Codex:

```text
Continue life ops setup. Help me connect Gmail, then Zeffy, then QuickBooks. One tool at a time. I am new to this.
```

- Gmail connection depends on what Codex can access on your machine. If a connector is not available, Codex will still help you with pasted emails and written drafts.
- Zeffy → QuickBooks is mostly done in the **browser** (Zeffy’s own settings). Codex will walk you through clicks; you do them.
- Never put API keys or passwords into the brain files. Password manager only.

---

## If something goes wrong

| What you see | What to try |
|--------------|-------------|
| `command not found: codex` | Step 2 install again; close Terminal and open a new window |
| `$life-ops-brain` does nothing | Type `Set up my life ops brain` instead |
| Skill not found | Repeat Step 5; confirm `SKILL.md` exists with the check command |
| Login / auth errors | Run `codex login` again |
| Afraid you broke something | Stop. Nothing here deletes your photos or bank account. Message Joe with the error text |

---

## Cheat sheet (after you have done this once)

**Mac — every day:**

```bash
cd ~/my-life-ops
codex
```

**Windows — every day:**

```text
cd %USERPROFILE%\my-life-ops
codex
```

**Run the setup skill again / resume:**

```text
$life-ops-brain
```

or

```text
Continue life ops setup
```

---

## Links

- Download package: https://github.com/joeprosynergy/life-ops-brain/archive/refs/heads/main.zip  
- Project page: https://github.com/joeprosynergy/life-ops-brain  
- This beginner guide (same repo): open `CODEX-FOR-BEGINNERS.md` after you unzip  

Questions → reply to Joe at joe@plyntr.com with the step number and the exact error message.
