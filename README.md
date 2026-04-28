# Oh My Spec

Claude Code Skills repository for spec-driven development — OpenSpec + Superpowers workflow tools.

## Installation

```bash
npx skills add https://github.com/9Ashwin/oh-my-spec.git --skill sdd-workflow
npx skills add https://github.com/9Ashwin/oh-my-spec.git --skill sdd-review-specs
```

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
