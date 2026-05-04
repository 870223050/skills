---
name: godot-project-bootstrap
description: 设计并稳定 Godot 4 项目的脚手架、目录结构、功能边界以及 Codex 协作规则。适用于新建 Godot 项目模板、规划可复用文件夹结构、拆分核心系统与功能模块，或约束 Codex 以局部修改代替大范围重构的场景。
---

# Godot 项目脚手架

## 概述

使用这个 skill 来搭建一个适合 AI 协作开发、结构稳定的 Godot 项目。核心层保持精简，把玩法逻辑尽量收敛到各自功能目录里，并默认采用兼容性优先的重构方式。

## 工作流程

1. 先判断当前请求属于项目初始化、功能开发，还是重构整理。
2. 参考 [references/project-layout.md](references/project-layout.md) 确定本次改动的归属层。
3. 尽量把改动限制在最小的功能目录或共享层中完成。
4. 如果共享接口必须变更，先保留兼容路径，再移除旧实现。
5. 如果改动涉及启动代码、autoload 或共享 API，要通过场景启动或 smoke test 做基本验证。

## 默认规则

- `autoload/` 保持极小，只放真正全局的内容。
- 可复用的运行时系统放在 `core/`。
- 某个功能专属的场景、UI、脚本、数据和测试，放在 `features/<feature>/`。
- 导入的美术、音频、字体等资源放在 `assets/`。
- 可跨功能复用的 UI 控件放在 `ui/`。
- 只有当一段代码被多个功能复用时，才提升到共享层。

## 重构策略

- 优先做局部修改，不做全项目重写。
- 优先使用适配器、包装层和信号，不要轻易做大面积继承改造或重命名。
- 除非需求明确要求，否则不要移动或重命名公共场景、autoload 或被广泛使用的 API。

## 参考资料

- [项目结构](references/project-layout.md)
- [Codex 协作规则](references/codex-collab.md)
