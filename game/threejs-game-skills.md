# threejs-game-skills

[← 返回游戏](./README.md) · [仓库](https://github.com/majidmanzarpour/threejs-game-skills)

`MIT` · Codex / Claude Code · Three.js 浏览器游戏 Skill 包 · 导演路由 9 支专精

## 它是什么

装好后让 agent 用 **`threejs-game-director`**：自动调度玩法、AAA 向画面、UI、资产生成、音频、调试与发布验证，不必手动点每个专精 skill。面向**可玩、打磨过的 Three.js 浏览器游戏**（示例有竞速、斯诺克、太空狗斗等 Netlify demo）。

包内含各 `SKILL.md`、参考资料、助手脚本，以及相关 skill 里的 **Vite + TypeScript + Three.js** 脚手架。成局带确定性测试钩子、播种 RNG、Playwright 冒烟 / 视觉回归 / bot 试玩模板，方便 agent 端到端自检。

**不强制付费模型或 API Key**；缺密钥时导演可走程序化/本地资产并说明限制。

## 九支 Skill（节选职责）

| Skill | 职责 |
|---|---|
| `threejs-game-director` | 总入口：范围、质量条、专精路由、连续性笔记、证据 |
| `threejs-gameplay-systems` | 可玩循环、架构、输入、相机、物理、手感 |
| `threejs-aaa-graphics-builder` | 模型/材质/灯光/VFX/渲染打磨与预算 |
| `threejs-game-ui-designer` | HUD、菜单、安全区、触控与字号 |
| `threejs-debug-profiler` | 黑屏、性能、draw call、移动端问题 |
| `threejs-qa-release` | 生产构建、截图/画布像素、发布风险 |
| `threejs-3d-generator` | Tripo：文/图生 3D、GLB/FBX 等（需 `TRIPO_API_KEY`） |
| `threejs-image-generator` | Gemini：概念图、贴图、天空、GUI 图（需 `GEMINI_API_KEY`） |
| `threejs-audio-generator` | ElevenLabs：SFX/配乐/TTS 等（需 `ELEVENLABS_API_KEY`） |

## 安装与用法

```bash
npx skills add majidmanzarpour/threejs-game-skills --skill '*' -a claude-code -g -y
npx skills add majidmanzarpour/threejs-game-skills --skill '*' -a codex -g -y

# 或从 clone：./install.sh --claude | --codex | --all
```

空目录或已有 Three.js 工程里说清目标，并点名导演，例如：

> Use threejs-game-director to build a premium futuristic tower defense game from scratch. …

Claude Code：`/threejs-game-director` 或自然语言点名；Codex：`$threejs-game-director`。密钥只放本机环境变量，勿写进浏览器游戏代码；可用包内 `probe_asset_credentials.sh` 探测。

## 限制

- 专攻 **Three.js 浏览器游戏**，不是 Godot/Unity 通用工作室模板。
- 外模 3D/图/音按各云厂商计费；无 Key 也能做，但资产会偏程序化。
- 宿主是否支持子 agent / 异步委托取决于 Codex 或 Claude Code 本身，装 skill 不会改模型设置。

## 相关

- [Claude-Code-Game-Studios](./Claude-Code-Game-Studios.md) — 多引擎「工作室职级」模板；本仓是 Three.js 可玩闭环。
- [pixelfx](./pixelfx.md) — 像素特效素材库。
- [3dviz-pro-max](../3d/3dviz-pro-max.md) / [img2threejs](../3d/img2threejs.md) — Three.js 可视化或模型重建，不是完整游戏 QA 流。
- [scenario-labs/skills](../studio/scenario-skills.md) — 跨域出游戏美术资产。
