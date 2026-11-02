# video-shotcraft

[← 返回视频生成与编辑](./README.md) · [仓库](https://github.com/Vincentwei1021/video-shotcraft) · [中文 README](https://github.com/Vincentwei1021/video-shotcraft/blob/main/README_CN.md) · [Gallery](https://vincentwei1021.github.io/video-shotcraft/) · [Showcase](https://vincentwei1021.github.io/video-shotcraft/showcase.html)

`Apache-2.0` · Agent Skill（Claude Code / Codex）· Remotion 产品宣传片 · 124 镜头卡 / 150 shots

## 它是什么

对 agent 说「给我的产品做一支宣传片」：抓取真实页面 → 从调校好的**镜头配方库**选题排分镜 → [Remotion](https://www.remotion.dev/) 做动画 → 音乐卡点与音效 → 逐帧验收 → 可继续改的 MP4。

**不是文生视频模型。** 每一帧由代码基于你的截图与文案绘制，贴品牌、可编辑。成片还可进浏览器 **Motion Workbench**，或导出**剪映**草稿（镜头切段、字幕轨、SFX/BGM 分轨）。

同作者还有口播向姊妹仓 [video-talkcraft](https://github.com/Vincentwei1021/video-talkcraft)（动效钉人声）。

## 镜头库

约 **124** 张配方卡、**10** 类、共 **150** 个镜头（开场品牌、运镜、产品特写、面板网格等）。在 [Gallery](https://vincentwei1021.github.io/video-shotcraft/) 可搜、滤、复制卡名，直接点名给 agent。

## 怎么说

| 说法 | 会发生什么 |
|---|---|
| `Use video-shotcraft to make a promo for my product.` | 介绍模板（如 Ink Press）、抓页、做片 |
| `Make a launch film for this repo with the Ink Press template.` | 最快路径：截图 / 文案 / logo 套进已验证模板 |
| `Use the deck-deal-flyin and row-embed shot cards…` | 按 Gallery 卡名点镜头 |
| `Design a product close-up inspired by spotlight-hero-card.` | 单镜头适配你的产品 |

## 安装

```bash
npx skills add Vincentwei1021/video-shotcraft
```

或把仓库链接丢给 agent 安装；也可 `git clone` 后 symlink 到 `~/.claude/skills/` / `~/.codex/skills/`。国内可用 AtomGit 镜像：`https://atomgit.com/VincentWei/video-shotcraft`。

## 限制

- 面向**产品 / 功能宣传片**（真实 UI 截图），不是通用电影级文生视频。
- 需要能跑 Remotion 与本地渲染的环境；agent 侧主要调校 Claude Code / Codex。
- 剪映导出以仓库文档版本为准（README 曾实测 Mac 剪映 Pro 11.2）。

## 相关

- [hyperframes](./hyperframes.md) — 通用 HTML → 确定性 MP4；本仓专攻产品 promo + 镜头菜谱。
- [lemo-opuscar](./lemo-opuscar.md) — 代码做片风格箱（不抓产品页）。
- [auto-motion](./auto-motion.md) — SRT → 多镜 MG 竖屏流水线。
- [awesome-seedance](./awesome-seedance.md) — Seedance 提示词路径，与本仓代码成片不同。
