# 网页与 UI 设计

[← 返回目录](../README.md)

按「它提供什么」分区。一行说得清就留在本页；要写第二段（怎么跑、限制、复刻流程）就单独开文件，本页那条指向它。

## 设计 Skill

- [impeccable](./impeccable.md) — 给 coding agent 的设计词汇：`polish` / `bolder` 控方向，`critique` / `audit` 审稿，62 条确定性规则抓 AI slop，装上就能对着现有页面或组件迭代。`Apache-2.0`
- [hallmark](./hallmark.md) — 反 AI 味的网页设计 skill：50 套材质主题，按「这页要干什么」铺版，浏览器里 lint 机造痕迹，也能 `/hallmark redesign` 改现有页。`MIT`
- [taste-skill](./taste-skill.md) — 给 agent 审美：艺术指导 + 真实参考图 + 浏览器自检，用来做站和 App 屏，而不是拼一张平均落地页。`MIT`
- [jakubkrehel/skills](./jakubkrehel-skills.md) — 界面工艺 skill 合集：排版、色板、无障碍、布局、文案、Figma/图稿还原，以及整屏 review / 变体 / 压力测试。`MIT`

## 平台能力（非仓库）

- （平台能力，非仓库）HTML-in-Canvas — Chrome 157+ 原生能力：把真实 DOM 直接画进 2D/WebGL/WebGPU canvas 做特效，网页依然可交互，不用 html2canvas 截图。[规范文档](https://developer.chrome.com/docs/web-platform/html-in-canvas) · [带源码的可交互演示](https://baked.design/fun/html-in-canvas/)（@nickbakeddesign） · [来源帖](https://x.com/sundyme/status/2116153194279764281)
