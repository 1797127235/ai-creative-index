# hyperframes

[← 返回视频生成与编辑](./README.md) · [仓库](https://github.com/heygen-com/hyperframes) · [文档](https://hyperframes.heygen.com/introduction) · [Showcase](https://hyperframes.heygen.com/showcase)

`Apache-2.0` · HeyGen 开源 · 写 HTML → 确定性渲 MP4 · 为 coding agent 设计

## 它是什么

把 **HTML / CSS / 媒体 / 可 seek 动画**渲成 MP4：时间轴暂停后逐帧 seek，**同输入同像素**。本地 CLI、Studio 桌面端、或挂在托管工作流里当渲染核都行。

给 Claude Code / Codex / Cursor 等装 skills 后，agent 会按「规划 → 写合法 HTML → 接线动画 → 加媒体 → lint → 预览 → 成片」闭环做片。

## 工程长什么样

- 根 `index.html`：声明变量，挂各场景子合成。
- `compositions/`：每场景一份；`assets/` 放媒体和字体。
- 新建：`npx hyperframes init <dir>`；把网站当题材：`npx hyperframes capture <url> --json`。
- 默认常见规格：1920×1080 @ 30fps（竖屏等按需求改）。

硬契约（`npx hyperframes check --json` 会报，多数带 `Fix:`）：

1. 定时元素：`class="clip"` + `data-start` / `data-duration`，区间半开。
2. 片长 = 根上 `data-duration`；超时裁切，提前结束定格末帧。
3. 每个合成注册暂停时间轴：`window.__timelines["id"] = tl`。
4. 禁止 `Date.now()`、未播种随机、联网 fetch、定时器、`repeat: -1`——可见物必须是时间的函数。
5. 勿用 GSAP 和 CSS `transform` 抢同一节点；媒体不要 `play()`，用时间轴驱动。
6. 资源路径 `assets/...`（无前导 `/`）；成片可编辑性靠稳定 `id` 与 `data-var-*` 变量。

做图表、转场、字幕样式前，先搜 registry；真人口播/成片素材走 media-use 约定（何时需要 HeyGen、何物免费）。

## 安装

```sh
# Claude Code 插件（推荐）
claude plugin marketplace add heygen-com/hyperframes
claude plugin install hyperframes@hyperframes

# 或 skills（含 OpenCode 等）
npx skills add heygen-com/hyperframes
# / 非交互、要最新 main：
npx hyperframes skills update
```

桌面 Studio：官网提供 macOS / Windows / Linux (.deb)。Node **≥ 22**。

试一句：

> Using `/hyperframes`, create a 10-second product intro with a fade-in title…

## 限制

- 要会（或让 agent 会）写符合契约的 HTML 时间轴；乱写随机/网络依赖会渲不一致或直接 check 失败。
- 「确定性」换来的是工程约束，不是一键文生视频。
- 部分口播/数字人能力接到 HeyGen 商业侧；纯开源路径以本地 HTML 渲染为主。

## 相关

- [auto-motion](./auto-motion.md) — 用 Codex 调度 + 本仓库技能，把 SRT 拆成多镜再拼片。
- [lemo-opuscar](./lemo-opuscar.md) — 风格库更大，偏 Claude 导演整支片。
- [animate](../motion/animate.md) — 单文件 canvas 程序化短片另一条线。
