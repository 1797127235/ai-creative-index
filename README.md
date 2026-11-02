# 项目索引

**寻找有哪些开源项目，能帮 AI（或人 + AI）完成某一类创作。**

## 怎么读

| 你想… | 去哪 |
|---|---|
| 按创作类型扫一圈 | 下面的[目录](#目录)，或点进对应领域文件夹 |
| 看某个项目怎么装、怎么跑、有什么坑 | 点项目名进**详情页**（每个仓库一篇） |
| 自己加一条 | 见[贡献](#贡献) |

结构约定：

- **领域 = 一级文件夹**（`web-ui/`、`motion/`…）
- 领域 `README.md` 用标题分子领域（风格库 / 生成器 / 工作流…）

## 收录标准

收：

- 开源，能自己跑起来（或有明确可复现的用法）
- 帮 AI / 人+AI 完成创作：出界面、出动效、出图、出片、出声音、出 3D/游戏资产等
- 少量**平台能力**（不是仓库，如浏览器原生 API）——必须标 `（平台能力，非仓库）`

不收：

- 闭源产品、商业 SaaS
- 纯模型权重（除非它本身就是可跑的创作工具）
- 只让 AI「写业务代码更好」、跟创作产出无关的 harness / SEO / 安全审计之类（那些另有列表）

## 条目格式

索引里一行：

```md
- [项目名](./详情页.md) — 一句话说清楚它帮 AI 做什么。`协议`
```

不写 star 数（会变）。详情页一般包括：它是什么、怎么装/怎么用、限制、和同类的关系。

## 目录

### [web-ui/](web-ui/) · 网页与 UI 设计

给 coding agent 审美和界面工艺，少出「AI 默认落地页」。

- [impeccable](web-ui/impeccable.md) — 设计词汇 + 审稿 + 确定性 slop 检测
- [hallmark](web-ui/hallmark.md) — 50 主题 + 浏览器 lint 的反 AI 味建页 skill
- [taste-skill](web-ui/taste-skill.md) — 艺术指导 + 真图 + 浏览器自检
- [jakubkrehel/skills](web-ui/jakubkrehel-skills.md) — 排版 / 色 / 无障碍 / 布局等工艺合集
- HTML-in-Canvas（平台能力，非仓库）— 见 [web-ui/README.md](web-ui/README.md)

### [motion/](motion/) · 动效与动画

风格参考、动作词典、程序化出片。

- [mg-styles-15](motion/mg-styles-15.md) — 15 种 MG 风格 × 成片 + 提示词 + 源码
- [motion-prompt](motion/motion-prompt.md) — 192 个可点名的动作/运镜/UI 效果名词
- [animate](motion/animate.md) — Claude skill：canvas + 程序化配乐 → 确定性 MP4

### [video/](video/) · 视频生成与编辑

用代码做片、HTML 渲视频、字幕驱动流水线。

- [lemo-opuscar](video/lemo-opuscar.md) — 66 种代码做片风格工具箱（Claude 向）
- [hyperframes](video/hyperframes.md) — 写 HTML，确定性渲 MP4，为 agent 设计
- [auto-motion](video/auto-motion.md) — SRT → 多镜 MG → 竖屏成片工作流模板

### [audio/](audio/) · 音频 / 音乐

- [VoiceStudio](audio/VoiceStudio.md) — 本地语音工作室：克隆、造声、配音、转写、有声书

### [3d/](3d/) · 3D / 空间

- [text-to-cad](3d/text-to-cad.md) — 自然语言/图稿 → 可制造 CAD（STEP/GLB/STL…）
- [teardown](3d/teardown.md) — 一句话生成可拆解的单文件机器模拟器

### [game-assets/](game-assets/) · 游戏素材与制作流

- [pixelfx](game-assets/pixelfx.md) — 244 个纯代码像素特效，可导出精灵图
- [Claude-Code-Game-Studios](game-assets/Claude-Code-Game-Studios.md) — 49 agent + 74 skill 的游戏工作室模板

### [image/](image/) · 图像生成与编辑

暂无收录（文生图、改图、抠图、超分等）。像素特效见 [game-assets/](game-assets/)。

## 贡献

1. 确认符合[收录标准](#收录标准)。
2. 在对应领域的 `README.md` 按格式加一行。
3. 建议同时加一篇详情页（参考 [motion/animate.md](motion/animate.md)）：是什么、安装/用法、限制、相关项目。
4. 或开 issue 丢链接 + 一句话说明它帮 AI 做什么。

PR / issue 都欢迎。领域划分不对也可以直接改文件夹标题或提建议。

## 协议

本仓库文档与索引内容采用 [MIT](LICENSE)。各收录项目仍遵循其自己的开源协议（条目里已标注）。
