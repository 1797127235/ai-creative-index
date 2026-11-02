# dimensional-drawing

[← 返回网页与 UI 设计](./README.md) · [仓库](https://github.com/enesozturk/dimensional-drawing)

`MIT` · Agent Skill · Apple 风格 UI 组件尺寸图 · 可选 motion 成片

## 它是什么

把 UI 组件画成 **一页技术规格图**（对标 Apple 配件 dimensional drawings）：padding、gap、圆角、图层、视口位置，测量并标注。单色线稿、用线宽/虚线/剖面区分层次；刻意不画文案内容，换 copy 也不过时。

产出通常是：标题块 + 关键变量、平面图、爆炸图层、细节圆（圆角/嵌套）、变量表。物理物件（如保温杯）也可画第三角视图，但只标已公布尺寸。

## 两条 Skill

| Skill | 作用 |
|---|---|
| `dimensional-drawing` | 根据源码 / Storybook / URL / 截图出规格 HTML |
| `dimensional-drawing-motion` | 把成品图画成约 10 秒「笔在画 + 镜头运动」短片 |

### 画图家规（摘要）

- **单色**：只用灰阶
- **架构不是内容**：TITLE SLOT · FLEX，ACTION · HUG，CONTENT SLOT · FILL
- **变量不是裸数字**：如 `S1`、`R2 = R1 − B − S6`
- **无品牌名**：中性代号如 `UI-CARD-001`
- **不编造**：未知值标 `[TBD]`

## 安装

```bash
npx skills add enesozturk/dimensional-drawing

# 或 Claude Code：拷 skills/* 到 ~/.claude/skills/
git clone https://github.com/enesozturk/dimensional-drawing
cp -r dimensional-drawing/skills/* ~/.claude/skills/
```

## 怎么用

> Make a dimensional drawing of the `Card` component in `src/components/Card.tsx`  
> Draw the anatomy of our settings dialog, same style as the examples  
> Animate this drawing

仓库 `skills/dimensional-drawing/examples/` 有 card / dialog 单文件 HTML 样例。成片样例见 `assets/dialog-motion.mp4`。

**动起来**：主路径是 Claude **Motion** artifact 导出 MP4；无 Claude 时可用 `skills/dimensional-drawing-motion/adapters/headless`（Playwright + ffmpeg，`Node 18+`）。Remotion / GSAP / Lottie 等**未测**。

## 限制

- 强项是**组件架构尺寸图**，不是整站审美 redesign（那用 impeccable / hallmark 等）。
- Motion 以 Claude Motion 调校为准；无头渲染是备选，别默认当成任意动画引擎。

## 相关

- [impeccable](./impeccable.md) / [jakubkrehel/skills](./jakubkrehel-skills.md) — 打磨与工艺；本仓出规格解剖图。
- [diagram-design](../diagram/diagram-design.md) — 通用示意图；本仓专做 UI 规格页。
- [animate](../motion/animate.md) — 通用程序化短片；本仓 motion 只服务「规格图画成片」。
