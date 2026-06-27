# sskills

`sskills` stands for Sunan skills: a small, personal skill set for coding agents.

The skills are adapted from [mattpocock/skills](https://github.com/mattpocock/skills) and kept in one shared source tree for Codex and Claude.

## Layout

- `skills/` contains the shared skill source tree
- `.claude-plugin/plugin.json` exposes the skills as a Claude plugin
- `skills/*/agents/openai.yaml` contains Codex-specific metadata where needed
- `disable-model-invocation: true` in `SKILL.md` is kept for Claude explicit-only skills

## Invocation Policy

Explicit-only skills use both agent-specific mechanisms:

```yaml
# Claude, in SKILL.md frontmatter
disable-model-invocation: true
```

```yaml
# Codex, in agents/openai.yaml
policy:
  allow_implicit_invocation: false
```

Model-invoked skills omit both restrictions.

## Skills

User-invoked:

- `ask-skills`
- `grill-me`
- `grill-with-docs`
- `handoff`
- `implement`
- `improve-codebase-architecture`
- `prototype`
- `setup-agent-skills`
- `to-issues`
- `to-prd`
- `triage`
- `writing-great-skills`

Model-invoked:

- `codebase-design`
- `diagnosing-bugs`
- `domain-modeling`
- `grilling`
- `resolving-merge-conflicts`
- `review`
- `tdd`

## Dotfiles

This directory is intentionally a dotfiles submodule, not a stow package. Its `.stow-local-ignore` file makes `stow sskills` a no-op while keeping `sskills/` visible at the dotfiles root.

GNU Stow supports package-local ignore lists with `.stow-local-ignore`; see the Stow manual's ignore list docs: <https://www.gnu.org/software/stow/manual/stow.html#Types-And-Syntax-Of-Ignore-Lists>.

After stowing dotfiles, link these skills into the live agent directories:

```sh
./sskills/scripts/link-skills.sh
```
