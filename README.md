# Claude Skills

A personal collection of custom skills for [Claude.ai](https://claude.ai) — modular instruction sets that make Claude significantly better at specific tasks without repeating yourself every chat.

---

## What are skills?

Claude skills are reusable instruction files that you install once and Claude automatically applies whenever relevant. Think of them as persistent context: instead of explaining your workflow, preferences, or domain knowledge at the start of every conversation, you define it once in a skill and Claude just knows.

Each skill is a `SKILL.md` file with a name, a trigger description, and detailed instructions. Claude reads the description to decide when to activate it, then follows the instructions to shape its response.

---

## Skills in this repo

### `chat-summarizer`
Generates a compact, LLM-readable handoff summary of your current chat so you can continue seamlessly in a new conversation. Captures your goal, tech stack, what was done, problems and solutions, current stage, and next steps — everything a new Claude instance needs to pick up exactly where you left off.

**Trigger:** type `/chat-summarizer` in any chat.

### `unity-companion`
A senior Unity mentor that answers C# and Unity 2022.3 LTS questions the way a professional game developer would. Covers MonoBehaviour lifecycle, physics, animations, performance optimization, editor tools, and general C# patterns. Every code sample follows production-grade standards: cached references, proper lifecycle methods, object pooling, Observer pattern, and no runtime `Find()` calls.

**Trigger:** any Unity or C# question, or type `/unity-companion`.

---

## Installation

1. Download the `.skill` file for the skill you want from [Releases](../../releases.
2. Go to **Claude.ai → Settings → Skills**.
3. Click **Install skill** and upload the file.

Done. Claude will automatically use the skill whenever it's relevant.

---

## Creating your own skill

Skills are just Markdown files. Here is the minimal structure:

```
my-skill/
└── SKILL.md
```

A `SKILL.md` looks like this:

```markdown
---
name: my-skill
description: >
  What this skill does and when Claude should use it.
  Be specific about trigger phrases and contexts.
---

# My Skill

Instructions for Claude go here. Write as if briefing
a smart colleague — context, rules, output format, tone.
```

The description is the most important part. Claude reads it to decide whether to activate the skill. Be explicit about triggers: list example phrases, contexts, and keywords. If you want a single command word like `composer` to always fire it, say so directly in the description.

Once your `SKILL.md` is ready, package it into a `.skill` file using the [skill-creator](https://claude.ai) skill inside Claude, then install it via Settings.

---

## Repo structure

```
claude-skills/
├── README.md
├── skills/
│   ├── chat-summarizer/
│   │   └── SKILL.md
│   └── unity-companion/
│       └── SKILL.md
```
