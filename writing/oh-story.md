# oh-story

[← 返回文字创作 / 网文](./README.md) · [仓库](https://github.com/zenstory-ai/oh-story-claudecode) · [主页](https://zenstory.ai/zh/oh-story)

`MIT` · 14 个 Agent Skills · 中文网文全流程 · 文件系统当记忆 · 确定性写前/写后检查

## 它是什么

**Oh Story**（仓库名 `oh-story-claudecode`）把网文流水线装进你正在用的编程 Agent：扫榜选材 → 拆爆款 → 搭大纲写正文 → 去 AI 味 → 封面。长篇短篇都有。

- **用文件当记忆**：设定、大纲、正文、追踪分文件维护；换会话或压缩上下文后，从磁盘恢复进度、伏笔和未完承诺。
- **确定性门禁**：长篇写前查细纲与追踪，写后查截断、工程词、常见 AI 句式；支持 hooks 的宿主可自动跑。
- **模型就是 Agent 自己的模型**：不另配 GPU/本地大模型；本地只跑 Node/Python 检查脚本。唯一例外是封面成图可走 GPT-Image-2。

面向起点、番茄、晋江、七猫、知乎盐言等。口号：**套路 = 确定性的情绪满足**——作者定方向，Agent 按确认后的方案推进。

## Skills（先会这几个就够写）

装好后跑一次 `story-setup`，之后长篇用 `story-long-write`、短篇用 `story-short-write`，写完 `story-deslop`；拿不准就 `/story` + 一句话。

| Skill | 命令（节选） | 干什么 |
|---|---|---|
| `story-setup` | `/story-setup` `/准备写书` | 部署 hooks / agents / 参考资料 |
| `story-long-write` | `/story-long-write` `/写长篇` | 大纲、设定、正文、作者偏好 |
| `story-short-write` | `/story-short-write` `/写短篇` | 情绪、反转、精修 |
| `story-deslop` | `/story-deslop` `/去AI味` | 检测并清 AI 写作痕迹 |
| `story-long-analyze` / `story-short-analyze` | `/长篇拆文` `/短篇拆文` | 拆节奏、爽点、反转等 |
| `story-long-scan` / `story-short-scan` | `/长篇扫榜` `/短篇扫榜` | 市场/风口扫榜 |
| `story-import` | `/story-import` `/导入小说` | 已有书稿 → 可续写工程 |
| `story-review` | `/story-review` `/审查` | 多视角审读 + 平台口味 |
| `story-publish` | `/story-publish` | 整理建书资料（目前偏番茄） |
| `story-cover` | `/story-cover` `/封面` | 封面提示词或成图 |

典型链路：长篇 `扫榜 → 拆文 → 写作`；短篇同理。共用 setup / deslop / review / cover。

内部还有架构、写手、一致性等子 Agent 分工；支持项目 Agent 的宿主由 setup 部署，**部署后要新开会话**。

## 安装

```bash
npx skills add zenstory-ai/oh-story-claudecode -y -g
```

去掉 `-g` 则只装当前目录。更新再跑同一条。

然后在**写作项目根**：

```text
/story-setup          # Codex：$story-setup
```

再**新开会话**。各宿主差异与排错见仓库 `docs/hosts.md`。适配：Claude Code、Codex、Antigravity、OpenCode、ZCode、OpenClaw、Reasonix 等。

## 限制

- 强绑定「编程 Agent + 项目文件」；不是独立网文 SaaS 客户端（同组织另有 [zenstory](https://github.com/zenstory-ai/zenstory) 工作台，偏产品侧）。
- 扫榜/拆文依赖网络与公开页可读性，平台改版会影响效果。
- 封面成图可能要图像 API / Codex 用量；纯本地可只出提示词。
- 去 AI 味以本地 lint + 读感为准；外部检测仅参考。
- 输出质量仍看你用的模型和你是否认真过门禁；skill 管流程与连续性，不保证「必火」。

## 相关

- [shuohao-skills](./shuohao-skills.md) — 小说 → 短剧改编与分镜，不是网文连载写作。
- 同组织还可看（未收录进本索引前可自行评估）：`drama-skills`（短剧/漫剧）、`novel-to-game`、`video-recap-skills`。
- 视觉封面若要单独做图，也可搭配 [image/](../image/)（目前待收录）或其它生图工具；本包已带 `story-cover`。
