# Read the Room

A communication coaching skill for Claude that helps you choose the right approach before any important conversation. Works with both **Claude Cowork** (as an installable plugin with slash commands) and **Claude Code** (as a local skill).

**The problem:** Most people walk into conversations and choose their communication style based on what *they* want to say — not what the other person is able to hear. This plugin helps you read the room first.

---

## Who Made This

This plugin is built from an instructional method at [CDO School](https://thecdo.school). Founded by [Ryan Rumsey](https://www.ryanrumsey.com) (formerly a design leader at Apple, Electronic Arts, and USAA) CDO School gives designers the concrete skills to connect design to business, build genuine influence, and lead with confidence. Its curriculum has been developed and refined with 2,500+ designers from companies including Apple, Google, Airbnb, Netflix, Slack, and more.

- [CDO School](https://thecdo.school) — learn more about the boutique courses, workshops, and communities of practice for experienced designers and design leaders.

---

## How It Works

Most communication breaks down not because of *what* you said, but because of *when* and *how* you said it. Before choosing how to communicate, you need to read the person you're talking to and notice what kind of argument you're actually in, assess whether they can receive your message, and then choose an approach that meets them where they are.

This plugin uses a simple model based on two emotional states:

**C-States** (Calm, Curious, Courageous, Confident, Connected, Creative, Compassionate, Clear) describe someone who is grounded and receptive. They're open to data, logic, and structured thinking. This is when an analytical approach works.

**T-States** (Testy, Tense, Tired, Triggered, Timid, Threatened, Tormented, Troubled) describe someone who is emotionally activated or guarded. They need to feel heard before they can hear you. Leading with analysis here doesn't just fail, it often makes things worse.

Once you've read the room, the plugin helps you choose the right method and frame your argument accordingly.

| State | Signs | Approach |
|-------|-------|----------|
| **C-States** | Receptive, engaged, open | SCR Framework — lead with data |
| **T-States** | Defensive, stressed, guarded | Imago Dialogue — validate first |

---

## Commands

These work as slash commands in Cowork, or can be invoked by name in Claude Code.

| Command | What it does |
|---------|-------------|
| `/start` | Guided flow — describe your meeting, get a recommendation |
| `/readroom` | Quick C-state vs T-state assessment |
| `/validate` | Step-by-step Imago Dialogue prep |
| `/analyze` | Step-by-step SCR Framework prep |

---

## Installation

### Option A: Claude Cowork (Plugin)

**Requirements:** Claude desktop app — [claude.ai/download](https://claude.ai/download) with Cowork mode enabled.

1. Download this repository as a ZIP file (use the **Code → Download ZIP** button on GitHub) and extract it to your computer
2. Locate the **[read-the-room.plugin](./read-the-room.plugin)** file inside the extracted folder
3. Open the Claude desktop app and start a Cowork session
4. Look for the plugin icon in the toolbar or sidebar
5. Click **"Add Plugin"** or **"Install Plugin"** and select the file
6. Click **Accept** when prompted

> **Alternative:** You may be able to drag and drop the `.plugin` file directly into the Cowork window.

**Verify:** Type `/` in your Cowork session — you should see the commands appear.

---

### Option B: Claude Code (Local Skill)

**Requirements:** [Claude Code](https://claude.ai/download) installed and configured.

1. Clone or download this repository
2. Copy the `skills/communication-methods/` folder into your project (or a shared skills directory)
3. To enable slash commands, copy the contents of `commands/` into `.claude/commands/` in your project root
4. In a Claude Code session, reference the skill directly:

```
Please load the skill at skills/communication-methods/SKILL.md and help me prepare for a conversation.
```

Or use a slash command if you copied the commands folder:

```
/start
```

> **Note:** The `.plugin` file is Cowork-specific and is not needed for Claude Code.

---

## How to Use It

### Starting Fresh (Recommended)

Type `/start` and describe your upcoming conversation:

> **You:** `/start`
>
> **Claude:** "Tell me about the conversation you're preparing for — who are you meeting with, what do you need to communicate, and how have your recent interactions been?"
>
> **You:** "I need to ask my VP for headcount. She's been stressed about budget and pushed back on my last request."
>
> **Claude:** [Reads the room, recommends approach, walks you through preparation]

### Quick Assessment

Use `/readroom` when you just want to check whether to lead with validation or analysis.

### When You Already Know the Approach

- `/validate` — if they seem defensive, stressed, or under pressure
- `/analyze` — if they're open, calm, and ready to hear data

---

## Project Structure

```
read-the-room/
├── .claude-plugin/
│   └── plugin.json           # Plugin metadata (name, version, author)
├── commands/
│   ├── start.md              # /start — guided coaching flow
│   ├── readroom.md           # /readroom — quick C/T state assessment
│   ├── validate.md           # /validate — Imago Dialogue walkthrough
│   └── analyze.md            # /analyze — SCR Framework walkthrough
├── skills/
│   └── communication-methods/
│       ├── SKILL.md          # Skill entry point and instructions
│       └── references/
│           ├── frameworks.md # 8 C-states, 8 T-states, SCR, Imago Dialogue
│           └── voice.md      # Tone and response pattern guidelines
├── LICENSE                   # MIT License (code)
├── LICENSE-CC.md             # CC BY-SA 4.0 (content and frameworks)
├── README.md
└── read-the-room.plugin  # Installable plugin for Claude Cowork
```

---

## Skills

Skills are folders of instructions, scripts, and resources that Claude loads dynamically to improve performance on specialized tasks. Skills teach Claude how to complete specific tasks in a repeatable way, whether that's creating documents with your company's brand guidelines, analyzing data using your organization's specific workflows, or automating personal tasks.

For more information, check out:
- [What are skills?](https://support.claude.com/en/articles/12512176-what-are-skills)
- [Using skills in Claude](https://support.claude.com/en/articles/12512180-using-skills-in-claude)
- [How to create custom skills](https://support.claude.com/en/articles/12512198-creating-custom-skills)
- [Equipping agents for the real world with Agent Skills](https://anthropic.com/engineering/equipping-agents-for-the-real-world-with-agent-skills)

---

## Troubleshooting

**Cowork: Commands don't appear when I type /**
→ Make sure the plugin was fully installed and accepted. Try closing and reopening Cowork.

**Cowork: I don't see a plugin option**
→ Make sure you're in a Cowork session (not a regular Claude chat). The plugin system is Cowork-specific.

**Cowork: The plugin file won't open**
→ Don't try to unzip it manually — Cowork installs it directly.

**Claude Code: Slash commands aren't working**
→ Make sure you copied the `commands/` files into `.claude/commands/` in your project root, and that each file has the correct YAML frontmatter (`name` and `description` fields).

**Claude Code: Claude doesn't seem to know the frameworks**
→ Explicitly point Claude at the skill file: *"Please read skills/communication-methods/SKILL.md before we begin."*

---

## Changelog

**v0.1.0** — Initial public release. Includes `/start`, `/readroom`, `/validate`, `/analyze` commands; dual installation paths for Claude Cowork and Claude Code.

---

## Attribution & License

Built on lessons inside [CDO School](https://thecdo.school) by [Ryan Rumsey](https://www.ryanrumsey.com).
Copyright © 2026 [Second Wave Dive LLC](https://www.secondwavedive.com).

The content of this project (frameworks, reference materials, skill instructions) is licensed under [Creative Commons Attribution-ShareAlike 4.0 International](./LICENSE-CC.md).

The code (commands, plugin configuration) is licensed under the [MIT License](./LICENSE).
