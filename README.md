# AI/UX Skills

> AI coding skills for designers. Accessibility, UX writing, design critique, and data visualization—install once, your AI uses them automatically. Works with Cursor, Claude Code, VS Code Copilot, and Codex.

Curated AI coding skills for UX and product designers. Install once, and your AI activates them automatically when relevant.

## Available Skills

| Skill | Description | Best For |
|-------|-------------|----------|
| [Accessibility Expert](./skills/accessibility-expert/) | Build inclusive interfaces with WCAG compliance, screen reader support, and keyboard navigation | UX, UI, Product, Frontend |
| [UX Writing](./skills/ux-writing/) | Write effective microcopy: button labels, error messages, empty states, onboarding, and tooltips | UX Writers, Content, Product |
| [Design Critique](./skills/design-critique/) | Structured framework for giving and receiving design feedback | Product, UX, UI, Visual |
| [D3.js Visualization](./skills/d3-visualization/) | Create interactive data visualizations, charts, and network diagrams | Visual, Data, Product |

## Installation

### Cursor

```bash
# Project-level (recommended)
mkdir -p .cursor/skills
cp -r skills/* .cursor/skills/

# Or global
cp -r skills/* ~/.cursor/skills/
```

[Official Cursor Skills Docs →](https://cursor.com/docs/context/skills)

### Claude Code

```bash
# User-level
cp -r skills/* ~/.claude/skills/

# Or project-level
mkdir -p .claude/skills
cp -r skills/* .claude/skills/
```

[Official Claude Code Skills Docs →](https://code.claude.com/docs/en/skills)

### VS Code (GitHub Copilot)

> ⚠️ Preview feature: Enable `chat.useAgentSkills` in settings first

```bash
# Project-level
mkdir -p .github/skills
cp -r skills/* .github/skills/

# Or global
cp -r skills/* ~/.copilot/skills/
```

[Official VS Code Agent Skills Docs →](https://code.visualstudio.com/docs/copilot/customization/agent-skills)

### OpenAI Codex

```bash
# User-level
cp -r skills/* ~/.codex/skills/

# Or project-level
mkdir -p .codex/skills
cp -r skills/* .codex/skills/
```

Use `$` to mention skills, or `/skills` to browse.

[Official OpenAI Codex Skills Docs →](https://developers.openai.com/codex/skills/)

### Quick Use (Any AI)

Copy the content from any `SKILL.md` file and paste it into your AI chat:

```
Here's a skill I want you to follow:

[paste SKILL.md content]

Now help me [your task]
```

## What are Skills?

Skills are `SKILL.md` files that teach AI coding agents specialized abilities. Unlike prompts (which you use once), skills are persistent—install them once, and your AI automatically activates them when relevant to your task.

## Contributing

Have a skill to share? Open a PR! Skills should be:

- **Focused**: One clear purpose
- **Actionable**: Specific guidance, not just concepts
- **Designer-friendly**: Relevant to UX, product, or visual design work

## License

MIT

---

Built by [AI/UX Playground](https://aidesignpatterns.com)
