# motion-prompt

[← 返回动效与动画](./README.md) · [仓库](https://github.com/showheyohtaki/motion-prompt) · [动态画廊](https://showheyohtaki.github.io/motion-prompt/)

`MIT` ⭐1.1k · 192 个动作/效果名词 · 5 种语言 · 附 Claude Code / Codex skill

## 它解决什么问题

跟 AI 说「动效高级一点」「丝滑一点」没用，它只能瞎猜。这个库把模糊的效果拆成 **192 个有名字的东西**（例如运镜里的某种推拉、UI 里的某种展开），每个名字都配：编号、含义、一句提问范例、一个能动的示例、一份 spec、一段可直接用的代码。

所以用法是反过来的：**先看画廊找到你想要的效果 → 拿到它的名字或编号 → 用名字跟 AI 说话**。它相当于动效领域的词典，不是素材包。

## 8 个 pack（各 24 个）

| 编号 | pack | 收什么 |
|---|---|---|
| 001–024 | `motion` | MG 动作 |
| 025–048 | `camera` | 运镜与转场 |
| 049–072 | `ui` | UI 组件动效 |
| 073–096 | `lp` | 落地页与网页效果 |
| 097–120 | `photo` | 摄影观感、打光、风格 |
| 121–144 | `motion2` | MG 动作，第二批 |
| 145–168 | `lp2` | 落地页与网页效果，第二批 |
| 169–192 | `camera2` | 运镜与转场，第二批 |

每个 pack 有自己的视觉风格，但作者明说：**pack 只要保证名字准确，不要形成「统一风格」** —— 所以 photo 那个 pack 没有共用配色，每张卡按自己场景的色来画。

## 三种用法

1. **装了 skill（Claude Code / Codex）**：`npx skills add showheyohtaki/motion-prompt`，然后跟 AI 说「打开 motion-prompt 库」→ 画廊自动打开 → 点样本上的 **Pick**（可多选），底部写一行用途（如「for the opening title」）→ **Send to AI**，你的选择直接进对话，再说要拿它做什么。它只会用你挑的那些。
2. **没装 skill**：在画廊里挑好，点 **Copy picks** 把文本贴进任意 AI 的聊天框（文本里带 demo 和 spec 链接）。
3. **已经知道编号**：跳过画廊，直接点名。命令行长这样：

```sh
search typewriter text        # 按词找（英文/日文都行）
list --pack motion            # 列某个 pack 的全部条目
get 12 #045                   # 打印 #045 的 spec 和代码（一次最多 8 个）
prompt 12                     # 打印 #012 可直接粘贴的提示词
kit motion                    # 某个 pack 的共用代码
info                          # 数据来源、数量、缓存在哪
```

## 数据与隐私

- 只对 `https://showheyohtaki.github.io/motion-prompt/api/v1/`（不通则回落 `raw.githubusercontent.com`）发 GET，**不上传你项目的任何东西**。
- `pick` 会在本机 127.0.0.1 开一个临时监听，只接收画廊「Send to AI」发来的编号和备注。
- 环境变量：`MOTION_PROMPT_BASE`（换成自己镜像或本地目录）、`MOTION_PROMPT_CACHE`（默认 `~/.cache/motion-prompt`）、`MOTION_PROMPT_TTL`（默认 `21600` 秒 = 6 小时）。
- 整个仓库 clone 下来后，CLI 优先读本地 `api/v1`，完全离线也能用。
- 本地跑画廊：`python3 -m http.server 8000` 后开 `http://localhost:8000/`。

## 限制

- 示例和代码是**网页实现**（给网页/UI 用的），搬进视频管线还得自己接渲染（对比 [mg-styles-15](./mg-styles-15.md) 的逐帧方案）。
- 名词是英文/日文为主，中文是翻译（初版翻译来自社区，见仓库致谢）。中文提问能让 AI 理解，但库里权威名字仍是英文。
- 用它的代码要在首行保留署名注释（MIT 许可要求），商用可以，别删那行。

## 相关

- 想找**风格**而不是**动作**：[mg-styles-15](./mg-styles-15.md)（15 种成片风格）、[lemo-opuscar](../video/README.md)（66 种）。
- 想让 AI 直接出片：[animate](./animate.md)。