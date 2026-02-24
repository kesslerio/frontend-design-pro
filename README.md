# frontend-design-pro

Wrapper skill that composes two specialized skills into one-command frontend execution:
1. `design-taste-frontend` (strict guardrails layer)
2. `frontend-design-ultimate` (generation/workflow layer)

## Composition Model

`frontend-design-pro` is intentionally thin. It does not replace the source skills.
It enforces execution order:
1. Guardrails first (`design-taste-frontend`)
2. Generation second (`frontend-design-ultimate`)

This preserves strict anti-slop quality gates while still delivering fast, production-ready frontend output.

## Install All Three Skills

Install/copy full folders for each skill into your skills directory.

```bash
# Example skills directory (adjust for your setup)
SKILLS_DIR=~/.claude/skills

# 1) strict guardrails
cp -R /path/to/taste-skill "$SKILLS_DIR/taste-skill"

# 2) generator workflow
cp -R /path/to/frontend-design-ultimate "$SKILLS_DIR/frontend-design-ultimate"

# 3) wrapper skill
cp -R /path/to/frontend-design-pro "$SKILLS_DIR/frontend-design-pro"
```

Required skill names used by composition:
- `design-taste-frontend` (from `taste-skill/SKILL.md`)
- `frontend-design-ultimate`
- `frontend-design-pro`

## Usage

Prompt with the wrapper skill name and your product/UI requirements.

Example:

```text
Use frontend-design-pro to create a conversion-focused product landing page.
Apply strict taste guardrails first, then generate the full frontend implementation.
```
