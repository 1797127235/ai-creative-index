# teardown

[← 返回 3D / 空间](./README.md) · [仓库](https://github.com/elvarofficial/teardown)

`MIT` · Claude Code skill · 一句话 → 可拆解的单文件离线 HTML 机器模拟器

## 它是什么

问「某某怎么工作」，Claude 建成**一个离线 HTML**：中间机器在转，周围面板读**真实数值**，按钮打开正在干活的零件；没人操作时页面自己巡游拆解。

示例机器：机械蜂、蝎子、章鱼；仓库里还有 V8、塞斯纳、Strandbeest 等完整样例（`-shared` 机体 / `-live` 可开 / `-film` 录好的巡游）。

> 与 [jakubkrehel/skills](../web-ui/jakubkrehel-skills.md) 里的同名 `teardown` skill（2D 技术插画导出）**不是同一个项目**。

## 安装

```sh
npx skills add elvarofficial/teardown -g -a claude-code
```

在装好的目录里再执行一次：

```sh
npm install && npx playwright install chromium
```

需要 **Node.js 20+**。要出视频加 `ffmpeg`；片上的声音还要 Python 3。

## 用法

直接说人话：

> Build me a simulator of a 4-stroke motorcycle engine I can take apart.  
> How does a mechanical watch keep time? Show me as a simulator.  
> Make a teardown of a hydraulic excavator arm and record a 20-second video of it.

或先开自带样例：

```sh
node sims/build.mjs v8-live          # → teardown-out/dist/v8-live.html
node sims/build.mjs cessna-live
node sims/build.mjs strandbeest-live
```

## 目录里有什么

| 路径 | 作用 |
|---|---|
| `SKILL.md` | Claude 读的：怎么搭机器、观感规则、评审环 |
| `sims/kit/` | 运行时、舞台、shader 预热 |
| `sims/*-shared|live|film` | 完整机器三件套 |
| `sims/build.mjs` | 打成单 HTML（three.js、字体内联） |
| `sims/capture.mjs` | 逐帧渲 60fps mp4 或静帧审片表 |
| `sfx/` + `run_sfx.py` | 按时间轴程序化音效，母带约 −14 LUFS |

运行时/逐帧/声音/评审规则基于 [whaleyxbt/claude-motion](https://github.com/whaleyxbt/claude-motion)（MIT）；采样 CC0，出处在 `sfx/samples/SOURCES.md`。

## 限制

- 绑 Claude Code skill；目标是**讲解/演示模拟器**，不是导出可打印 CAD（要实体件用 [text-to-cad](./text-to-cad.md)）。
- 复杂机构依赖模型空间想象力与评审环，物理精度不能当工程仿真用。
- 出片要 Playwright Chromium + ffmpeg，机器弱会慢。

## 相关

- [text-to-cad](./text-to-cad.md) — 出 STEP/STL 的制造向 CAD。
- [animate](../motion/animate.md) — 另一类「单 HTML 确定性成片」，偏 2D 讲解片。
