# huashu-art-motion

[← 返回动效与动画](./README.md) · [仓库](https://github.com/alchaincyf/huashu-art-motion) · [英文 README](https://github.com/alchaincyf/huashu-art-motion/blob/main/README.en.md) · [样片 Releases](https://github.com/alchaincyf/huashu-art-motion/releases/latest)

`MIT`（代码与文档）· 艺术动画 Agent Skill · 风格配方 + 解说语法 · 用代码让画动起来

## 它是什么

教 coding agent **用代码画出会动的艺术片**：先定一帧，再让它动；可拆参考片量转场/节拍，再按机制复刻。偏艺术史风格穿越、名画入画、口播解说动画段——不是网页 ScrollTrigger，也不是文生视频模型。

仓库量级会变，大致含：数十张艺术风格配方卡与对应场景代码、9 种解说语法（Kurzgesagt / Vox / 白板 / 3b1b / 动态字等）、长卷穿越骨架、纯代码配乐模板，以及 `qa.py` / `film_gate.py` / `deliver.py` 验收与交付门禁（反「PPT 翻页感」）。

## 你能说什么

| 说法 | 它做什么 |
|---|---|
| 「做个梵高／莫奈／包豪斯那种的动画」 | 风格配方卡 → 定帧 → 动起来 |
| 「复刻 / 拆这段动画」 | `breakdown` 量转场与运动热图，再代码复刻 |
| 「用我的口播做一段艺术动画」 | 镜头表 → 风格 → 世界画布 → 画面轨 |
| 「人穿过一幅幅名画」 | 长卷骨架：跨边界换画风 |
| 「做解说视频的动画段」 | 选语法 + JSON spec → 帧精确片段（可横竖/透明底） |

人物可用生图模型出帧，由代码合成；配乐可走 BPM 网格的纯代码合成。

## 安装与试渲

```bash
npx skills add alchaincyf/huashu-art-motion
```

依赖：`uv`、ffmpeg、Playwright Chromium。试一帧 / 一支片段：

```bash
cd huashu-art-motion
uv run --with playwright python scripts/engine/render.py --solo 09_postimp --stills 0.3 --out 试渲
uv run --with playwright python scripts/engine/render.py --spec scripts/engine/examples/t3_finance_chart.json --out 财经图表.mp4
```

可选语音/生图能力见仓库「可选媒体能力」；基础代码动画不强制账号。

## 限制

- Skill 正文以**中文**为主；完整口播示范多为参考代码快照，需自备部分角色素材。
- **花叔卡通形象、Clawd 示范成片**不随 MIT 外用；字体 OFL、个别笔顺数据有单独许可——见仓库 LICENSE 例外说明。
- 艺术史速通样片构图是「风格在变、场景不变」的机制示范，做新题材要重新构图。
- 起点致敬 Tak 的 Art History Speedrun：布局思路沿用，画面代码重画，不含原片素材。

## 相关

- [animate](./animate.md) — canvas + 程序化配乐 → 确定性 MP4（讲解/历史）；本仓更偏艺术史风格与解说语法库。
- [mg-styles-15](./mg-styles-15.md) — MG 风格成片参考。
- [lemo-opuscar](../video/lemo-opuscar.md) — 另一套代码做片风格箱。
- [gsap-skills](./gsap-skills.md) — 网页交互动效，不是成片艺术动画。
