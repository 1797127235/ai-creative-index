# text-to-cad

[← 返回 3D / 空间](./README.md) · [仓库](https://github.com/earthtojake/text-to-cad) · [网站](https://www.texttocad.dev)

`MIT` · Agent 插件/skills · 自然语言/图稿 → 可制造 CAD（STEP / GLB / STL / 3MF）

## 它是什么

给 Claude Code、Codex、Cursor、Gemini、Grok 等装上后，agent 用本地工作流做**实体产品设计**：

1. 把零件/装配写成 [build123d](https://github.com/gumyr/build123d)（Open CASCADE）Python 脚本。  
2. `python model.py` 经 text-to-cad 的 server 建成 `.xbf` 文档（零件、名、色、材料、关节）并导出你声明的 STEP/GLB/STL/3MF；改一点只重算脏部分。  
3. CAD 查看器在 agent 应用或浏览器里跟着每次重建刷新。

顺带：可制造性检查、工程图、对接常见 3D 打印 / 钣金 / CNC 打样服务。

## 安装

macOS / Linux：

```bash
curl -fsSL https://texttocad.dev/install.sh | sh
```

Windows（PowerShell）：

```powershell
irm https://www.texttocad.dev/install.ps1 | iex
```

脚本会按需装 `uv`，往本机各 agent 写入插件（skills + CAD MCP）或纯 skills，注册 `cad` 命令并升级 server。再跑一次即更新；手工分应用安装见 `docs/install.md`。

然后直接跟 agent 要零件或装配即可。

## 自带 Skills（节选）

| Skill | 作用 |
|---|---|
| CAD | 自然语言/图 → 脚本 → XBF + 导出 |
| step.parts | 找现成 STEP（螺丝、轴承、电机等） |
| Engineering Drawing | 零件出标注工程图 PDF |
| DXF | 2D 轮廓/垫片/下料 |
| URDF / SRDF / SDF | 机器人结构、MoveIt、仿真世界 |
| SendCutSend | 上传前检查 DXF/STEP |

## 限制

- 输出是**精确 CAD 几何**，不是游戏向美术 mesh；有机雕塑、影视资产不是主场。
- 依赖本机 Python/CAD server；复杂装配要人会看图、会改脚本，不能当纯黑盒。
- 打样对接是检查与工作流辅助，下单与报价仍在各厂商自己的站上完成。

## 相关

- [teardown](./teardown.md) — 讲解向可拆解 HTML 模拟器，不是出 STEP 的 CAD。
