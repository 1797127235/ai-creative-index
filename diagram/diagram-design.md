# diagram-design

[← 返回示意图 / 信息图](./README.md) · [仓库](https://github.com/cathrynlavery/diagram-design) · [网站](https://diagramdesign.dev) · [图鉴](https://cathrynlavery.github.io/diagram-design/)

`MIT` · Agent Skill · 45 种编辑向示意图 · 自包含 HTML + SVG · No Mermaid slop

## 它是什么

让 coding agent 用人话出图：架构、时序、象限、泳道、ER、甘特、Sankey、用户旅程……一共约 **45** 种视觉类型。产物是**一个可双击打开的 `.html`**（内联 SVG），可再导出 PNG/SVG。

设计立场是编辑向示意图，不是「能画就行」：

- 无阴影、不走 Mermaid 默认皮肤；
- 密度目标约 4/10，能删就删，焦点色只点 1–2 处；
- 可 onboard 到你的网站，抽色板和字体，后面每张图跟品牌走。

也支持从 `.drawio` / Mermaid / `.excalidraw` 导入，再按同一套视觉重画。

## 怎么用

人话举例：

> Make me an architecture diagram of my app: frontend, backend, database, Redis cache.  
> I need a quadrant showing Q2 projects by impact vs effort.  
> Give me a sequence of a bearer call with token refresh on 401.  
> Onboard diagram-design to https://yoursite.com

Agent 先选型、说计划，再写出那个 HTML。新项目第一次画图前会问要不要定制 style guide（URL / 已有 skill / 本地设计系统 / 粘贴 token / 保持默认 / 读已存 profile）。

## 安装

跨 Agent Skills 宿主（Cursor、Claude Code、Codex、Copilot、Gemini CLI 等）：

```sh
npx skills add cathrynlavery/diagram-design
```

Claude Code（带 slash 命令与更新）：

```text
/plugin marketplace add cathrynlavery/diagram-design
/plugin install diagram-design@diagram-design
```

Codex / Copilot 等也有各自的 marketplace 装法，见仓库 README。官方包只认本仓库；`PRIVACY.md` 写明 skill 会不会联网、连什么。

## 适合 / 不适合

适合：读者从图里学到的比散文、表格、列表更多的时候。

不要用：纯列表、只比属性的前后对比、一个形状就能说完的「图」、需要速记 unicode 线框图（那是别的工具）。

## 限制

- 绑 Agent Skills / 各家插件机制，不是独立 GUI 绘图软件。
- 默认皮肤未定制时，会主动拦你，避免整库图都长得像官方 demo。
- 节点一多就该拆成两张；它解决的是**可读的编辑图**，不是无限复杂的运维拓扑大屏。
- 和网页落地页设计 skill（[impeccable](../web-ui/impeccable.md) 等）互补：一个管页面，一个管示意图。

## 相关

- [anatomy](../3d/anatomy.md) — 等轴测实体「机器隐喻」插画，不是方框箭头示意图。
- [web-ui/](../web-ui/) — 页面与 UI 审美；不是架构/时序图。
- [image/](../image/) — 预留文生图/改图；本仓库产出是代码画的 SVG，不进那一类。
