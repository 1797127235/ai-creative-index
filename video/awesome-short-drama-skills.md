# awesome-short-drama-skills

[← 返回视频生成与编辑](./README.md) · [仓库](https://github.com/UnderleveledBuilder/awesome-short-drama-skills) · [网站](https://shortdramaskills.com)

`CC0-1.0` · 短剧/漫剧 Agent Skill 索引 · 83 个 skill + 16 个平台 · 带两轮实测

## 它是什么

不是某一个 skill，而是**AI 短剧 / 漫剧这一整条流水线的 skill 索引**：小说改编、集纲、钩子与付费卡点、剧本审稿、分镜、角色资产，以及给 Seedance / 可灵 / MiniMax 的视频提示词。目前 83 个 skill + 16 个配套开源平台（后者是完整应用，不是 skill）。

和普通 awesome list 的区别是它**自己做过对照实验**：

- **第一轮（2026-10-18）**：10 个剧本 skill + 无 skill 对照组，同一个开放题各写 3 次，Opus 与 GPT 双盲评。4 个 skill 三次全赢对照组。
- **第二轮（2026-10-20）**：11 个选题 skill + 对照组，同一道爽文选题各定 3 次，两两盲比计分。两位评审的前三名一致，且都三次全赢。

原始稿、评审脚本、run 记录都在 `evals/`，可复跑。

## 怎么读

| 你想 | 去哪 |
|---|---|
| 从零到成片一路跑完 | 「全流程：剧本 → 分镜 → 成片」23 个 |
| 只缺某一步 | 「按创作阶段查找」 |
| 指定视频模型 | 「按视频模型查找」（Seedance / 可灵 / MiniMax） |
| 抄别人的搭配 | 「推荐组合」4 套（小说改编 / 原创爆款 / Seedance 出片 / 漫剧长线连载） |
| 先看谁真的赢 | 上面两轮实测表 |

分类不是按作者，是按**创作阶段**和**适配模型**——和你这个仓库的切法一致。

## 安装

它自己是索引，装的是里面的 skill，绝大多数是标准 `SKILL.md`。常见：

```bash
npx skills add <owner>/<repo>
```

然后直接把仓库地址丢给千问办公、豆包电脑版、龙虾（OpenClaw）、WorkBuddy、Kimi Code、Qwen Code、CodeBuddy、Trae、Qoder、Claude Code、Codex 等支持技能的 agent。

> 注意：仓库里的批量安装命令自称「未逐个验证，以各仓库 README 为准」——这点很诚实，也说明装的时候要一条条来。

## 数据怎么维护

`data/*.toml`（skills / packs / taxonomy / 分类）+ `templates/` → `scripts/build.py` 生成 README，**不要手改 README**。每周一自动刷新星数、最近更新、许可证并搜索新仓库；新仓库人工核对后才收录。「人工核对」指核对仓库说明、目录结构和分类，**不等于实测过效果**——实测看 `evals/`。

## 限制

- 索引本身不产片；成片仍依赖 Seedance / 可灵 / MiniMax 等**闭源视频模型**和额度。
- 两轮实测只用了 `claude-opus-5-5` 一个模型；集尾钩子两位评审结论相反，另 6 个 skill 分歧很大——结论别当定论。
- skill 稿子里常夹编号和自检表，交给 AI 出片前要删。
- 推荐组合注明「尚未实测」，只是按仓库说明搭的。
- 收录是「有人收录」不是「都值得装」，装前先读它的 `SKILL.md`（可能带脚本）。

## 相关

- [awesome-seedance](./awesome-seedance.md) —— 单个视频模型的提示词库与复测；这份索引是「整条短剧流水线」。
- [scenario-labs/skills](../studio/scenario-skills.md) —— 经 MCP 直接出片、剪辑、调色，不靠 skill 拼装。
- [Easel](../studio/easel.md) —— 短剧/短视频制作台，覆盖剪辑切片与发布复盘。
- [lemo-opuscar](./lemo-opuscar.md) —— 若最终要的是「成片风格」而非「短剧叙事」，走风格库。