# sskills

Sunan skills: personal coding-agent skills for Codex and Claude

Adapted from [mattpocock/skills](https://github.com/mattpocock/skills)

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

## Notes

- Skills live in `skills/`
- Codex metadata lives in `skills/*/agents/openai.yaml`
- Claude plugin metadata lives in `.claude-plugin/plugin.json`
- `.stow-local-ignore` keeps this submodule from being linked by `stow */` ([Stow ignore docs](https://www.gnu.org/software/stow/manual/stow.html#Types-And-Syntax-Of-Ignore-Lists))
