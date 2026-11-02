# auto-motion

[← 返回视频生成与编辑](./README.md) · [仓库](https://github.com/vibe-motion/auto-motion)

`未声明协议` · SRT → 多段 MG 镜头 → 竖屏 `final.mp4` · Codex 调度 + Claude Code 执行

## 它是什么

一份**工作流模板**，不是通用库：你只准备 `transcription.srt`，让 Codex 执行根目录 `PROMPT.md`。它会按字幕语义拆成连续镜头，逐镜调 Claude Code 写动画并渲 MP4，最后 FFmpeg 拼成竖屏成片。

架构四层：

| 层 | 谁 | 干什么 |
|---|---|---|
| 调度 | Codex + `PROMPT.md` | 读 SRT、拆镜、建 `scenes/scene-00x`、拷模板、串行调 Claude、验收、拼接 |
| 执行 | `exampleFolder/run-claude-ai.sh` | 填 `SCENE_ID` / 时长 / 文案 / 输出路径，`claude -p` 非交互跑单镜 |
| 动画 | HyperFrames 相关 skills（打在 exampleFolder 里） | 写 HTML 动画，渲 **1080×1440、30fps、静音无音轨** MP4 |
| 验收 | `auto-test/` | 临时工作区跑通，校验分辨率、帧率、时长、无音轨 |

## 前提

本机已登录/可用：

- Codex CLI、Claude Code  
- Node.js **22+**、FFmpeg / FFprobe、`jq`  
- 可联网（搜素材、装依赖、下品牌资产）

```bash
codex --version && claude --version && node --version
ffmpeg -version && ffprobe -version && jq --version
```

## 怎么跑

```bash
cp /path/to/transcription.srt ./transcription.srt

codex exec \
  --cd . \
  --sandbox danger-full-access \
  --ask-for-approval never \
  - < PROMPT.md
```

产物大致：

```text
scenes/scene-001/scene-001.mp4
scenes/scene-002/…
final.mp4
```

端到端自测：`bash auto-test/run.sh`（产物在 `auto-test/.tmp/`，已 gitignore）。

## 注意

- **同一时间只跑一个** Claude Code 镜头，不并行。
- 镜头必须铺满字幕时间轴，时长总和 ≈ SRT 总长。
- 失败先看该镜目录下 `stderr.log` / `stream.jsonl` / `user.log`。
- 规格不一致要先统一转码再拼接。
- 仓库**未声明开源协议**；商用前自己确认许可风险。

## 限制

- 绑死 Codex + Claude Code + HyperFrames 这条链；换调度器要改 `PROMPT.md` 与脚本。
- 成片默认**无音轨**（字幕驱动画面）；旁白/配乐要另接。
- 长字幕会跑很久（作者实证可超过一小时量级），适合批跑不适合「改一字立刻出片」。

## 相关

- [hyperframes](./hyperframes.md) — 单镜动画实际用的渲染框架。
- [lemo-opuscar](./lemo-opuscar.md) — 另一套「agent 导演整片」，输入是风格+故事而非 SRT。
