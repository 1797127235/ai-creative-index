# 3dviz-pro-max

[← 返回 3D / 空间](./README.md) · [仓库](https://github.com/viettranx/3dviz-pro-max) · [站点](https://3dviz.dev) · [安装](https://github.com/viettranx/3dviz-pro-max/blob/main/docs/installation.md) · [提示词画廊](https://github.com/viettranx/3dviz-pro-max/blob/main/docs/prompt-gallery.md)

`MIT` · Agent skill · 想法 → 可探索的 Three.js / Blender 场景 · Claude Code + Codex

## 它是什么

创意 **3D 可视化** skill：把一句话意图做成值得逛的场景——定视觉方向、建模对象规则、加交互，再**真跑渲染并抓帧自检**，而不是空口描述画面。事实性说明要有来源；会动的装饰不等于仿真。

开场不必先选渲染器或填规格，例如：

> Use 3dviz-pro-max to build a small fantasy village I can explore. Choose a distinctive art direction, add a few moving creatures, and inspect the result.

规模会随仓更新；大致含 200+ recipes、400+ knowledge、20+ 已验证 kit、数十个可跑 studies，覆盖环境、产品装配、建筑剖切、解剖/生理、数学场、机器人、天文等二十多个方向。

## 和同类差在哪

| | [img2threejs](./img2threejs.md) | 3dviz-pro-max |
|---|---|---|
| 输入 | 参考图 | 意图 / 学科可视化需求 |
| 产物 | 程序化物体 `THREE.Group` 工厂 | 可探索场景（模板 / kit / Blender 烘焙） |
| 强项 | 分 pass 对照参考图质检 | 配方库 + 证据抓帧 + 多学科方向 |

| | [anatomy](./anatomy.md) / [teardown](./teardown.md) | 3dviz-pro-max |
|---|---|---|
| 范围 | 单类「机器图 / 可拆模拟器」 | 通用可视化 skill + 可检索知识库 |

## 安装

权威内容是整份 `skills/3dviz-pro-max/`（勿只拷 `SKILL.md`）。

```sh
git clone https://github.com/viettranx/3dviz-pro-max.git

# Claude Code：个人技能目录（可用 symlink）
ln -s "$(pwd)/skills/3dviz-pro-max" ~/.claude/skills/3dviz-pro-max

# 或 marketplace / plugin
# /plugin marketplace add viettranx/3dviz-pro-max
# /plugin install 3dviz-pro-max@3dviz-pro-max
# claude --plugin-dir /path/to/3dviz-pro-max
```

Codex：把同一文件夹拷进其认可的 skill 目录。模板在 `templates/`，需先拷到自己的项目再 `pnpm install`（不要在 skill 目录里装依赖）。

装好后先让 agent 认 skill、读入口，再跑场景提示词并在运行时看帧。

## 限制

- 需要能写/跑 Three.js（或接 Blender kit）的 coding agent；抓帧自检依赖本机/浏览器 GPU 路径。
- Marketplace 全链路（更新/卸载）与 Claude App 上传限制以仓库 `docs/compatibility.md` 为准，勿把「能装上」当成「已证明能渲」。
- 展示用 demo 有的是 skill 诞生前的历史素材；判断能力以 kit 抓帧与 evidence 为准。

## 相关

- [img2threejs](./img2threejs.md) — 图 → 程序化模型。
- [image-blaster](./image-blaster.md) — 图 → 云端 splat 场景。
- [scenario-labs/skills](../studio/scenario-skills.md) — 云端 mesh / 天空盒 MCP，不是本仓这种配方驱动可视化。
