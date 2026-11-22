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

## Skills

| Skill | Purpose |
| --- | --- |
| [`ahmed-ui-ux-pro-max`](ahmed-ui-ux-pro-max/SKILL.md) | Distinctive UI/UX design and implementation, including Arabic and RTL interfaces. |
| [`ahmed-laravel-modular-backend`](ahmed-laravel-modular-backend/SKILL.md) | Modular Laravel backend engineering grounded in project-matched official documentation, with a multi-agent workflow for non-trivial tasks when supported by the host. |

Skills use the open Agent Skills format and are designed for compatible coding agents. Agent-specific features may vary.
