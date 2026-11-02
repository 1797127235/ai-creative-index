# Claude-Code-Game-Studios

[← 返回游戏素材](./README.md) · [仓库](https://github.com/Donchitos/Claude-Code-Game-Studios)

`MIT` · 把一次 Claude Code 会话变成游戏工作室 · 49 agents · 74 skills · hooks / rules / 模板

## 它是什么

单聊做游戏没有职级、没有设计评审、也没有人拦你硬编码魔法数。这个模板按**真工作室层级**拆角色：

- Tier 1 总监：creative / technical / producer  
- Tier 2 部门 Lead：设计、程序、美术、音频、叙事、QA、发行、本地化…  
- Tier 3 专精：玩法/引擎/AI/网络/工具/UI 程序，系统/关卡/经济设计等  

每人有职责、升级路径和质量门。你仍做所有决定，但有人问该问的问题、早拦错、从脑暴盯到上线。

附带：约 15 hooks、14 path-scoped rules、60+ 文档模板（GDD、UX、ADR、冲刺、HUD、无障碍…）。

## 会不会只会写文档？

作者用同一 brief、不同 `modes.rigor` 测过：`standard` 在第一行游戏代码前可写出约 30 份文档，但盲审+实机试玩里未必赢过更轻的流程——**多文档买的是可追溯，不是自动更好玩**。

另一条硬规则：改到玩家看得见的东西，故事不能结，除非**真的启动游戏、看过、截图留在** `production/qa/evidence/`。过解析 ≠ 过游玩。仓库故意不塞别人的成品游戏，避免模板里堆无关工程。

## 安装与起步

依赖：Git、Claude Code、Python 3（读 `project.yaml`）、Bash（hooks）；推荐 `jq`。

```bash
git clone https://github.com/Donchitos/Claude-Code-Game-Studios.git my-game
cd my-game
claude   # 必须在含 CLAUDE.md / project.yaml 的根目录开
```

然后 `/start`：问你现在处在「没想法 / 模糊概念 / 设计清晰 / 已有工程」哪一档，再导入对应流程。也可直跳 `/brainstorm`、`/setup-engine godot 4.7`、`/project-stage-detect` 等。

`project.yaml` 是行为单一真相源；最关键旋钮是 **`modes.rigor`**：`minimal`（默认，Jam 速度）/ `standard` / `full`，一次门控文档密度、QA、评审人数等。

## Slash 命令（节选）

| 阶段 | 例子 |
|---|---|
| 入职 | `/start` `/setup-engine` `/adopt` |
| 设计 | `/brainstorm` `/design-system` `/map-systems` |
| 美术/UX | `/art-bible` `/asset-spec` `/ux-design` |
| 故事与冲刺 | `/create-epics` `/create-stories` `/dev-story` `/story-done` |
| 评审/QA | `/design-review` `/code-review` `/qa-plan` `/smoke-check` |
| 发行 | `/release-checklist` `/patch-notes` `/hotfix` |
| 多 agent 编队 | `/team-combat` `/team-ui` `/team-audio` … |

完整 74 个在仓库 README 的 Slash Commands 一节。

## 限制

- **只服务 Claude Code** 这套 agents/skills/hooks 布局；换工具要大量移植。
- 默认在 `game-assets` 下是因为「做游戏的 AI 工作流」；它产出的是流程与工程纪律，**不是**现成像素包（素材见 [pixelfx](./pixelfx.md)）。
- `full` rigor 文档税很重；小项目用 `minimal`，别被模板吓跑。

## 相关

- [pixelfx](./pixelfx.md) — 可进引擎的像素特效代码/精灵图。
