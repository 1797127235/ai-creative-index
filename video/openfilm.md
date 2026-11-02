# openfilm

[← 返回视频生成与编辑](./README.md) · [仓库](https://github.com/openfilm/openfilm) · [官网](https://openfilm.dev) · [示例片](https://github.com/openfilm/examples)

`MIT`（名称与 Logo 是商标）· 让编程智能体做视频 · 一个 HTML + 一个函数 · 带真正的剪辑器

## 它是什么

把编程智能体变成视频智能体，并且**它做出来的片子你能亲手改**。做法是把片子的格式压到两样东西：

- **一个 `film.html`** —— 片子就是一个文件夹，`<section>` 是轨道，里面的元素是片段（网页、视频、图片、声音）。放哪用 CSS，放多久用媒体片段（`#t=12,18` / `at="4"` / `speed`）。
- **一个 `frame(t)`** —— 每个镜头就是一个网页，用任意方式画出第 t 秒（three.js、WebGL、canvas、SVG、CSS、GSAP 都行），不需要 Remotion / HyperFrames 之类的框架。

然后配一个在浏览器里跑的本地**剪辑器 Studio**：画面里的任何元素都能移动、缩放、旋转，改文字/颜色/样式，时间线上修剪切分，调音量与速度、改字幕。你的修改写回片子文件，智能体下次编辑时会保留（存在 `overrides` 里），也能存命名版本随时回退。

## 唯一规则，也是最关键的设计

> 同一个 `t` 永远画出同一个画面，不管之前画过什么。

因为渲染是**乱序、并行**地请求各帧，还会请求两帧之间的时刻做运动模糊——所以遵守这条的片子，在任何尺寸、任何电脑上渲出来都一样。Python / Blender / 视频生成模型这类出不了 `frame(t)` 的，以视频或图片的形式接进轨道。

它把功夫花在模型容易出错的地方：`openfilm look` 会把总览里每一帧按两种打乱顺序各画一遍，**指出前后不一致的帧**，同时报告页面报错、字体加载失败、缺失音频、被画面边缘截断的文字。这基本等于「渲染前的 lint」。

## 命令

```sh
openfilm                          # 手册：智能体需要知道的全部内容
openfilm open   [folder | url]    # 在 Studio 里打开：新建、已有的、从 GitHub 取、当前目录、上次的
openfilm look   [what] [t | a-b]  # 缩略图总览、单帧、一段区间（一致性检查在这里）
openfilm render [a-b]             # 渲成 MP4；--4k、--blur（运动模糊）、--alpha（.webm/.mov 透明）
openfilm get    [what]            # 用你接的服务生成配音、音乐、音效、转写、图片、视频
```

## 安装

```sh
npx skills add openfilm/openfilm
```

需要 **Node 22.2+** 和 ffmpeg，macOS / Windows / Linux；首次运行下载无头 Chromium（约 100 MB）。Studio 保存版本还需要 git。不想装 skill 就让 agent「运行 `npx -y openfilm@latest`，按它打印的手册来做」。

桌面版（macOS / Windows）就是 Studio 加一个对话窗口，自带 ffmpeg 和浏览器；也可从源码 `pnpm dev`（Node 22.18+、pnpm 9）。

## 导出

视频、GIF、声音或分轨、字幕、静帧、幻灯片、透明背景视频，以及**整条时间线导出给 Final Cut Pro / Premiere Pro / DaVinci Resolve**——这一步是很多「agent 做视频」方案缺的，它承认最后可能还是要在 NLE 里收尾。

## 费用与账号

制作、剪辑、渲染都不需要账号。要配音/音乐/图片/视频时，在 Studio 设置里用**自己的 key** 接 ElevenLabs、OpenAI、Google、fal 等。

## 限制

- **`frame(t)` 必须是纯函数**。一旦镜头里藏了随机数、真实时钟或未等待的异步加载，`look` 会报不一致，渲染也会随机崩坏——这是它的核心约束，不是可选建议。
- 素材生成全靠外部服务与你的额度；仓库本身不产模型。
- 桌面版比 CLI 新，两个入口的完成度可能不同步；源码运行与安装版共用同一个项目库。
- 名字和 Logo 受商标保护，MIT 只管代码/格式。
- 想做「代码做片的风格库」而不是「做某一支片」时，它不是这个用途。

## 与 hyperframes 的分工

| | openfilm | [hyperframes](./hyperframes.md) |
|---|---|---|
| 抽象 | 一个 HTML + 一个 `frame(t)`，不要框架 | HTML/CSS + 可 seek 动画 + 组件库 |
| 强项 | **人手改**：内置剪辑器、NLE 导出、命名版本 | 组件/区块生态、lint、Workbench 预览 |
| 适合 | 交付给客户前要精修、要和剪辑师协作 | 批量出片、模板化、团队统一构件 |

两者都遵守「同一时刻同一画面」，选哪个取决于你是要**编辑器**还是要**构件库**。

## 相关

- [hyperframes](./hyperframes.md) —— 同上对比的另一半。
- [video-shotcraft](./video-shotcraft.md) —— 产品宣传片配方，Remotion 成片。
- [auto-motion](./auto-motion.md) —— SRT 自动拆镜的流水线，适合当 openfilm 的素材上游。
- [remotion 生态](../motion/README.md) —— 若你已有 React 代码库、想复用组件，那条路更顺。