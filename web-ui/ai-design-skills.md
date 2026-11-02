# ai-design-skills

[← 返回网页与 UI 设计](./README.md) · [仓库](https://github.com/elayadesign/ai-design-skills) · [skills.sh](https://skills.sh/elayadesign/ai-design-skills)

`MIT` · 设计 Skill 合集 · 落地页从零搭建 + Figma 结构化设计 · Claude Code / Cursor / Codex 等

## 它是什么

给 AI coding 工具用的**可拆装设计 skill 包**：每个 skill 一个文件夹，按需安装。当前两支：

| Skill | 做什么 |
|---|---|
| `landing-page-design` | 从零做落地页：intake 问答、页面结构、转化文案，以及字体 / 间距 / 圆角 / 动效一整套视觉系统 |
| `figma-designer` | 在 Figma 里按真结构做：间距/圆角/色变量、具名文本样式、auto layout、多状态组件，以及随 token 更新的 Foundations 画板 |

改现有站另有姊妹仓 [redesign-skill](https://github.com/elayadesign/redesign-skill)（独立仓库，早于本合集）。作者还挂了 [SlopScan](https://slopscan.co)（商业向）：按同类规则审线上页，再把修复提示交给 agent——**本索引只收本开源仓**。

`landing-page-design` 的内容真实感与动效思路借鉴了 [taste-skill](./taste-skill.md)（MIT，见其 SKILL.md 致谢）。

## 安装

```bash
npx skills add elayadesign/ai-design-skills

# 只装一支
npx skills add elayadesign/ai-design-skills --skill landing-page-design

# 指定 agent / 用户级 / 仅列表
npx skills add elayadesign/ai-design-skills -a claude-code -a cursor
npx skills add elayadesign/ai-design-skills -g
npx skills add elayadesign/ai-design-skills --list
```

装好后用人话要即可（「按 landing-page-design 做一页…」「用 figma-designer 搭组件…」）。设计取值（字体、色、间距、动效）集中在各 `SKILL.md` 底部一节，fork 后改那一块即可带动全文。

## 限制

- 合集仍在增长；「改旧站」不在本仓，要另装 redesign-skill。
- Figma skill 需要你在 Figma 里能改文件；落地页 skill 产出的是给 coding agent 的设计/实现指引，不是托管建站 SaaS。
- SlopScan 是站外产品，不要和本 MIT 仓混为一谈。

## 相关

- [taste-skill](./taste-skill.md) — 艺术指导 + 真图 + 浏览器自检；本仓落地页 skill 有借鉴。
- [impeccable](./impeccable.md) / [hallmark](./hallmark.md) — 打磨现有页 / 主题 + lint。
- [jakubkrehel/skills](./jakubkrehel-skills.md) — 更广的界面工艺合集（含 Figma 还原等）。
- [scroll-world](./scroll-world.md) — 特定卷动 3D 世界落地页流水线（外模计费）。
