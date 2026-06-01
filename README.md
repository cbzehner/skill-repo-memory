# Repo Memory

Maintain lightweight memory for a repo without making every session carry it by default. The skill records runbooks, theories, learnings, and durable project facts.

## Use It For

- Writing down what future agents should remember
- Updating runbooks after a fix or investigation
- Separating durable repo facts from one-off session notes

## Install

Clone the repo and run the installer:

```bash
git clone https://github.com/cbzehner/skill-repo-memory.git
cd skill-repo-memory
./install.sh all
```

Install targets:

- `./install.sh claude` installs to `~/.claude/skills/repo-memory`
- `./install.sh codex` installs to `~/.codex/skills/repo-memory`
- `./install.sh agents` installs to `~/.agents/skills/repo-memory`
- `./install.sh opencode` installs to `~/.config/opencode/skills/repo-memory`
- `./install.sh all --copy` copies files instead of symlinking

Manual install works too: symlink or copy `skills/repo-memory` into your agent's skills directory.

## Agent Support

This repo uses the plain `skills/repo-memory/SKILL.md` layout. Claude Code and Codex also get small plugin manifests at `.claude-plugin/plugin.json` and `.codex-plugin/plugin.json`.

Other agents can read the same `SKILL.md` file. If a host does not support a frontmatter field or tool name, ignore that field and follow the workflow text.

## Layout

```text
.claude-plugin/plugin.json
.codex-plugin/plugin.json
install.sh
skills/repo-memory/SKILL.md
README.md
LICENSE
```

## Public Notes

These repos are public. Keep private repo names, secrets, customer data, raw logs, cookies, and absolute filesystem paths out of examples.

## License

MIT
