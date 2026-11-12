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

### Claude app

1. Download [paper-page.zip](https://github.com/learnaiwithhugo/paper-page-skill/releases/latest/download/paper-page.zip).
2. In Claude, go to **Customize > Skills**.
3. Click **+**, then **Create skill**, then **Upload a skill**.
4. Pick `paper-page.zip`.

Use it in the Claude desktop app, where Paper connects. Skills you add here also show up in Claude Code when you sign in with the same account.

### Claude Code

Paste this into Claude Code:

```
Install the paper-page skill from https://github.com/learnaiwithhugo/paper-page-skill into ~/.claude/skills/paper-page
```

Or run this in your terminal:

```bash
git clone https://github.com/learnaiwithhugo/paper-page-skill.git /tmp/paper-page-skill && mkdir -p ~/.claude/skills && cp -R /tmp/paper-page-skill/paper-page ~/.claude/skills/
```

Restart Claude Code, then type `/paper-page`.
