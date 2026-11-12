# paper-page

A Claude skill for designing a web page in [Paper](https://paper.design) with Claude, one section at a time.

Made by Hugo Manning ([learnaiwithhugo.com](https://learnaiwithhugo.com)).

## What it does

Type `/paper-page` (or "let's design my homepage in Paper") and Claude walks you through 5 steps:

1. **Context.** Claude reads what you've shared and asks only what's missing.
2. **Why, who, which sections.** Who lands on the page, its one job, and the shortest list of sections.
3. **Lock the words.** Every section's copy written and approved before anything is designed.
4. **Build one section at a time.** Claude designs each section in Paper and checks it before showing you.
5. **Pick and tweak.** You pick, change or send back each section, then move on to the next.

Nothing moves to the next step until you say yes.

## You'll need

Paper Desktop connected to Claude. Download it at [paper.design/downloads](https://paper.design/downloads), open a file, then in the MCP panel on the right click **Add to Claude**. Paper's guide: [paper.design/docs/mcp](https://paper.design/docs/mcp).

## Install

Pick one: the plugin (easy updates) or just the skill.

### Option 1: The plugin

**Claude app** (paid plans)

1. Open **Customize** in the left sidebar, then the **Plugins** tab.
2. Click **Add**, then **Add marketplace**.
3. Choose **Add from a repository** and enter `learnaiwithhugo/paper-page-skill`.
4. Find **paper-page** and click **Add**.

**Claude Code**

Type this in Claude Code:

```
/plugin install paper-page --marketplace learnaiwithhugo/paper-page-skill
```

### Option 2: Just the skill

**Claude app**

1. Download [paper-page.zip](https://github.com/learnaiwithhugo/paper-page-skill/releases/latest/download/paper-page.zip).
2. Open **Customize > Skills**.
3. Click **+**, then **Create skill**, then **Upload a skill**.
4. Pick `paper-page.zip`.

**Claude Code**

Run this in your terminal:

```bash
git clone https://github.com/learnaiwithhugo/paper-page-skill.git /tmp/paper-page-skill && mkdir -p ~/.claude/skills && cp -R /tmp/paper-page-skill/skills/paper-page ~/.claude/skills/
```

### Then

Use it in the Claude desktop app or Claude Code, where Paper connects. Anything you add in the Claude app also shows up in Claude Code when you sign in with the same account. Start a new chat and type `/paper-page`.
