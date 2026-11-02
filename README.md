# 项目索引

**寻找有哪些开源项目，能帮 AI（或人 + AI）完成某一类创作**；另辟教育/课标数据分区，收对齐课标的知识图谱与诊断类开源。

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
- 帮 AI / 人+AI 完成创作：出界面、出动效、出示意图、出图、出片、出声音、出文字/网文/短剧前期、出 3D、做游戏等
- **教育 / 课标数据**（[edu/](edu/)）：对齐课标或教材的开源知识图谱、题库、诊断与学习路径数据（及可复现浏览工具）
- 少量**平台能力**（不是仓库，如浏览器原生 API）——必须标 `（平台能力，非仓库）`
- **跨域制作台**（一套 skill/MCP 打通多种媒质）放 [studio/](studio/)；各单模态领域可挂回链，详情只维护一份

不收：

- 闭源产品、商业 SaaS（开源 skill 经商业 API/MCP 出内容的可以收，须在详情页写明依赖与费用）
- 纯模型权重（除非它本身就是可跑的创作工具）
- 只让 AI「写业务代码更好」、跟创作产出无关的 harness / SEO / 安全审计之类（那些另有列表）
- 泛泛的题库爬虫、未开源或无可复现数据的「AI 家教」包装站

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
- [ai-design-skills](web-ui/ai-design-skills.md) — 落地页从零 + Figma 结构化设计 skill 合集
- [dimensional-drawing](web-ui/dimensional-drawing.md) — Apple 风格 UI 组件尺寸图（可选画成短片）
- [scroll-world](web-ui/scroll-world.md) — 品牌 → 卷动飞穿小世界落地页（AI 出片 + scrub，按量计费）
- HTML-in-Canvas（平台能力，非仓库）— 见 [web-ui/README.md](web-ui/README.md)

### [diagram/](diagram/) · 示意图 / 信息图

编辑向技术图与信息图（架构、时序、象限等），不是文生图。

- [diagram-design](diagram/diagram-design.md) — 45 种图型，自包含 HTML + SVG，按品牌出图、避开 Mermaid slop

### [motion/](motion/) · 动效与动画

风格参考、动作词典、GSAP 工程 skill、程序化出片。

- [mg-styles-15](motion/mg-styles-15.md) — 15 种 MG 风格 × 成片 + 提示词 + 源码
- [huashu-art-motion](motion/huashu-art-motion.md) — 艺术动画：风格配方 + 解说语法，代码让画动起来
- [motion-prompt](motion/motion-prompt.md) — 192 个可点名的动作/运镜/UI 效果名词
- [gsap-skills](motion/gsap-skills.md) — GreenSock 官方：教 agent 正确写 GSAP
- [animate](motion/animate.md) — Claude skill：canvas + 程序化配乐 → 确定性 MP4
- [scroll-world](web-ui/scroll-world.md) — 卷动飞穿落地页（主条目在 web-ui；动效相关回链）
- [dimensional-drawing](web-ui/dimensional-drawing.md) — UI 规格图画成片（主条目在 web-ui）

### [video/](video/) · 视频生成与编辑

用代码做片、HTML 渲视频、字幕驱动流水线；Seedance 等模型向提示词与案例库。

- [lemo-opuscar](video/lemo-opuscar.md) — 66 种代码做片风格工具箱（Claude 向）
- [awesome-seedance](video/awesome-seedance.md) — Seedance 已验证提示词 / 复测 / 模板 / Agent Skill（依赖即梦等）
- [hyperframes](video/hyperframes.md) — 写 HTML，确定性渲 MP4，为 agent 设计
- [video-shotcraft](video/video-shotcraft.md) — 产品宣传片：镜头配方 + Remotion，可编辑 / 剪映导出
- [auto-motion](video/auto-motion.md) — SRT → 多镜 MG → 竖屏成片工作流模板
- [scenario-labs/skills](studio/scenario-skills.md) — 文/图生视频、剪辑调色、广告与成片组装等（跨域主条目在 studio/）
- [Easel](studio/easel.md) — 短视频/短剧、剪辑切片与多平台发布等（跨域主条目在 studio/）

### [audio/](audio/) · 音频 / 音乐

- [VoiceStudio](audio/VoiceStudio.md) — 本地语音工作室：克隆、造声、配音、转写、有声书
- [scenario-labs/skills](studio/scenario-skills.md) — 音乐、音效、语音与配乐等（跨域主条目在 studio/）
- [Easel](studio/easel.md) — TTS、配音/克隆与社媒音视频后期等（跨域主条目在 studio/）

