# Visualize skill repository

This repository contains the Codex `visualize` skill. The distributable skill lives in `skills/visualize/`.

## Repository structure

- `skills/visualize/SKILL.md`: core instructions loaded by Codex
- `skills/visualize/agents/openai.yaml`: Codex UI metadata
- `skills/visualize/references/`: detailed specifications loaded progressively
- `examples/`: checked-in example HTML outputs
- `eval/`: evaluation pipeline and historical results

## Editing the skill

- Keep YAML frontmatter limited to `name` and `description`.
- Keep trigger conditions in the frontmatter description.
- Put detailed patterns in `references/` and link them directly from `SKILL.md`.
- Start generated examples from `skills/visualize/references/skeleton.md`.
- Preserve single-file HTML output, class-based themes, accessibility, and responsive behavior.
- Use `var` for top-level JavaScript variables to avoid temporal-dead-zone failures.

## Validation

Run the Codex skill validator after editing skill metadata or instructions:

```bash
python3 "${CODEX_HOME:-$HOME/.codex}/skills/.system/skill-creator/scripts/quick_validate.py" skills/visualize
```

For visualization regressions, run the local evaluation pipeline documented in `eval/EVAL.md`.
