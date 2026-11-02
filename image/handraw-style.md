# handraw-style

[← 返回图像生成与编辑](./README.md) · [仓库](https://github.com/yang0/handraw-style) · [英文 README](https://github.com/yang0/handraw-style/blob/master/README_en.md)

`MIT`（带署名要求）· 手绘风格编号画廊 · 双语生图提示词 Skill

## 它是什么

给 coding agent 用的**手绘 / 写实风格提示词库**：不会描述画风、排不好社媒构图时，选编号（或让 Skill 自荐），拿到实测过的中英双语提示词，再贴进 Midjourney、Flux、GPT Image、SD 等出图。

规模大致为：**365+** 种视觉风格、**170** 种排版图型、**36** 种经典单色主题。另有文章/视频封面、长文批量插图回填、摄影企划等进阶模式。

视频制作已拆到独立仓 `handraw-video`；本仓保留静态图与**视频封面**（静态）设计。

## 库怎么组织

| 资源 | 内容 |
|---|---|
| `STYLES.md`（及 `_en`） | 风格图鉴；支持 `FA`–`FI` 分类编号与 `001–365` 传统编号 |
| `LAYOUTS.md` | 排版图型：社媒卡、数据信息图、漫画分镜、IP、电商等 |
| `COLORS.md` | 单色主题（克莱因蓝、鼠尾草绿、爱马仕橙…） |
| 本地画廊 | `skills/handraw-style-prompter/gallery/index.html` 可离线检索放大 |

可 **纯图** / **图文** 双模式切换：纯图只出插画；图文让文案参与构图（海报、金句卡）。

## 怎么用

装好 Skill 后常见说法：

- 零门槛：`帮我生成猫咪在窗台晒太阳的治愈插画提示词，你帮我选风格和主题色`
- 指定编号：`图型：SC-001，风格：FB-006，主题色：C-01，主题：秋天的第一杯奶茶`
- 海报：`请帮我出海报提示词，主题：秋分`
- 封面 / 长文配图 / 摄影企划：把文章、字幕或「摄影写真模式，拍摄类型：情侣」丢给 Skill

默认只产提示词；你明确说「生图 / 全自动出图」时，再按客户端能力调用生图工具。未深度标定的模型会走参考图垫图兜底。

## 安装

把仓库地址发给 Codex / 兼容 skills 的 agent，例如：

> 帮我安装这个 Skill：https://github.com/yang0/handraw-style

本地跑图库索引等 Python 脚本时：`python -m pip install -r requirements.txt`（Pillow、PyYAML；Python ≥ 3.10）。只读画廊与规范不必装依赖。

## 限制

- **不包含生成模型**：出图依赖你本机/平台的模型权限与费用；本包交付的是提示词与风格资源。
- 协议是 MIT **附加署名**：二次开发或产品使用须保留作者 yang0 与原仓库链接。
- 视频成片不在本仓；需要视频向能力另找 `handraw-video` 或本索引 `video/` 条目。

## 相关

- 同目录跨域出图：[scenario-labs/skills](../studio/scenario-skills.md)（MCP 直接出图改图）。
- 确定性 HTML/SVG 示意图（不调生图模型）：[diagram-design](../diagram/diagram-design.md)。
- 视频侧「编号模板 → 提示词」对照：[awesome-seedance](../video/awesome-seedance.md)。
