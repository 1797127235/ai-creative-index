# mg-styles-15

[← 返回动效与动画](./README.md) · [仓库](https://github.com/Vincentwei1021/mg-styles-15) · [15 支成片在线看（带声音）](https://vincentwei1021.github.io/mg-styles-15/?lang=zh)

`MIT` · 15 种 MG 风格 × 10 秒成片 · 全部由 Claude Opus 5.5 写代码生成，不用生图/生视频模型

## 它给你什么

不是「一堆好看的片子」，而是**可以整条复刻的生产线**：每种风格都能拿到成片、风格说明、完整提示词、全部源码，四样都在同一个仓库里。你要做一条同风格的片，把对应的提示词丢给 AI，改题材就行。

- 画面 = 代码：SVG / Canvas / WebGL / Three.js；3D 那支用 Blender 渲染画面，网页只叠文字和颗粒。少数几支用了 CC0 或公有领域照片。
- 声音也是代码：每支片的 `audio.py` 在同一组时间点上合成配乐和音效，15 支共用 103 个真实录制的乐器采样。
- 每支片经过两轮 AI 评审（按 `rubric.md`），终评 7.57–8.21 / 10。

## 15 种风格

| # | 风格 | 提示词 | 源码 |
|---|---|---|---|
| 01 | 逐帧手绘 / 线条沸腾 | `prompts/05-cel-boil.md` | `demos/05-cel-boil` |
| 02 | 等轴 2.5D | `prompts/03-isometric.md` | `demos/03-isometric` |
| 03 | 扁平矢量动画 | `prompts/01-flat-vector.md` | `demos/01-flat-vector` |
| 04 | 线条动画 | `prompts/02-line-art.md` | `demos/02-line-art` |
| 05 | 3D 渲染系 | `prompts/04-3d-render.md` | `demos/04-3d-render` |
| 06 | 形变动画 | `prompts/08-morph.md` | `demos/08-morph` |
| 07 | 粗描边贴纸人科普 MG | `prompts/19-paperclip.md` | `demos/19-paperclip` |
| 08 | 赛博朋克 HUD / FUI | `prompts/22-hud.md` | `demos/22-hud` |
| 09 | 拼贴剪贴 | `prompts/06-collage.md` | `demos/06-collage` |
| 10 | 弥散渐变 / 玻璃拟态 | `prompts/12-aurora-glass.md` | `demos/12-aurora-glass` |
| 11 | 几何构成 / 包豪斯 | `prompts/09-bauhaus.md` | `demos/09-bauhaus` |
| 12 | 复古 80s Synthwave / VHS | `prompts/10-synthwave.md` | `demos/10-synthwave` |
| 13 | 像素风 | `prompts/20-pixel.md` | `demos/20-pixel` |
| 14 | 液态流动 | `prompts/07-liquid.md` | `demos/07-liquid` |
| 15 | 综艺花字 | `prompts/18-hanazi.md` | `demos/18-hanazi` |

> 提示词文件编号（05、03、01…）和上表序号不一致，是仓库内部的制作顺序；按文件名找，别按序号。

## 一支片怎么做出来（这套流水线本身就是可复用的方法）

1. 每种风格一段提示词（`prompts/*.md`）交给 Claude。
2. Claude 把片子写成一个**网页**：暴露 `window.renderAt(t)`，给它任意时间点就画出那一帧 —— 这是整条流水线能确定性重跑的关键。
3. 无头 Chrome 逐帧截图。
4. `audio.py` 在**同一组时间点**上合成配乐与音效，画面和声音不会错位。
5. ffmpeg 合成正好 10 秒的 MP4。
6. 另一个 AI 按 `rubric.md` 评审 → 改两轮。

3D 那支是例外：Blender 渲染画面，网页只负责文字和颗粒。

## 怎么用

- 只想要灵感：在线看成片，挑风格。
- 想复刻：复制 `prompts/<风格>.md`，把题材、文案、品牌色换掉，让 AI 先生成一版网页动画，再走第 3–5 步渲染。
- 想改模板：`template.md` 是骨架，`harness/` 是渲染脚本，`lib/` 是共用绘制层，`requirements.txt` 是 Python 依赖（音频合成用）。
- 想自己定审片标准：直接改 `rubric.md`，评审环节会跟着你的标准走。

## 限制

- 成片固定 **10 秒**；做长片得自己改时长，`renderAt(t)` 的时间轴和音频对齐也要重排。
- 逐帧渲染（无头 Chrome 或 Blender）—— 这是「画面完全可控」的代价，长片会很慢。
- 提示词是围绕 Claude Opus 5.5 写的，换模型后出片质量会漂，需要人看一眼再调。
- 许可 MIT，代码可商用；但少数照片素材是 CC0/公有领域，二次分发前自己确认一遍。

## 同类

- [lemo-opuscar](../video/lemo-opuscar.md) — 66 种「用代码做片」风格，更偏整套制片流程（分镜、配乐、字幕）。
- [animate](./animate.md) — 同样是代码出片，但它是 Claude Code skill，自带分镜/审片/多尺寸导出，长片比它顺手。