### [3d/](3d/) · 3D / 空间

- [text-to-cad](3d/text-to-cad.md) — 自然语言/图稿 → 可制造 CAD（STEP/GLB/STL…）
- [anatomy](3d/anatomy.md) — 概念 → 可交互等轴测「机器图」（SVG / WebGL / 3D）
- [image-blaster](3d/image-blaster.md) — 单图 → 环境 splat + 物体 mesh + 音效（需云 API）
- [img2threejs](3d/img2threejs.md) — 参考图 → 纯代码程序化 Three.js 模型（分 pass 质检）
- [3dviz-pro-max](3d/3dviz-pro-max.md) — 想法 → 可探索 Three.js / Blender 场景（配方 + 抓帧自检）
- [teardown](3d/teardown.md) — 一句话生成可拆解的单文件机器模拟器
- [scenario-labs/skills](studio/scenario-skills.md) — mesh、PBR 纹理、天空盒、可走房间等（跨域主条目在 studio/）

### [game/](game/) · 游戏

做游戏：资产、工作室工作流、引擎向 Skill 等。

- [pixelfx](game/pixelfx.md) — 244 个纯代码像素特效，可导出精灵图（资产）
- [Claude-Code-Game-Studios](game/Claude-Code-Game-Studios.md) — 49 agent + 74 skill 的游戏工作室模板
- [threejs-game-skills](game/threejs-game-skills.md) — Three.js 浏览器游戏：导演 + 玩法/画面/UI/QA（可选外模资产）
- [scenario-labs/skills](studio/scenario-skills.md) — 精灵/瓦片/贴图/天空盒/引擎向资产等（跨域主条目在 studio/）

### [writing/](writing/) · 文字创作

网文连载与短剧改编（叙事向）。

- [oh-story](writing/oh-story.md) — 网文 skill 包：扫榜、拆文、写作、去 AI 味、封面（文件系统记忆）
- [shuohao-skills](writing/shuohao-skills.md) — 短剧前期：小说 → 大纲 / 角色 / 美术 / 剧本 / 站位 / 分镜
- [Easel](studio/easel.md) — 社媒文案、选题策划与去 AI 感等（跨域主条目在 studio/）

### [edu/](edu/) · 教育 / 课标数据

对齐课标的知识图谱、题库与诊断（教学路径底座，不是网文创作）。

- [cn-math-taxonomy](edu/cn-math-taxonomy.md) — 多学科课标知识图谱 + 先修边 + 题库 + 自适应诊断（`CC BY-NC`）

### [studio/](studio/) · 跨域制作台

一套 skill/MCP 打通图像、视频、音频、3D、游戏资产等；另有社媒运营闭环工作台（详情只在这里维护一份；各单模态目录有回链）。

- [scenario-labs/skills](studio/scenario-skills.md) — Scenario MCP：图/视频/音频/纹理/天空盒/3D/自定义训练 + 本机 DCC 专家组
- [Easel](studio/easel.md) — 社媒工作台：发现 → 策划 → 创作 → 多平台发布 → 归因（OpenClaw）

### [image/](image/) · 图像生成与编辑

- [handraw-style](image/handraw-style.md) — 手绘风格编号画廊 + 双语生图提示词 Skill（依赖外模出图）
- [RuiC-PoseAtlas](image/RuiC-PoseAtlas.md) — 姿态 / 衣装 / 人像三图鉴，作 AI 作图视觉参考
- [scenario-labs/skills](studio/scenario-skills.md) — 文生图、改图、产品图、品牌、分镜静帧等（跨域主条目在 studio/）
- [Easel](studio/easel.md) — 社媒卡片、海报、信息图与 AI 生图等（跨域主条目在 studio/）

像素特效等游戏资产见 [game/](game/)。

## 贡献

1. 确认符合[收录标准](#收录标准)。
2. 在对应领域的 `README.md` 按格式加一行。
3. 建议同时加一篇详情页（参考 [motion/animate.md](motion/animate.md)）：是什么、安装/用法、限制、相关项目。
4. 或开 issue 丢链接 + 一句话说明它帮 AI 做什么。

PR / issue 都欢迎。领域划分不对也可以直接改文件夹标题或提建议。

## 协议

本仓库文档与索引内容采用 [MIT](LICENSE)。各收录项目仍遵循其自己的开源协议（条目里已标注）。
