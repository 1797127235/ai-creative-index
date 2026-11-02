# 3D / 空间

[← 返回目录](../README.md)

按「它提供什么」分区。一行说得清就留在本页；要写第二段（怎么跑、限制、复刻流程）就单独开文件，本页那条指向它。

## CAD 生成

- [text-to-cad](./text-to-cad.md) — 给 agent 的本地 CAD 工作流：自然语言/图稿 → build123d 脚本 → STEP/GLB/STL/3MF，顺带可做工程图、可制造性检查和打样对接。`MIT`

## 等轴测图解

- [anatomy](./anatomy.md) — 把抽象概念发明成一台会运转的实体，再画成可交互等轴测图（SVG，可选 WebGL / 3D）；读数与零件运动同源。`MIT`

## 图像 → 场景

- [image-blaster](./image-blaster.md) — 单图经 Claude + World Labs / FAL 等炸成可探索环境：动态物体 mesh、静态 Gaussian splat、氛围与物理音效。`MIT`

## 图像 → 程序化 Three.js

- [img2threejs](./img2threejs.md) — 参考图 → 分 pass 质检的纯代码 Three.js 模型（可动画）；重建靠写代码，不是摄影测量或抽 mesh。`Apache-2.0`

## 可视化 Skill

- [3dviz-pro-max](./3dviz-pro-max.md) — 想法 → 可探索 Three.js / Blender 场景：配方库 + knowledge + 已验证 kit，真跑抓帧自检。`MIT`

## 可拆解模拟器

- [teardown](./teardown.md) — Claude Code skill：一句「做个能拆的 XX 模拟器」，生成单文件离线 HTML——机器在中间运转、周围面板读真实数值、按钮打开正在工作的零件、无人操作时自动巡游拆解。`MIT`

## 跨域制作台（3D / 纹理 / 天空盒）

- [scenario-labs/skills](../studio/scenario-skills.md) — 经 Scenario MCP：文/图生 mesh、PBR 纹理、360 天空盒、可走房间、动捕与 Blender 联调等（同包还覆盖图像/视频/音频/游戏资产）。`MIT`
