# lemo-opuscar

[← 返回视频生成与编辑](./README.md) · [仓库](https://github.com/lemomo-ai/lemo-opuscar) · [风格图鉴](https://lemomo-ai.github.io/lemo-opuscar/) · [中文说明](https://github.com/lemomo-ai/lemo-opuscar/blob/main/README.zh-CN.md)

`MIT`（代码）· 内容多为 `CC BY 4.0` · 用代码做片的风格工具箱 · 为 Claude Opus 5.5 调校

## 它是什么

不是 awesome 列表：库里每支 demo 片都是作者用 **Claude Opus 5.5 写代码**导出来的——Canvas/WebGL 逐帧画面、采样库原创配乐、TTS 旁白，**不调视频生成模型、不用素材库成片**。

你选一个风格（或改成自己的），带上故事，让编程 agent 当导演。另有特别片 **OPUSCAR 98**（98 年最佳影片巡礼）和对应 98 套可复用风格提示词。

## 风格怎么组织

约 **66** 种现成风格（仍在加），含分类如：

- 常规代码 MG / 插画风
- **剪辑与纪实**：真档案、文件、数据剪出来
- **实证影像**：拍真实素材，数字有出处

每种 = `styles/<name>/STYLE.md`（画什么、听什么）+ demo 成片。完整索引见仓库 `styles/README.md`；中英文风格名都能点名。

## 流程（agent 当小工作室）

装 skill 后直接说要什么，例如：

> Make a 45-second film in the **watercolor** style about …

它会先问清：题材里定不了的点、你有没有自己的人声/音乐/素材、要不要先看分镜。然后读三份指南：

| 文件 | 给 agent 什么 |
|---|---|
| `DIRECTOR.md` | 故事、声音、节奏、镜头、表演、自检 |
| `TECHNIQUE.md` | 逐帧渲染、配音、配乐、混音 |
| `styles/<style>/STYLE.md` | 这套风格的视听规则；故事是你的 |

**改成自己的风格**：基于库内风格改品牌色/角色/调性，或从空白做一套没有的，流程与作者往库里加新风格相同；可存下来以后复用。

## 安装

```sh
claude plugin marketplace add lemomo-ai/lemo-opuscar
claude plugin install lemo-opuscar@lemolab
```

- 首次会把指南、工具、风格提示词下载到 `~/lemo-opuscar`（所有片子共用）。
- 每支片的工程（源码到成片）落在你发起时所在目录；clone 用法则进仓库里的 `films/<name>/`。
- 其他 agent：拷 `plugin/skills/lemo-opuscar/` 到各自 skills 目录。
- 只开 skill 不带参数：`/lemo-opuscar:lemo-opuscar`，会问语言和要做片 / 改风格 / 用已存风格。

## 限制

- **为 Claude（尤其 Opus 5.5）调的**；换模型复现度会掉，作者明确警告。
- 画面是程序化/档案实证路线，不是电影级实拍或扩散模型质感。
- 逐帧渲染，片越长越慢；复杂片要自己盯分镜与时长。

## 相关

- [hyperframes](./hyperframes.md) — HTML 时间轴 → 确定性 MP4，偏可编辑工程。
- [auto-motion](./auto-motion.md) — SRT 自动拆镜，底层也用 HyperFrames 技能。
- [mg-styles-15](../motion/mg-styles-15.md) / [animate](../motion/animate.md) — 动效侧同类「代码出片」。
