# img2threejs

[← 返回 3D / 空间](./README.md) · [仓库](https://github.com/img2threejs/img2threejs) · [Live 画廊](https://img2threejs.io/)

`Apache-2.0` · Agent skill · 参考图 → 纯代码程序化 Three.js 模型 · 分 pass 质检，可动画

## 它是什么

把参考图里的物体（或角色）重建成 **只用代码写的** Three.js 模型：图元 + 程序化材质/几何，产出可运行的 `THREE.Group` 工厂（TypeScript），带 pivot / socket 等运行时层级，方便接动画——**不是**摄影测量、抽 mesh、也不是下载素材包。

管线强制分阶段，禁止一锤子出 mesh：

1. 每次开干 / 续跑 / 纠错前先跑 `forge/next.py`（以 `.img2threejs/state.json` 为清单权威）
2. 校验图是否适合做 3D → 评估类别与复杂度 → 先写 `qualityContract`
3. 出 sculpt spec（层级、材质、灯光、枢轴、动作锚点）
4. 按 pass 构建：blockout → 结构 → 形体 → 材质 → 灯光 → 交互 → 优化
5. 每 pass 截图对照参考；身份特征错了即使总分好看也判失败

单图看不到背面、不能保证精确几何——要显式说明是 stylized / 近似，而不是装确定。

## 和 image-blaster 差在哪

| | [image-blaster](./image-blaster.md) | img2threejs |
|---|---|---|
| 路径 | 云 API 生成 splat + mesh + 音效 | Agent 写程序化 Three.js 代码 |
| 产物 | `.spz` / `.glb` 等场景资产 | 浏览器可跑的 TS 模型工厂 |
| 依赖 | World Labs、FAL 等密钥 | coding agent + 本地 forge（Python） |

## 安装与用法

```sh
npx --yes img2threejs@latest install   # 链到本机各 agent
npx --yes img2threejs@latest doctor    # 看是否 managed
```

可选插件脚手架（领域扩展，如角色 / CS2 等）：

```sh
npx --yes @img2threejs/img2@latest install --yes
npx --yes @img2threejs/img2@latest plugins
```

建议**一个 checkout + symlink** 给 Claude / Codex，避免两套代码漂移。Claude Code、Codex、OpenCode、Hermes 等均可；vision / 浏览器工具用宿主自带的。

状态门禁示例：

```sh
python3 forge/state.py init --state .img2threejs/state.json --reference <img> --profile <generic|character|…> --spec object-sculpt-spec.json
python3 forge/next.py --state .img2threejs/state.json
```

画廊：[img2threejs.io](https://img2threejs.io/) — 每个 demo 都是生成代码在浏览器里跑。

## 限制

- 强依赖 **coding agent 的视觉与迭代**；pass 多、故意省 token，但复杂对象仍会耗会话与时间。
- 单图无法保证隐面与百分百像；角色 likeness 有单独路径，仍会报区域置信度。
- 默认产物是 **Three.js 代码模型**；导出其它格式是建完之后的可选终端变换，不是第二条建模路。
- 领域插件（室内、CS2、环境等）有的要额外授权，别默认全装。

## 相关

- [image-blaster](./image-blaster.md) — 单图 → 云端场景资产（splat/mesh/SFX）。
- [text-to-cad](./text-to-cad.md) — 可制造 CAD，不是网页 Three 程序化模型。
- [anatomy](./anatomy.md) — 概念隐喻等轴测图，不是对照片重建物体。
- [game/](../game/) — 程序化道具可再进游戏侧工作流。
