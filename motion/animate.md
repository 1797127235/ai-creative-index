# animate

[← 返回动效与动画](./README.md) · [仓库](https://github.com/cth9191/animate)

`MIT` · Claude Code skill · 一个 `<canvas>` + 程序化配乐 → 逐帧确定性渲染 MP4

## 它是什么

给它一句话，它自己走完「问需求 → 查事实 → 定风格 → 画分镜 → 生成 → 审片」。整片是**一个自包含的 HTML**（`<canvas>` 绘制），音乐和音效也由代码合成，所以每次渲染同一帧都是同一像素 —— 能重跑、能局部重渲。

适合：讲解片、历史、机制/原理说明、小故事、产品发布短片。不适合：真人实拍、需要大量实拍素材的片子。

## 流程（每一步都让你先做便宜的决定）

| 步骤 | 你看到 | 你要决定 |
|---|---|---|
| 0. 需求 | 一组问题（题材、画幅、配音、风格、主角、你的音乐、你的产品）+ 风格画廊 | 回答，或选风格，或丢参考图 |
| 1. 故事检查 | 它选的故事格式 + 编号节拍表，事实已联网核对 | 通过 / 改节拍 |
| 2. 观感检查 | 2–4 张满幅风格帧（新风格则与你的参考并排） | 逐张点头 |
| 3. 分镜 | 每个节拍一张关键帧，含声音和转场 | 按面板号点头/打回 |
| 4. 生成 | —（按通过的分镜做动画、渲染、审片） | — |
| 5. 交付 | 成片 + 量化检查：卡点、故事弧响度、主角锚定、静音后的最响点、旁白速度 | 提意见 → 进修改轮 |

关键设计：**先批准便宜的东西（节拍表、静帧、分镜），再花时间做动画**。

## 7 种内置风格

| 风格 | 观感 |
|---|---|
| cut paper | 撕纸、投影、蜡笔、图案、有表情的角色 |
| crosshatch | 墨线每 2 帧「沸腾」一次，排线+铅笔灰，暖纸色 + 藏青的「机器内部」 |
| riso | 三色孔版印刷：不同角度的网点、叠印、套色偏移 |
| sketchbook | 石墨 + 一个强调色，画在速写本页上，手写字 |
| math | manim 式数学讲解：黑底、坐标轴与图像、变量配色、平滑缓动 |
| pixel | 按真实分辨率画、最近邻放大、点阵字体 |
| isometric | 精确等轴线稿：恒定细线、白面遮挡、圆角板、一个深色强调 |

**自己的风格**：给它参考（视频、静帧、网页），它按程序测量配色/线宽/纹理/运动/剪辑节奏 → 用 `tools/compare.mjs` 画出 1–2 帧跟参考并排给你比对 → 你点头后存成 `styles/<name>/`，之后所有片子都能用。**参考素材只留在你本机。**

每个风格目录有：`STYLE.md`（规则、配色、运动习惯、单帧清单）、`kit.js`、`sample.png`、`demo/`。

## 自带的东西

- **故事语法** `grammar/`：8 种短片格式（历史 = 按时间串起来、用形变转场；任务片 = 卡点切…）+ 每片都遵守的规则（一个恒定元素、颜色只代表一件事、最响点在静音之后、结尾 = 开头的变体）+ 单帧检查清单。
- **工具包** `kit/`：可控随机、每 2 帧沸腾的线条、相机、带形状形变转场的渲染器（旧世界收拢到一个物体 → 变成新世界的对应物 → 新世界展开）、分镜、合成器 + 手机播放响度处理。
- **命令行工具** `tools/`：build（打包成单个 `index.html`）、test tiles、stills、storyboard、export（帧 → WAV + 分轨 → MP4）、review（接触表 + 量化检查：文字截断/重叠、响度）、compare、参考测量、gallery、帧哈希校验（改 kit 后可验证成片像素不变）。
- **配音**：自己写稿 → ElevenLabs connector（或你自己录）逐句出音 → 本地 faster-whisper 对齐到词 → 画面跟着词走；重录会自动重排画面。
- **用自己的音乐**：给一首歌，它测 tempo、小节、大拍点、drop，按歌的节拍切，最响的 hit 放高潮；也可以让它用代码作曲。
- **你的真实产品**：截你的网站（或给 logo 文件），把真实界面放进风格里动。
- **四种画幅**：9:16、1:1、4:5、16:9 各自排版，不是裁切。
- **并行构建**：长片按场景拆成多个文件，多个 agent 并行做完再拼。

## 安装

依赖：Claude Code、Node 18+、Playwright + Chromium、PATH 里有 ffmpeg；配音需要 Python + `faster-whisper`。

```sh
npm i -g playwright && npx playwright install chromium
```

```sh
# 作为插件
/plugin marketplace add cth9191/animate
/plugin install animate@animate
# 或手工安装
cp -r plugins/animate/skills/animate ~/.claude/skills/animate
```

## 用法

```sh
/animate a 45-second history of the bicycle, cut paper
/animate how a hash map works, in the math style
/animate a short about our API in the style of these screenshots: ./refs/
/animate a 20s launch reel for https://my-product.com, cut to ./audio/song.mp3, vertical and square
/animate a narrated 45s explainer of how DNS works, math style, 16:9, voice from ElevenLabs
```

片子生成在你的项目 `pieces/<name>/` 下，也可以自己调工具：

```sh
SKILL=~/.claude/skills/animate
node $SKILL/tools/build.mjs <piece>
```

## 限制

- 绑 **Claude Code** 的 skill 机制（也能手拷目录用），不是通用 npm 库。
- 要 Chromium + ffmpeg；无 GPU 时会退到软件渲染并提示，WebGL 风格仍在开发中（"coming"）。
- 风格是「程序化插画」的算法感，做不了写实/摄影质感；要真实素材就走参考图或产品截图那条路。
- 时长越长渲染越久，靠并行构建摊平，机器弱会明显等待。

## 相关

- [mg-styles-15](./mg-styles-15.md) — 15 支成片 + 提示词，可以拿来当风格参考喂给 animate。
- [motion-prompt](./motion-prompt.md) — 用具体动作名词指挥它做某一段动效。
- [lemo-opuscar](../video/lemo-opuscar.md) — 另一套代码做片系统，风格库更大。