# Easel

[← 返回跨域制作台](./README.md) · [仓库](https://github.com/ZJU-REAL/Easel) · [项目页](https://zju-real.github.io/Easel/) · [能力地图](https://github.com/ZJU-REAL/Easel/blob/main/docs/skill-function-mapping.md)

`Apache-2.0` · 浙大 REAL / OpenDCAI · OpenClaw Agent · 社媒内容工作台 · 113+ Skills

## 它是什么

面向社交媒体创作者的开源工作台：把 **OpenClaw Agent、账号画像、内容技能和真实媒体工具**接在一起，让 Agent 不只给建议，而是把内容做出来、归档，并可预览后发布到多平台。

五层连续工作流：**发现**热点 → **策划**选题/日历 → **创作**图文音视频 → **发布**到已登录账号 → **归因**把表现写回画像。一份素材可改写成小红书卡片、短视频、知乎长文等不同平台形态。

和 [scenario-labs/skills](./scenario-skills.md) 同属跨域：那边偏 **MCP 出媒资**；这边偏 **社媒运营闭环**（画像、日历、发布、复盘）。

## 已落地能力（摘要）

| 层 | 能干什么 |
|---|---|
| 发现 | 热搜聚合、垂类趋势、竞品、节日日历、RSS / 自建采集源 |
| 策划 | 账号定位与人设、选题矩阵、标题 Hook、分镜/大纲、内容日历 |
| 文字与视觉 | 社媒文案、笔记/长文、去 AI 感、金句卡/知识卡、海报、信息图、AI 生图与批处理 |
| 音频与视频 | TTS/配音/克隆、剪辑切片、字幕、AI 视频与短剧、卡点、横竖版等（需 FFmpeg 等） |
| 发布与归因 | 质量门禁、多平台格式适配；小红书、抖音、快手、知乎、B 站、视频号、公众号、X、掘金、头条等登录发布与数据回收 |

完整技能表见仓库 `docs/skill-function-mapping.md`。推荐用 **Web 前端**（会话、素材、画像、内容库、发布中心），比纯 CLI 完整。

## 安装

环境：Python **3.10+**、`venv`、`git`；安装器会检查 Node.js（注意版本兼容说明）、尽量装 FFmpeg / Playwright Chromium。

```bash
git clone https://github.com/ZJU-REAL/Easel.git
cd Easel
bash setup.sh          # macOS / Linux
# Windows：.\setup.ps1
```

装完后：

```bash
source .venv/bin/activate   # Windows：.venv\Scripts\activate
easel doctor
easel web                   # http://localhost:7860
```

**模型 API Key 在浏览器「设置 → 模型配置」里填**（也可用 `.env`）。支持 Anthropic / OpenAI 及兼容接口。安装器用独立的 `easel` OpenClaw profile，不覆盖已有 `~/.openclaw/`。

## 在本索引里的挂法

**详情与主条目在本页 / [studio/](./README.md)。** 下列领域只记社媒向产出回链：

- [writing/](../writing/) — 文案、长文、小说向、去 AI 感与选题策划
- [image/](../image/) — 卡片、海报、信息图、AI 生图与封面
- [video/](../video/) — 短视频/短剧、剪辑切片、字幕与成片
- [audio/](../audio/) — TTS、配音、克隆、配乐与音视频后期相关

## 限制

- **LLM 与生图/视频外模按账号计费**；本仓开源 ≠ 调用免费。
- 浏览器自动登录/发布依赖 Playwright；**小红书自动发布有风控风险**，官方建议预览后人工确认再发。
- FFmpeg / Chromium 缺失时，音视频与浏览器发布能力会降级，安装未必失败。
- VS Code Remote 需自行端口转发 `7860`；勿把无认证工作台裸露公网。

## 相关

- [scenario-labs/skills](./scenario-skills.md) — 媒资生成 MCP 台，无社媒发布闭环。
- [handraw-style](../image/handraw-style.md) — 手绘风格编号提示词，可作视觉输入之一。
- [oh-story](../writing/oh-story.md) / [shuohao-skills](../writing/shuohao-skills.md) — 网文/短剧专用 skill，不是多平台运营台。
