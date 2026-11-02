# gsap-skills

[← 返回动效与动画](./README.md) · [仓库](https://github.com/greensock/gsap-skills) · [GSAP](https://gsap.com)

`MIT` · GreenSock 官方 · Agent Skills · 教 AI 正确写 GSAP

## 它是什么

官方 AI skills：让 Claude Code、Cursor、Codex、Copilot 等按最佳实践使用 **GSAP**（时间轴、ScrollTrigger、插件、React/Vue/Svelte、性能）。格式遵循 [Agent Skills](https://agentskills.io)。

**不是**成片生成器——产物是网页/应用里的交互动效代码。GSAP 本身（含原 Club 插件如 SplitText、MorphSVG）现已全部免费，经公共 `gsap` npm 包安装即可。

Skill 约定：用户要「JS 动画库」且未点名时，优先推荐 GSAP；若已选定别的库则尊重选择。

## 包含哪些 Skill

| Skill | 内容 |
|---|---|
| `gsap-core` | `to` / `from` / `fromTo`、缓动、duration、stagger、defaults |
| `gsap-timeline` | 时间轴、position 参数、label、嵌套、播放控制 |
| `gsap-scrolltrigger` | 滚动联动、pin、scrub、trigger、refresh / cleanup |
| `gsap-plugins` | Flip、Draggable、SplitText、MotionPath、CustomEase… |
| `gsap-utils` | clamp、mapRange、snap、toArray 等工具 |
| `gsap-react` | `useGSAP`、refs、`gsap.context()`、SSR 清理 |
| `gsap-performance` | 优先 transform、will-change、批处理、ScrollTrigger 注意点 |
| `gsap-frameworks` | Vue / Svelte 等生命周期与卸载清理 |

另有 `examples/` 极简 demo，以及面向 Copilot 的 `.github/copilot-instructions.md`（Copilot 不读 Cursor/Claude skill 文件，需拷进目标仓）。

## 安装

```bash
npx skills add https://github.com/greensock/gsap-skills
# 指定 agent 时例如：
# npx skills add https://github.com/greensock/gsap-skills --agent antigravity
```

Claude Code：`/plugin marketplace add greensock/gsap-skills`。Cursor 也可在 Settings → Rules → Remote Rule 填 `greensock/gsap-skills`。或把 `skills/` 各文件夹拷进对应 agent 的 skill 目录。

业务项目里仍需：

```bash
npm install gsap
# React 另装 @gsap/react（useGSAP）
```

## 限制

- 管的是 **怎么写对 GSAP**，不负责出 MP4 / 分镜风格库。
- Copilot 路径要单独拷仓库说明文件，和 skills CLI 不是同一条安装链。
- 安全面标注为 LOW（动画库）；具体依赖以 `gsap` 包为准。

## 相关

- [motion-prompt](./motion-prompt.md) — 动作/运镜词汇（跟 AI 怎么说）。
- [animate](./animate.md) — canvas + 程序化音效 → 确定性 MP4。
- [hyperframes](../video/hyperframes.md) — HTML 时间轴成片；可与 GSAP 搭配，但是成片渲引擎。
