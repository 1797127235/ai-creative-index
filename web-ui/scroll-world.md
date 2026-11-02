# scroll-world

[← 返回网页与 UI 设计](./README.md) · [仓库](https://github.com/oso95/scroll-world)

`MIT` · Agent Skill · 品牌 → 可滚动「飞穿小世界」落地页 · 依赖外模出图出片

## 它是什么

给 Claude Code / Codex 等装的 skill：为任意行业或品牌做出**滚动 scrub 的连续镜头落地页**——相机从场景外飞入内部，再无剪接到下一场（类似 Emons 物流站那种「小世界飞行」叙事，可套到你自己的题材）。

流程是 AI 出**等轴测场景静帧** + **dive-in / 接缝视频链**，再用可移植的 vanilla JS 引擎按滚动位置播整条链。相机在片里真的在动，滚动只驱动时间；不绑死 Next / Vue 等框架。

## 调用时做什么

1. **访谈**：题材与 pitch、品牌 kit（URL / 自备 / 让它提议）、美术方向、相机访问的有序场景、要不要**原生竖屏 9:16 第二链**（不是横屏裁切）、预算与渲染档位（先报价再开跑）。
2. **出资产**：每场一张静帧、一段 dive-in；邻场之间用真实邻帧生成 **connector**，保证接缝像素一致。
3. **接线**：配置驱动的 scrub 引擎串成一次飞行；手机自动切竖屏链与海报。

Skill 内含：`SKILL.md`、提示词模板、批处理管线说明、`scrub-engine.js`、`index-template.html`、可选背景抠除脚本。

## 安装

```bash
# Claude Code 插件（推荐）
/plugin marketplace add oso95/scroll-world
/plugin install scroll-world@scroll-world

# 或 skills CLI
npx skills add oso95/scroll-world
```

也可把 `skills/scroll-world` 拷进 `~/.claude/skills/` 或 `~/.codex/skills/`。

## 依赖与费用（必读）

| 依赖 | 用途 |
|---|---|
| Monid CLI + 余额 | **默认**视频链后端（Seedance 2.0，按条 USD） |
| Higgsfield CLI + credits | 场景静帧、`kling3_0` 回退；无 Monid 时整条链也可走它 |
| Codex CLI（可选） | 静帧可走内置 `image_gen`（ChatGPT 订阅计费） |
| `ffmpeg` / `ffprobe` | 抽帧与编码 |
| Python 3 + Pillow | 竖屏画布、可选透明抠景 |

Skill 开源 ≠ 生成免费。文档量级：约 6 场景 1080p 链 ≈ **$27**（Monid 按 token，以当次打印为准）；竖屏链会再翻倍视频条数。开跑前会给出预估并等你确认。

## 限制

- 强依赖商业视频/图像 API；账号、余额、模型目录变化时管线会做探测，以仓库 README 为准。
- 成片 `.mp4` / `.webp` 按项目生成，不随 skill 仓库分发。
- 和「纯代码 GSAP 卷动」不是一条路：这边是 **AI 视频链 + scrub**。

## 相关

- 同目录 [impeccable](./impeccable.md) / [hallmark](./hallmark.md) / [taste-skill](./taste-skill.md) — 通用审美与建页；本 skill 专攻一种卷动世界叙事。
- [gsap-skills](../motion/gsap-skills.md) — 代码侧滚动动画；可互补，但不是本流水线。
- [awesome-seedance](../video/awesome-seedance.md) — Seedance 提示词库；本仓用 Seedance 当飞行片后端之一。
