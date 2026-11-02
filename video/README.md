# 视频生成与编辑

[← 返回目录](../README.md)

按「它提供什么」分区。一行说得清就留在本页；要写第二段（怎么跑、限制、复刻流程）就单独开文件，本页那条指向它。

## 风格库

- [lemo-opuscar](./lemo-opuscar.md) — 用代码做片的风格工具箱：66 种现成风格，每种 = 一段风格提示词 + 一支纯代码 demo 短片（不调用视频模型），也能从空白做出自己的风格。`MIT`

## 生成器

- [hyperframes](./hyperframes.md) — 写 HTML/CSS + 可 seek 动画，确定性渲成 MP4；给 coding agent 装 skills 后就能规划、写片、lint、预览、成片。`Apache-2.0`

## 工作流

- [auto-motion](./auto-motion.md) — 给一份 `transcription.srt`，按语义自动拆成多段 MG 镜头、逐镜调 Claude Code 生成动画、FFmpeg 拼成竖屏 `final.mp4` 的工作流模板（Codex 调度）。`未声明协议`
