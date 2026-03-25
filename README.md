# frontend-design-pro

Wrapper skill that composes two specialized skills into one-command frontend execution:
1. `design-taste-frontend` (strict guardrails layer)
2. `frontend-design-ultimate` (generation/workflow layer)

## Dependencies

Both skills must be installed before this skill will work. Install them first:

| Skill | Frontmatter name | Source repo |
|-------|-----------------|-------------|
| Taste guardrails | `design-taste-frontend` | [kesslerio/taste-skill](https://github.com/kesslerio/taste-skill) |
| Generator workflow | `frontend-design-ultimate` | [kesslerio/ultimate-frontend-design-openclaw-skill](https://github.com/kesslerio/ultimate-frontend-design-openclaw-skill) |

### Install by tool

**Claude Code**
```bash
# design-taste-frontend (symlink the skills/taste-skill/ subdir)
git clone https://github.com/kesslerio/taste-skill.git ~/code/taste-skill
ln -s ~/code/taste-skill/skills/taste-skill ~/.claude/skills/design-taste-frontend

# frontend-design-ultimate (already present if using compound-engineering-plugin)
# otherwise clone and symlink the repo root to ~/.claude/skills/frontend-design-ultimate
```

**Codex & Windsurf** (via [compound-engineering-plugin](https://github.com/EveryInc/compound-engineering-plugin))
```bash
# After compound-engineering-plugin is installed and ~/.claude/skills/ is set up:
compound-plugin sync --target codex
compound-plugin sync --target windsurf
# Both skills sync automatically — no manual steps needed.
```

**OpenClaw**
```bash
# design-taste-frontend
git clone https://github.com/kesslerio/taste-skill.git /tmp/taste-skill
cp -R /tmp/taste-skill/skills/taste-skill ~/.openclaw/extensions/design-taste-frontend

# frontend-design-ultimate
git clone https://github.com/kesslerio/ultimate-frontend-design-openclaw-skill.git /tmp/ultimate
cp -R /tmp/ultimate ~/.openclaw/extensions/frontend-design-ultimate
```

Then install this wrapper skill the same way (symlink or copy its repo root to your tool's skills/extensions directory).

## Composition Model

`frontend-design-pro` is intentionally thin. It does not replace the source skills.
It enforces execution order:
1. Guardrails first (`design-taste-frontend`)
2. Generation second (`frontend-design-ultimate`)

This preserves strict anti-slop quality gates while still delivering fast, production-ready frontend output.

## Usage

Prompt with the wrapper skill name and your product/UI requirements.

```text
Use frontend-design-pro to create a conversion-focused product landing page.
Apply strict taste guardrails first, then generate the full frontend implementation.
```
