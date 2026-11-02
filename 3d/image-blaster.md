# image-blaster

[← 返回 3D / 空间](./README.md) · [仓库](https://github.com/neilsonnn/image-blaster)

`MIT` · Claude skill 工作流 · 单图 → 可探索 3D 环境 + mesh + 音效 · 依赖 World Labs / FAL 等 API

## 它是什么

把一张图「炸」成可起步的 3D 场景资产：用 Claude skills 串起 World Labs、FAL（及可选图像编辑、ElevenLabs）。作者称约 **5 分钟内**可从单图到带 mesh 的环境，适合给引擎 / DCC / Web 3D 起草稿，而不是最终成片。

默认从输入图生成：

1. **动态物体**的 3D 模型（`.glb` / `.obj`）
2. **静态环境**的 Gaussian splat（`.spz`）
3. 环境循环氛围音 + 物体物理音效（`.mp3`）

产物可嵌进 Unity / Unreal / Godot、Blender 等 DCC、Three.js / Electron。

## 流水线用到的模型

| 能力 | 模型 / 通道 |
|---|---|
| 可探索环境 | World Labs `marble-1.1` |
| 源图清理 / 净板 / 物体参考图 | 默认 `nano-banana`；可改偏好 `gpt-image-2` |
| 物体 mesh | FAL 上的 Hunyuan 3D（`hunyuan-3d`） |
| 音效 | ElevenLabs SFX |

Hunyuan 常用参数（仓库默认）：`--face-count` 默认 `50000`、`--enable-pbr true`、`--generate-type Normal`（另有 LowPoly / Geometry）、LowPoly 时 `--polygon-type triangle`。

## 怎么跑

```sh
git clone https://github.com/neilsonnn/image-blaster
cd image-blaster
claude   # 需已安装 Claude Code
```

把 **World Labs** 与 **FAL** 的 API key 交给 Claude；把图放进 `input/`，然后说：

> blast it and confirm each step with me

适合：关卡概念、童年房间、机器人训练场、勘景参考、建筑效果图起稿等。

开发提示：从 `.claudeignore` 去掉 `/app`，可让 Claude 改仓库自带的 React viewer。

## 限制

- **不是纯本地**：要多家云 API（至少 World Labs + FAL；音效/改图另算），有费用与账号门槛。
- 绑 **Claude Code** 工作流；产出是跳板资产，精度/拓扑未必直接上线级。
- Gaussian splat + 分物体 mesh 的管线，和 [text-to-cad](./text-to-cad.md) 的精确 CAD、[anatomy](./anatomy.md) / [teardown](./teardown.md) 的讲解向机器图不是一类东西。
- 音效走 ElevenLabs，没配 key 时环境音/物理音可能缺席。

## 相关

- [img2threejs](./img2threejs.md) — 同是「从图到 3D」，但走程序化 Three.js 代码，不靠云端 splat/mesh API。
- [text-to-cad](./text-to-cad.md) — 自然语言 → 可制造 CAD，偏工程件。
- [teardown](./teardown.md) / [anatomy](./anatomy.md) — 讲解/隐喻向可交互图，不从照片重建场景。
- [game/](../game/) — 若目标是进游戏管线，炸完的资产可再交给引擎侧工作流。
- [audio/VoiceStudio](../audio/VoiceStudio.md) — 本地语音工作室；本仓库音效默认走 ElevenLabs API。
