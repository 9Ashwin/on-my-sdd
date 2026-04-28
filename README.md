# On My SDD

OpenSpec + Superpowers all-in-one Claude Code Skills — the complete SDD toolchain in one package.

## Installation

### Claude Code

```bash
npx skills add https://github.com/9Ashwin/on-my-sdd.git --skill sdd-workflow
npx skills add https://github.com/9Ashwin/on-my-sdd.git --skill sdd-review-specs
```

### Codex

```bash
git clone https://github.com/9Ashwin/on-my-sdd.git ~/.codex/on-my-sdd
mkdir -p ~/.agents/skills
ln -s ~/.codex/on-my-sdd/skills ~/.agents/skills/on-my-sdd
```

详见 [Codex 安装指南](.codex/INSTALL.md)

## Available Skills

| Skill | Description |
|-------|-------------|
| [sdd-workflow](skills/sdd-workflow/) | Spec-driven development router — classifies requests, detects current project phase, and routes to the right specification or execution tool |
| [sdd-review-specs](skills/sdd-review-specs/) | Structured review gate for OpenSpec artifacts before implementation begins — validates proposal scope, spec completeness, design decisions, and task executability |

## SDD Workflow

```
User request → sdd-workflow (classify & route) → /opsx:propose → sdd-review-specs → writing-plans → /opsx:apply → /opsx:archive
```

## License

MIT
