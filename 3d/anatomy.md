# anatomy

[← 返回 3D / 空间](./README.md) · [仓库](https://github.com/wheresryan22/anatomy) · [介绍页](https://skills.wheresryan.sh/anatomy)

`MIT` · Agent Skill · 把概念做成可交互的等轴测「机器图」· SVG / SVG+WebGL / 3D（beta）

## 它是什么

多数技术说明是方框和箭头；Anatomy 反过来：**为概念发明一台会工作的实体**，再用大量精细零件画出来。

例子：cache key 未变则跳过计算 → 一把只有销全对齐才转的弹子锁；一个 GPU context 服务多块 canvas → 一台打印头巡游 16 个井的龙门机。

成图放在带标题、提示和**实时读数**的卡片里，指针/键盘可轻推；读数来自驱动零件运动的同一小模型。自检会放大每一个关节。支持 Claude Code、Antigravity、OpenCode、Codex、MiniMax Code。

## 三种成片

| 种类 | 是什么 | 例子 |
|---|---|---|
| SVG | 核心：四调明暗等轴测实体，前后绘制，可导出独立 HTML / 内嵌样式的 `.svg` / React 组件 | dial-indicator、arcade-cabinet |
| SVG + WebGL | 火、水、焦散、灯光等线条画不出的东西；shader 夹在前后 SVG 之间，同一套等轴相机 | raptor-engine、ripple-tank |
| 3D（beta） | 旋钮、转台、可折断落下的零件等真 3D 运动；动件每帧重投影重着色，其余仍是静画 | turning-dial |

先按浅色主题设计（含 shader）；也有深色。仓库 `examples/` 里有可直接打开的成品页。

## 安装

```sh
npx skills add wheresryan22/anatomy -g
# 或指定宿主：-a claude-code / antigravity / opencode / codex / minimax-code
```

只需较新的 Node（skills CLI 会要求版本）；**不要 API key，也不用再 `npm install`**，kit 只用 Node 内置模块。整仓含例子大约十几 MB。

## 用法

```text
/anatomy explain how a token bucket rate limiter works, interactive
```

Codex 上用 `$anatomy`。也可以不点名 skill，直接要「等轴测说明图 / 文档用可交互 figure」。

好习惯：先定体量（Figure / Hero / Epic）和大概耗时；说清要交互还是静图、浅色还是深色、HTML / SVG / React；给真实约束（连接池大小、TTL 秒数），别只给形容词。

## 限制

- **不是图表库**：没有坐标轴和数据序列；数字是读数和零件真实个数/尺寸。
- 画的是机器、仪器、工具、家具；**不画人、不做精确地图**。没有机制可发明的概念会弱。
- **故意慢**：零件表、几何、审计、双主题关节特写；Raptor 级几分钟，完整 3D 环视审计可到十几二十分钟。
- Shader 要 WebGL；没有也能读 SVG。减少动效时整图静止。
- Codex 沙箱可能拦无头 Chrome 自检；成片仍在，只是检查失败——按仓库 README 放行或本机跑 `scripts/capture.mjs`。

## 相关

- [teardown](./teardown.md) — 同是可拆机器 HTML；偏「拆真机器读面板」，Anatomy 偏「为概念造隐喻机器并精画」。
- [diagram-design](../diagram/diagram-design.md) — 架构/时序等编辑向示意图，不是等轴测实体插画。
- [text-to-cad](./text-to-cad.md) — 出可制造 STEP/STL；Anatomy 出说明用 figure。
