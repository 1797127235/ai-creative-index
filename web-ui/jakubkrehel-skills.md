# jakubkrehel/skills

[← 返回网页与 UI 设计](./README.md) · [仓库](https://github.com/jakubkrehel/skills) · [Interfaces](https://interfaces.dev/)

`MIT` · 界面工艺 Agent Skills 合集 · 排版 / 色 / 无障碍 / 布局 / 文案 / 还原 / 审查

## 它是什么

[Jakub Krehel](https://jakub.kr/) 把自己在个人站和设计工程杂志 **Interfaces** 上写的那套界面知识，收成可给 coding agent 调用的 skills：不是「一个审美主题」，而是**按维度检查和改界面**。

```sh
npx skills add jakubkrehel/skills
```

Claude Code 插件：

```text
/plugin marketplace add jakubkrehel/skills
/plugin install interfaces@interfaces
```

## Skills 清单

| Skill | 干什么 |
|---|---|
| `better-interface` | 整屏/流程跨无障碍、布局、文案、排版、色、抛光，出一份排序报告 |
| `better-ui` | 圆角、光学对齐、阴影、图标态、动效 —— 给到具体数值 |
| `better-typography` | 字阶、间距、OpenType、折行、截断、标点 |
| `better-colors` | 生成色板、语义 token、格式转换、对比度 |
| `better-accessibility` | 键盘/焦点、ARIA、可访问名、表单、读屏、动效、缩放，对 WCAG 2.2 |
| `better-layout` | 分组、对齐、阅读顺序、响应式、翻译后仍站得住 |
| `better-writing` | 标签、错误、空态、确认 —— 对齐产品语气 |
| `interface-review` | 审 branch / PR / 未提交改动里**这次引入或回退**的界面问题（用户触发） |
| `explain-interface` | 从线上 URL 或截图解释某个站/效果/动画怎么做的（用户触发） |
| `break` | 把组件丢到临时页，扫能碰到的场景做压力测试（用户触发） |
| `build-design` | 从 Figma 或设计图还原，尽量用项目已有 token/组件 |
| `teardown` | 做可配置的物体技术插画，导出 SVG/PNG/PDF（与 3d 目录里的 [teardown](../3d/teardown.md) 模拟器不是同一个仓库） |
| `state-machine` | 组件各状态铺在临时页上，带切换器（用户触发） |
| `variant` | 同一组件出多变体，帮你迭代挑选（用户触发） |

## 怎么用

装进 agent 后，按任务点名：要整体体检用 `better-interface`；只修字用 `better-typography`；PR 上线前用 `interface-review`。它补的是**工程与可用性维度**，不替代品牌艺术指导。

## 限制

- 产出是审查报告与改码建议，**不会**像 hallmark/taste 那样从零定一套视觉世界观。
- 依赖你项目里已有组件与 token 时，`build-design` 效果最好；空项目仍会落到通用实现。
- 与 [taste-skill](./taste-skill.md) 可叠加：一个管味道，一个管工艺清单。

## 相关

- [impeccable](./impeccable.md) / [hallmark](./hallmark.md) / [taste-skill](./taste-skill.md) — 更偏「别做成 AI 默认页」。
- 仓库里的 `teardown` skill ≠ [elvarofficial/teardown](../3d/teardown.md)（可拆解 3D 模拟器）。
