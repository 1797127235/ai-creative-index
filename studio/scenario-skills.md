# scenario-labs/skills

[← 返回跨域制作台](./README.md) · [仓库](https://github.com/scenario-labs/skills) · [skills.sh](https://www.skills.sh/scenario-labs/skills) · [Scenario](https://scenario.com) · [MCP 文档](https://mcp.scenario.com/docs)

`MIT` · Agent Skills + Scenario MCP · 图像 / 视频 / 音频 / 3D / 游戏资产 · 本机 DCC 专家组

## 它是什么

教 Claude Code、Cursor、Codex、Copilot 等 coding agent，经 **[Scenario MCP](https://mcp.scenario.com)** 做出生产向内容：先发现模型与 schema、再报价、再生成，并尽量保持角色与品牌一致。覆盖游戏、娱乐和其它创意垂类。

仓库里其实是**两大块**：

1. **Scenario 技能（默认主路径）** — 需要连上 Scenario MCP 与账号；选型、定价、一致性、质检、工作流作者ing 等都在这里。  
2. **Expert tools（本机 DCC / 引擎）** — 不依赖 Scenario MCP；驱动已安装的 ZBrush、Blender、Maya、Unreal、Unity、Godot、Roblox 等，从教程与官方文档蒸馏成的专家 skill 族。

Skill 格式遵循 [Agent Skills](https://agentskills.io)。**skill 仓库开源；经 MCP 的生成走 Scenario 云端（有账号与费用）。**

## 能力地图（按媒质）

| 方向 | 代表 skill（节选） | 能干什么 |
|---|---|---|
| 入门 | `scenario` | 接 MCP；发现 → schema → 跑 → 等 → 展示 → 下载 |
| 找方向 | `scenario-inspiration` | 参考猎取、A/B 概念、情绪板 |
| **图像** | `scenario-image`、`multi-reference`、`product-shots`、`brand-kit`、`image-editing`、`text-overlay`、`storyboards`、`thumbnails` | 文生图/改图、多参考合成、产品图、品牌套件、遮罩编辑、完美字卡、分镜页、封面 |
| **游戏美术** | `game-assets`、`sprite-animation`、`side-view-game-kit` | 精灵/图标/瓦片/像素风、动画表、横版全套 |
| **纹理 / 天空盒** | `scenario-textures`、`scenario-skyboxes` | 无缝/PBR 贴图、360 天空盒与引擎导出 |
| **3D** | `scenario-3d`、`video-to-motion`、`blender`、`patina-retexture`、`orbit-views`、`walkable-room`、`meshy`/`rodin`/`sparc3d` 等 | 文/图生 mesh、动捕、Blender MCP、PBR 重贴图、可走房间、多 3D 后端 |
| **视频** | `scenario-video`、`video-editing`、`color-grade`、`seedance-*`、`video-ads`、`video-assembly`、`caption-studio`… | 文/图生视频、剪辑调色、分镜连戏、广告、成片组装与字幕 |
| **音频** | `scenario-audio`、音乐/ElevenLabs 等模型 skill | 配乐、音效、人声/语音、给视频配乐 |
| 一致性与训练 | `consistency`、`identity-library`、`model-training`、`quality-gate`、`refine-loop` | 角色/品牌一致、自定义训练、质检与精修环 |
| 本机专家组 | `dcc/zbrush|blender|maya`、`game-engines/unreal|unity|godot|roblox` | 驱动本机软件，不经 Scenario MCP |

按岗位/目标的一键安装见仓库 [INSTALL.md](https://github.com/scenario-labs/skills/blob/main/INSTALL.md)。

## 安装

```bash
# 交互菜单（按主题勾选；默认不预选）
npx skills add scenario-labs/skills

# 只装核心
npx skills add scenario-labs/skills --skill scenario

# 装全套 Scenario 技能（不含专家组）——命令很长，以仓库 README 为准
```

接 MCP：

```bash
claude mcp add --transport http scenario https://mcp.scenario.com/mcp
```

或在任意 MCP 客户端填 `https://mcp.scenario.com/mcp`，用 Scenario 账号 OAuth，或 [API key](https://app.scenario.com/settings/api)。更新：`npx skills update` 或重跑原来的 `add`。

## 在本索引里的挂法

**详情与主条目在本页 / [studio/](./README.md)。** 下列领域只记「能覆盖什么」，避免拆成多份重复详情：

- [image/](../image/) — 文生图、改图、产品图、品牌、分镜静帧…
- [video/](../video/) — 文/图生视频、剪辑、调色、广告与成片组装…
- [audio/](../audio/) — 音乐、音效、语音与配乐…
- [3d/](../3d/) — mesh、天空盒相关导出、可走房间、Blender/动捕…
- [game/](../game/) — 精灵、贴图、瓦片、横版套件、引擎向导出…

## 限制

- **Scenario 路径依赖商业平台**：要账号与额度；skill 开源 ≠ 生成免费。
- 技能数量极大，按需装；全量安装命令易过时，以仓库 README / INSTALL 为准。
- Expert tools 需要本机已装对应 DCC/引擎，和 MCP 生成是两套前置。
- 和本索引里单模态开源工具（[hyperframes](../video/hyperframes.md)、[VoiceStudio](../audio/VoiceStudio.md)、[img2threejs](../3d/img2threejs.md) 等）互补：那边偏本地/专用管线，这边偏统一路由与一致性。

## 相关

- [image-blaster](../3d/image-blaster.md) — 单图炸场景（World Labs/FAL），不是全媒质台。
- [img2threejs](../3d/img2threejs.md) — 程序化 Three.js 代码重建。
- [Claude-Code-Game-Studios](../game/Claude-Code-Game-Studios.md) — 游戏制作流程编排，不经 Scenario 出图。
