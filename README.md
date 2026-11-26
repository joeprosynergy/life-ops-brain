# Life Ops Brain setup skill

> **The brain itself has moved to a template: https://github.com/Plyntr-LLC/life-ops-brain-template**
>
> That template is now the Life Ops Brain. It has safety guards built in (sends wait for the word "send", changes wait for "approve", passwords and keys stay out of reach) for Claude Code, Codex, Grok and Antigravity. Start there.

This repo keeps the **setup skill** (`life-ops-brain/`). The skill gets the template onto your computer, runs its setup, and can add optional areas for a ministry or nonprofit (donors, campaigns, Zeffy, QuickBooks), a business, or family.

## Quickest start

**Terminal (Claude Code, Codex, Grok, Antigravity):**

```bash
git clone https://github.com/Plyntr-LLC/life-ops-brain-template.git my-brain
cd my-brain && node setup.cjs
```

Then open the folder in your AI tool and say **/start**.

**Claude or ChatGPT desktop app:** download the [template zip](https://github.com/Plyntr-LLC/life-ops-brain-template/archive/refs/heads/main.zip), unzip it, open the folder in the app and say **/start**.

## Want the add-on areas too?

Install this skill: download [this repo's zip](https://github.com/joeprosynergy/life-ops-brain/archive/refs/heads/main.zip), unzip it, and add the `life-ops-brain` folder as a skill (Claude desktop: Settings, Skills. Codex: copy it to `~/.agents/skills/`). Then say **/life-ops-brain** or "set up my life ops brain".

ChatGPT desktop, click by click: [CODEX-FOR-BEGINNERS.md](./CODEX-FOR-BEGINNERS.md).

## Privacy

- Your brain stays on your computer. Nothing is uploaded.
- Never put passwords or API keys in the brain folder.
- Family notes stay under `personal/family/` and are not used for donor or client writing unless you ask.
- Outgoing messages are drafts until you say **send**.

## Support

If something fails, tell the person who shared this with you which step broke.
