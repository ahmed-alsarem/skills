# Ahmed's Agent Skills

Personal Agent Skills for UI/UX design and Laravel backend engineering. Each skill is independent and can be installed on its own.

## Install one skill and choose your agent

Run the command without `--agent` or `--yes`. The `skills` CLI will let you choose which detected coding agent or agents should receive the skill. `--global` makes it available across projects for the selected agent:

```bash
npx skills add ahmed-alsarem/skills --skill ahmed-ui-ux-pro-max --global
```

```bash
npx skills add ahmed-alsarem/skills --skill ahmed-laravel-modular-backend --global
```

To choose multiple agents, select each one in the CLI prompt. To install both skills and choose the target agents:

```bash
npx skills add ahmed-alsarem/skills \
  --skill ahmed-ui-ux-pro-max \
  --skill ahmed-laravel-modular-backend \
  --global
```

The CLI follows each agent's global skill directory. Antigravity's global location is `~/.gemini/config/skills/`; Codex uses `~/.agents/skills/`. If Antigravity is not listed in the prompt, install it explicitly with `--agent antigravity`. Other supported targets can be selected by name, such as `--agent codex` or `--agent claude-code`.

For unattended setup, you can bypass the selection prompt with `--agent '*' --yes`; this installs to all detected agents.

## Antigravity plugin: Laravel icon and agent roles

Antigravity skills do not have their own custom icons. This repository also includes an Antigravity plugin with a Laravel-inspired icon, the Laravel backend skill, and read-only documentation, architecture, and security subagents. Install it with:

```bash
agy plugin install https://github.com/ahmed-alsarem/skills
```

To run Antigravity's real shared-board Swarm, start the task with `/swarm` and ask it to use the Laravel backend skill. The plugin includes a suggested prompt that starts this workflow. The skill guides the workers; Antigravity's built-in `/swarm` command runs the orchestration.

## Skills

| Skill | Purpose |
| --- | --- |
| [`ahmed-ui-ux-pro-max`](ahmed-ui-ux-pro-max/SKILL.md) | Distinctive UI/UX design and implementation, including Arabic and RTL interfaces. |
| [`ahmed-laravel-modular-backend`](ahmed-laravel-modular-backend/SKILL.md) | Modular Laravel backend engineering with version-matched documentation, multi-agent workflow, and focused security audits. |

Skills use the open Agent Skills format and are designed for compatible coding agents. Agent-specific features may vary.
