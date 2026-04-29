# On My SDD

Spec-Driven Development skill suite — combining OpenSpec (specification) and Superpowers (execution discipline) in a single installable skill.

## Installation

### Claude Code

```bash
npx skills add https://github.com/9Ashwin/on-my-sdd.git --skill sdd-workflow
```

Or install the full plugin:

```bash
/plugin install https://github.com/9Ashwin/on-my-sdd.git
```

### Codex

```bash
git clone https://github.com/9Ashwin/on-my-sdd.git ~/.codex/on-my-sdd
mkdir -p ~/.agents/skills
ln -s ~/.codex/on-my-sdd/skills ~/.agents/skills/on-my-sdd
```

See [Codex Install Guide](.codex/INSTALL.md) for details.

## What's Included

A single `sdd-workflow` skill that handles the entire SDD pipeline:

| Phase | Tool | Description |
|-------|------|-------------|
| **Classify** | Boundedness Check | Is the request a one-line fix? Bug? Clearly bounded feature? Fuzzy greenfield task? |
| **Explore** | `/opsx:explore` | Read code, build context for unfamiliar codebases |
| **Design** | `superpowers:brainstorming` | Socratic design for fuzzy tasks — compare approaches, define scope |
| **Specify** | `/opsx:propose` | Generate 4 artifacts: proposal.md + specs/ + design.md + tasks.md |
| **Review** | `reference/sdd-review-specs.md` | Tier-based review gate — validate scope, completeness, design, executability |
| **Plan** | `superpowers:writing-plans` | Refine tasks.md into 2-5 minute bite-sized subtasks |
| **Implement** | `/opsx:apply` + TDD | RED → GREEN → REFACTOR per task |
| **Archive** | `/opsx:archive` | Delta merge specs, move change to archive/ |

## Directory Structure

```
skills/sdd-workflow/
├── SKILL.md                         ← Routing, Boundedness Check, pipeline orchestration
└── reference/
    └── sdd-review-specs.md          ← Review checklists, red flags, tier-based gate
```

## Quick Reference

```
Fuzzy request ("add collaboration", "improve the app")
    → Boundedness Check → NOT bounded
    → /opsx:explore (read code) → re-check
    → superpowers:brainstorming (design)
    → /opsx:propose (specify)
    → review (reference/sdd-review-specs.md)
    → writing-plans → /opsx:apply + TDD → /opsx:archive

Clear request ("add DELETE /tasks/{id}")
    → Boundedness Check → IS bounded
    → /opsx:propose (specify)
    → review → writing-plans → implement → archive
```

[中文文档](README.md)

## License

MIT
