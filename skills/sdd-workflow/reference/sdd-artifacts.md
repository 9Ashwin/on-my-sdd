# SDD Artifacts & Commands

## Artifact Ownership

OpenSpec and Superpowers each produce plan-like files — they serve different roles and both belong in `openspec/changes/<name>/`:

| Artifact | Owner | Granularity | Purpose | Example |
|----------|-------|-------------|---------|---------|
| `tasks.md` | OpenSpec (`/opsx:propose`) | Coarse checkbox items | WHAT to implement | `- [ ] Implement Store interface` |
| `plan.md` | Superpowers (`writing-plans`) | 2-5min subtasks | HOW to implement | `1. Define Store interface in store/store.go (2 min)` |

**Rule:** `plan.md` refines `tasks.md` — it does NOT replace it. Both coexist in the same change directory. `writing-plans` reads `tasks.md` as input and outputs `plan.md` with detailed steps, file paths, and test names.

```
openspec/changes/<name>/
├── proposal.md    ← OpenSpec: why + scope boundary
├── specs/         ← OpenSpec: behavior delta specs
├── design.md      ← OpenSpec: technical decisions
├── tasks.md       ← OpenSpec: coarse implementation checklist (WHAT)
└── plan.md        ← Superpowers: refined subtasks (HOW)
```

`docs/superpowers/specs/` and `docs/superpowers/plans/` are legacy brainstorming output paths — they are NOT used by this workflow. All artifacts live under `openspec/changes/<name>/`.

## OpenSpec Commands Used

These 5 commands drive the SDD pipeline. The other opsx commands (`new`, `continue`, `ff`, `sync`, `bulk-archive`, `onboard`) are available but outside this skill's scope.

| Command | Used in Tier | Purpose |
|---------|-------------|---------|
| `/opsx:propose` | Lite, Standard, Full | Generate 4 artifacts in one step |
| `/opsx:explore` | Fuzzy → Full | Read code, build context before brainstorming |
| `/opsx:apply` | Lite, Standard, Full | Implement tasks from tasks.md |
| `/opsx:verify` | Standard, Full | 3-dimension validation before archive |
| `/opsx:archive` | Lite, Standard, Full | Delta merge + move to archive/ |
