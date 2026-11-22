# Ahmed's Agent Skills

Personal Agent Skills for UI/UX design and Laravel backend engineering. Each skill is independent and can be installed on its own.

## Install one skill globally

The `skills` CLI installs the selected skill to the coding agents you choose. Use `--agent '*'` to install it for every detected agent, including Codex and Antigravity:

```bash
npx skills add ahmed-alsarem/skills --skill ahmed-ui-ux-pro-max --agent '*' --global --yes
```

```bash
npx skills add ahmed-alsarem/skills --skill ahmed-laravel-modular-backend --agent '*' --global --yes
```

Install both skills in one command:

```bash
npx skills add ahmed-alsarem/skills \
  --skill ahmed-ui-ux-pro-max \
  --skill ahmed-laravel-modular-backend \
  --agent '*' --global --yes
```

The CLI follows each agent's global skill directory. Antigravity's global location is `~/.gemini/config/skills/`; Codex uses `~/.agents/skills/`. To install for only one agent, replace `--agent '*'` with its name, such as `--agent antigravity` or `--agent codex`.

## Skills

| Skill | Purpose |
| --- | --- |
| [`ahmed-ui-ux-pro-max`](ahmed-ui-ux-pro-max/SKILL.md) | Distinctive UI/UX design and implementation, including Arabic and RTL interfaces. |
| [`ahmed-laravel-modular-backend`](ahmed-laravel-modular-backend/SKILL.md) | Modular Laravel backend engineering grounded in project-matched official documentation, with a multi-agent workflow for non-trivial tasks when supported by the host. |

Skills use the open Agent Skills format and are designed for compatible coding agents. Agent-specific features may vary.
