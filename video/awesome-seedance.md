# awesome-seedance

[← 返回视频生成与编辑](./README.md) · [仓库](https://github.com/LearnPrompt/awesome-seedance) · [中文 README](https://github.com/LearnPrompt/awesome-seedance/blob/main/README_zh.md) · [案例浏览](https://goodcase.ai/cases?filter=video&q=seedance)

`MIT`（代码）· 整理内容 `CC BY 4.0` · Seedance 2.5 / 2.0 提示词验证库 · Agent Skill 可装

## 它是什么

面向 **Seedance（即梦 / Dreamina）** 的证据型提示词库：案例核对过原帖、带完整 prompt、有跨模型复测结论；另从案例提炼分类模板，并打包成可装进 Claude Code / Codex 等的 AI 视频 Skill。

数据日更自 [goodcase.ai](https://goodcase.ai)。规模会变，大致量级：九百多条已核案例、近五百次跨模型复测、二十多个分类模板、七十多个可安装 Skill。

**不是**视频生成器本身——成片仍要粘到 Seedance（或复测里用过的其他模型）去跑。

## 你能拿什么

| 形态 | 给谁 | 拿到什么 |
|---|---|---|
| 分类提示语模板 | 不想装东西的人 | 复制「直接复制」段，换掉【】，丢给任意对话模型润色后再进 Seedance |
| 案例画廊 / 热度榜 | 想对照成片与原帖 | 完整 prompt、来源帖、部分条有复测分 |
| Agent Skill | 已在用 coding agent | `npx` 一行装好，按片型或工作流让 agent 写结构化提示语 / 做验收 |

模板按片型切，例如：逐秒时间轴分镜、参考图身份锁定、分镜网格转视频、手持 UGC vlog、产品广告分镜、电影级叙事短片、打斗编排、音乐卡点 MV、3D 卡通短片等。

Skill 分两路：本仓 `agents/skills` 下以 `seedance-` 开头（模板库、制作工作流、单片型）；更多创作者方法也可经 goodcase-lite 装。

## 安装（Skill）

```sh
# 本仓模板库（一步装进 Claude Code / Codex）
npx seedance-prompt-library install

# 或按 skills CLI 装单个 skill，例如制作工作流
npx skills add LearnPrompt/awesome-seedance --skill seedance-production-workflow
```

新手五步（不装 Skill）：在模板索引里看图挑一类 → 打开模板复制「直接复制」→ 换【】里的产品/人物/场景 → 连同参考图发给任意对话模型 → 把成品提示语贴进 Seedance。效果不对先看模板里的常见坑。

## 限制

- **依赖闭源视频模型**：主路径是 Seedance；库内复测还用过 MiniMax、Grok Imagine 等——生成费用与账号在模型侧，不在本仓。
- 这是策展 + Skill，不是本地文生视频引擎；没有 GPU 也能读模板，但成片离不开模型 API / 产品端。
- 复测结论会标「复现 / 降级 / 失败」——热帖 prompt 不等于跨模型稳。

## 相关

- 同目录 [lemo-opuscar](./lemo-opuscar.md)：代码做片的风格箱（不调视频模型）；本仓是 Seedance 向提示词与复测。
- [hyperframes](./hyperframes.md) / [auto-motion](./auto-motion.md)：确定性 HTML 渲片或字幕驱动 MG 流水线，和「写进 Seedance 的 prompt」是另一条成片路径。
- 跨模态 MCP 制作台见 [scenario-labs/skills](../studio/scenario-skills.md)。
