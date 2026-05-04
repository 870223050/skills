# Codex Skills

这个仓库用于托管我维护的自定义 Codex skills。

当前仓库只跟踪自定义 skill，不包含 Codex 自带的系统 skill 和运行时 skill：

- `.system/`
- `codex-primary-runtime/`

## 已收录 Skills

### `game-ui-concept-pack`

根据游戏 UI 需求说明和参考图生成概念图，并额外产出无字纯美术版本。

### `godot-project-bootstrap`

为 Godot 4 项目规划稳定的目录结构、功能边界和 Codex 协作规则。

### `godot-tscn-ui-rules`

约束 Godot `.tscn` UI 场景的结构、命名和拆分方式，便于持续生成和维护界面。

### `project-skeleton-generator`

根据需求分析文档生成项目目录结构、UI 场景、UI 场景脚本，以及带简短注释的游戏逻辑接口骨架。

## 目录说明

```text
skills/
  game-ui-concept-pack/
  godot-project-bootstrap/
  godot-tscn-ui-rules/
  project-skeleton-generator/
```

## 使用方式

1. 将 skill 目录放入 `C:\Users\lee2813\.codex\skills`。
2. 在 Codex 对话中直接显式调用对应 skill。

示例：

```text
使用 $project-skeleton-generator，根据需求分析文档生成项目目录、UI 场景和逻辑接口骨架。
```

## 维护约定

- 新增自定义 skill 时，默认提交对应目录、`SKILL.md`、`agents/openai.yaml` 和所需 `references/`。
- 保持 skill 名称使用 `hyphen-case`。
- 文本文件统一使用 LF 换行。
