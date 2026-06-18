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
```

## Plugins

| Plugin | Description | Source |
|---|---|---|
| `mtk` | MTK (Moberg Toolkit) — compliance-first engineering workflows, review agents, and skills for .NET, Python, and TypeScript | [moberghr/mtk-agent-toolkit](https://github.com/moberghr/mtk-agent-toolkit) |
| `work-tree` | Skills for the work-tree CLI (`work` / `wd`) — interactive browser diff reviews | [moberghr/cli-work-tree-manager](https://github.com/moberghr/cli-work-tree-manager) |

This is an **aggregator** marketplace: the manifest here points at each plugin's own
repository, so plugin code continues to live and version in those repos.
