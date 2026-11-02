# VoiceStudio

[← 返回音频 / 音乐](./README.md) · [仓库](https://github.com/debpalash/VoiceStudio) · [网站](https://voicestudio.sh) · [简体说明](https://github.com/debpalash/VoiceStudio/blob/main/docs/readme/README_CN.md)

`AGPL-3.0` · 本地开源 ElevenLabs 替代 · 克隆 / 造声 / 配音 / 听写 / 有声书 · 646 语言

## 它是什么

跑在你自己设备上的 **AI 语音工作室**（笔记本、台式机、服务器、手机和平板等）：不把声音交给闭源 SaaS，模型按需本地下载。

| 能力 | 做什么 |
|---|---|
| Voice cloning | 干净参考录音 → 熟悉音色的说话 |
| Voice design | 用文字描述一种声音再生成 |
| Video dubbing | 译配视频，口型/时轴对齐原片语势 |
| Dictation / transcription | 听写与转写 |
| Audiobook / narrate | 长文本朗读、有声书向工作流 |
| Local models | 自选引擎，只下需要的模型 |

桌面端有暗色工作区演示；HD 导览见仓库 `docs/media/`。

## 怎么开始

- 发行版：GitHub [Releases](https://github.com/debpalash/VoiceStudio/releases/latest) 下载安装包。  
- 从源码/文档：[Get started](https://github.com/debpalash/VoiceStudio#get-started) 与 `docs/`（克隆质量、配音、模型下载等分册）。  
- 社区：Discord；多语言 README 在 `docs/readme/`。

这是**完整应用**，不是给 coding agent 的一行 skill；做片配音时通常：人在 VoiceStudio 出音轨 → 再丢进 [hyperframes](../video/hyperframes.md) / [animate](../motion/animate.md) 等视频管线。

## 限制

- **AGPL-3.0**：改过再提供网络服务时，需遵守 AGPL 开源义务；闭源产品内嵌要谨慎评估。
- 音质与速度取决于本机算力与所选模型；旗舰云 TTS 的「开箱即用」稳定度不能默认对等。
- 646 语言是能力上限宣传，具体语种覆盖以你下载的模型为准。
- 克隆他人声音涉及肖像/声音权与平台条款，商用务必合规。

## 相关

- 视频管线配音入口：[hyperframes](../video/hyperframes.md)、[animate](../motion/animate.md)（后者也可接 ElevenLabs connector）。
- 本目录目前以语音工作室为主；纯音乐生成工具仍待收录。
