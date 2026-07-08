# sskills

Sunan skills: personal coding-agent skills for Codex and Claude

Adapted from [mattpocock/skills](https://github.com/mattpocock/skills) (tracks [v1.1.0](https://github.com/mattpocock/skills/releases/tag/v1.1.0))

## Setup

Managed from the dotfiles repo as a submodule at `sskills`:

```sh
git submodule update --init sskills
./sskills/scripts/link-skills.sh
```

Standalone install:

```sh
git clone git@github.com:sunanmau5/sskills.git ~/src/sskills
~/src/sskills/scripts/link-skills.sh
```

## Typical workflow

```text
wayfinder -> to-spec -> to-tickets -> implement -> code-review
```

1. `/wayfinder` to chart the effort as a map of tickets. For plans small enough for one session, `/grill-me` or `/grill-with-docs` instead
2. `/to-spec` to turn the conversation into a spec
3. `/to-tickets` to break the spec into tracer-bullet tickets
4. `/implement` to build each ticket, with `/tdd` for test-first work
5. `/code-review` to review the changes since a fixed point

Run `/setup-agent-skills` once per repo before first use of the tracker-backed skills.

## Notes

- Skills live in `skills/`
- Codex metadata lives in `skills/*/agents/openai.yaml`
- Claude plugin metadata lives in `.claude-plugin/plugin.json`
- `.stow-local-ignore` keeps this submodule from being linked by `stow */` ([Stow ignore docs](https://www.gnu.org/software/stow/manual/stow.html#Types-And-Syntax-Of-Ignore-Lists))
