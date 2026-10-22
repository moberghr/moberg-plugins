# Moberg Plugins

Single Claude Code marketplace for Moberg d.o.o. plugins.

## Install

```
/plugin marketplace add moberghr/moberg-plugins
```

Then install whichever plugins you want:

```
/plugin install mtk@moberg-plugins
/plugin install work-tree@moberg-plugins
/plugin install docume@moberg-plugins
```

## Plugins

| Plugin | Description | Source |
|---|---|---|
| `mtk` | MTK (Moberg Toolkit) — compliance-first engineering workflows, review agents, and skills for .NET, Python, and TypeScript | [moberghr/mtk-agent-toolkit](https://github.com/moberghr/mtk-agent-toolkit) |
| `work-tree` | Skills for the work-tree CLI (`work` / `wd`) — interactive browser diff reviews | [moberghr/cli-work-tree-manager](https://github.com/moberghr/cli-work-tree-manager) |
| `docume` | DocuMe's generative tier — `/docs-loop`, `/docs-processes`, `/docs-refresh`, `/docs-feedback` write and correct a repo-based wiki published to Confluence; every skill's output is a PR | [moberghr/docu-me](https://github.com/moberghr/docu-me) (`plugin/`) |

This is an **aggregator** marketplace: the manifest here points at each plugin's own
repository, so plugin code continues to live and version in those repos.

`mtk` is pinned to the `plugin` branch (`ref`), the slim runtime-only tree that the MTK release
workflow rebuilds from each release tag. Installs therefore move only on a tagged release, never on
an unreleased `main` commit. Its entry carries no `version` field: `.claude-plugin/plugin.json` on that
branch is the single copy.

`docume` is pinned to a release tag (`ref`) rather than a branch, because DocuMe releases its CLI,
library and plugin off one version — bump the `ref` to each new `vX.Y.Z`. Its entry carries no
`version` field on purpose: `plugin/.claude-plugin/plugin.json` in that repo is the single copy, and a
duplicate here is a number that goes stale silently.

`work-tree` tracks the default branch of its repo and, like the others, carries no `version` field:
`plugins/work-tree/.claude-plugin/plugin.json` there is the single copy. Bump it there to ship an update.
