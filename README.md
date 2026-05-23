# claude-tex-skills

A collection of [Claude Code](https://claude.com/claude-code) plugins
around TeX and LaTeX. The repository is structured as a Claude Code plugin
marketplace named `koppor-tex-skills`, so adding it once exposes every
plugin it contains.

## Prerequisites

- [Claude Code](https://claude.com/claude-code)
- Plugin-specific prerequisites (e.g. Docker for `compile-tex`)

## Install the marketplace

From within Claude Code:

```text
/plugin marketplace add koppor/claude-tex-skills
```

Then install any of the plugins below.

## Plugins

### `compile-tex`

Compile LaTeX, plain TeX, and ConTeXt documents to PDF using the
[Island of TeX](https://gitlab.com/islandoftex/images/texlive)
`texlive/texlive` Docker image — no local TeX Live installation required.
Defaults to LuaLaTeX as the modern engine; covers `latexmk`, `arara`,
`context`, TeX Live schemes, the weekly `latest` rebuild, the unprivileged
`texlive` user, and engine-log error extraction.

```text
/plugin install compile-tex@koppor-tex-skills
```

Skill source:
[`plugins/compile-tex/skills/compile-tex/SKILL.md`](plugins/compile-tex/skills/compile-tex/SKILL.md).
The SKILL.md itself is plain Markdown and agent-agnostic — it can be read
by any documentation-consuming agent, not only Claude Code.

### (Planned)

Future plugins may include language checks (LanguageTool / TeXtidote),
CI/CD helpers (GitHub Actions / GitLab CI snippets for `latexmk` builds),
LaTeX template generators (book, article, beamer, thesis), and similar
TeX-adjacent automation. Each will live under `plugins/<name>/` and be
listed in `.claude-plugin/marketplace.json`.

## Uninstall

```text
/plugin uninstall compile-tex@koppor-tex-skills
/plugin marketplace remove koppor-tex-skills
```

## Repository layout

```
.claude-plugin/marketplace.json        # marketplace registration
plugins/
  compile-tex/
    .claude-plugin/plugin.json         # plugin manifest
    skills/
      compile-tex/
        SKILL.md                       # the skill content
```

## License

[MIT](LICENSE). The Docker images referenced by `compile-tex` are produced
by the Island of TeX project and follow the licenses of the software they
bundle; see
[gitlab.com/islandoftex/images/texlive](https://gitlab.com/islandoftex/images/texlive).
