---
id: goal-and-requirements
type: goal-and-requirements
status: draft
title: AI 创作开源项目索引
---

# AI 创作开源项目索引

一个仓库：只收**开源**的、能帮 AI 做创作的项目，按用途领域分类。

## Overview

用 README 当索引，按用途领域分节收录开源项目，每条一行说明它帮 AI 做什么。
不建网页、不做后端，读的人只需要会翻 Markdown。

## Problem

现在找 "帮 AI 做网页设计 / 动效 / AIGC 的开源项目"，得在若干个 awesome-list 之间翻：
大部分列表要么只覆盖单一领域（UI、视频、动效各一份），要么混入大量闭源 SaaS 和通用 AI 工具，
看完还得自己逐个判断"这个是不是开源、是不是帮 AI 干活"。这个仓库只回答一个问题：
**有哪些开源项目，能帮 AI 做某一类创作。**

## Capabilities

- README 作为唯一入口：按用途领域分节，给出项目名、链接、一句话说明。
- 只收开源项目，每条标注它的开源协议（unconfirmed：尚未确定是否强制标注）。
- 允许少量「平台能力」条目（不是仓库，如浏览器原生 API），必须显式标注。
- 领域分类由维护者（用户）自己划分和维护；README 只提供起始骨架。
- 仓库自带开源协议文件。

## Non-Goals

- 不做浏览器展示页、不做搜索/筛选界面。
- 不做后端、数据库、账号体系。
- 不做链接自动抓取或自动分类。
- 不收录闭源产品、商业 SaaS、纯模型权重（除非它本身是创作工具）。

## Alternatives Considered

| 项目 | 缺口 | 链接 |
|---|---|---|
| isaacsight/awesome-creative-intelligence | 最接近（开源创作智能项目），但跨视觉/音乐/写作/科研，不是按"帮 AI 做设计"来组织 | https://github.com/isaacsight/awesome-creative-intelligence |
| swiftsimplify/awesome-open-source-ai-tools | 737+ 开源 AI 工具，够全但没有创作领域的横切视角，条目太重 | https://github.com/swiftsimplify/awesome-open-source-ai-tools |
| allanjsx/awesome-ai-for-design | AI 设计工具，混入大量商业产品（Lovable、v0、Figma Make） | https://github.com/allanjsx/awesome-ai-for-design |
| maxbogo/awesome-ai-tools-for-ui | 只覆盖 UI/设计辅助工具与 agent skills | https://github.com/maxbogo/awesome-ai-tools-for-ui |
| rapidpages/awesome-gen-ui · narrowin/awesome-generative-ui | 只覆盖生成式 UI 框架 | https://github.com/rapidpages/awesome-gen-ui · https://github.com/narrowin/awesome-generative-ui |
| frankxai/awesome-motion-design-agent-skills | 只覆盖动效 + agent skills | https://github.com/frankxai/awesome-motion-design-agent-skills |
| awesome-ai-tools/curated-ai-image-video · jianzhnie/awesome-text-to-video | 只覆盖图像/视频，且以商业模型为主 | https://github.com/awesome-ai-tools/curated-ai-image-video |
| wjlgatech/animate-anything | 动画知识地图，偏学习路径而非项目索引 | https://github.com/wjlgatech/animate-anything |

结论：单领域列表已饱和，缺的是**只收开源 + 按创作领域横切 + 条目极轻**的一份。

## 未确认假设

- 开源协议用 MIT（用户未指定；内容型列表也常见 CC0，一句话即可更换）。
- 起始领域骨架：Web/UI 设计、示意图/信息图、动效与动画、图像生成与编辑、视频生成与编辑、3D/空间、音频/音乐、游戏（含资产分区）、文字创作/网文、教育/课标数据（edu）、跨域制作台（studio）；具体划分由维护者调整。
- 结构：领域 = 一级文件夹，条目写在领域 `README.md` 里并按子领域用标题分区；某一类攒到十几条才升成子文件夹。不强制预先分子文件夹。
- 子领域按「它在制作流程里提供什么」切（库 / 参考 / 词汇 / 生成器 / 工作流 / 素材类型），不按作者或仓库切。