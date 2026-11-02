# 视频生成与编辑

[← 返回目录](../README.md)

按「它提供什么」分区。一行说得清就留在本页；要写第二段（怎么跑、限制、复刻流程）就单独开文件，本页那条指向它。

## 风格库

- [lemo-opuscar](./lemo-opuscar.md) — 用代码做片的风格工具箱：66 种现成风格，每种 = 一段风格提示词 + 一支纯代码 demo 短片（不调用视频模型），也能从空白做出自己的风格。`MIT`

## 提示词与案例库

- [awesome-seedance](./awesome-seedance.md) — Seedance 2.5 / 2.0 已验证提示词库：案例核原帖、跨模型复测、分类模板 + 可装 Agent Skill（成片依赖即梦等闭源模型）。`MIT` / 整理 `CC BY 4.0`

## 短剧 / 漫剧 Skill 合集

- [awesome-short-drama-skills](./awesome-short-drama-skills.md) — 83 个短剧/漫剧 skill + 16 个配套平台，按创作阶段和适配模型分类，附两轮双盲实测（剧本、选题各与无 skill 对照组比）；索引本身不出片。`CC0-1.0`

## 生成器

- [openfilm](./openfilm.md) — 把编程智能体变成视频智能体：片子 = 一个 `film.html`（section 即轨道、CSS 定位、`#t=12,18` 切片）+ 每个镜头一个 `frame(t)` 纯函数；自带本地剪辑器 Studio 可手改任意元素，能导出透明/4K/运动模糊，也能把时间线交给 FCP / PR / DaVinci。`MIT`（名称是商标）
- [hyperframes](./hyperframes.md) — 写 HTML/CSS + 可 seek 动画，确定性渲成 MP4；给 coding agent 装 skills 后就能规划、写片、lint、预览、成片。`Apache-2.0`
- [video-shotcraft](./video-shotcraft.md) — 产品宣传片 Skill：抓真实页面 + 124 镜头配方，Remotion 成片，可进 Workbench / 导出剪映（非文生视频）。`Apache-2.0`

## 工作流

- [auto-motion](./auto-motion.md) — 给一份 `transcription.srt`，按语义自动拆成多段 MG 镜头、逐镜调 Claude Code 生成动画、FFmpeg 拼成竖屏 `final.mp4` 的工作流模板（Codex 调度）。`未声明协议`

## 跨域制作台（视频能力）

- [scenario-labs/skills](../studio/scenario-skills.md) — 经 Scenario MCP：文/图生视频、剪辑与调色、分镜连戏、广告、成片组装与字幕等（同包还覆盖图像/音频/3D/游戏资产）。`MIT`
- [Easel](../studio/easel.md) — 短视频/短剧、剪辑切片、字幕与成片，以及多平台发布复盘（同工作台还覆盖图文/音频）。`Apache-2.0`
