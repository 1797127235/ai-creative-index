# shuohao-skills

[← 返回文字创作](./README.md) · [仓库](https://github.com/eternityspring/shuohao-skills) · [中文说明](https://github.com/eternityspring/shuohao-skills/blob/main/README.zh.md) · [Reelbench Studio](https://studio.reelbenchai.com)

`Apache-2.0` · AI 短剧制作 skill 包 · 小说 → 大纲 / 角色 / 美术 / 剧本 / 站位 / 分镜 · 脚本门禁

## 它是什么

把一本小说（或自有故事）做成**可交给 AI 视频管线的短剧前期材料**：改编大纲、角色圣经、场景道具设定、剧本、开场站位、分镜；另有独立的角色参考图生成。每个 skill 自包含，任何能读 `SKILL.md` 并跑随附脚本的 Agent 都能用（Claude Code、Codex 是示例，不是唯一宿主）。

流程概览：

```text
小说 → novel-outline
        ├→ novel-characters ⇄ novel-art ⇄ novel-script
        │         └→ character-refs（可选，真出参考图）
        └→ novel-staging（剧本+美术后）→ novel-storyboard → 投产包
```

质量门大量用 **Node 脚本硬检查**（大纲 14 道、剧本/美术各 10、站位 8、分镜 18），报告可出 HTML；五个阶段还可合成单页导航报告。

## Skills 一览

| Skill | 做什么 |
|---|---|
| `novel-outline` | 短剧大纲五件套：改编说明、人物表、爽点、分集梗概、资产清单 |
| `novel-characters` | 角色设定集：画像、形象/音色提示词、设定图 |
| `character-refs` | **真出**角色参考图（正面锚点 → 其它视角只跟锚点）；ComfyUI / Codex / GPT Image 等 |
| `novel-art` | 场景 + 叙事道具美术圣经；一致性锚点、光照变体、白底板 |
| `novel-script` | 场次 + 节拍流；时长按语速折算；冷开场钩子门；台词本对接 TTS |
| `novel-staging` | 开场站位俯视图（可拖）；输出走位句给分镜第一段照抄 |
| `novel-storyboard` | 段 → 分镜 → 关键帧；对齐 H3 等提示词；可 export H3 / Seedance 投产包 |

注意：分镜**尚不会自动读** `staging.json`，需把确认后的开场走位句交给 Agent 抄进每场第一段。

## 安装

```bash
git clone https://github.com/eternityspring/shuohao-skills.git
cd shuohao-skills
./scripts/install.sh                 # 检测 Claude Code / Codex，symlink 全部 skill
./scripts/install.sh novel-characters  # 只装一个
./scripts/install.sh --uninstall
```

symlink 后 `git pull` 即生效。其它 Agent：把 `skills/<name>` 链/拷进其 skills 目录，或直接加载 `SKILL.md`。

合成多阶段报告（不含站位与 character-refs 图册）：

```bash
node scripts/report.mjs --from <demo目录> --out report.html
```

## 和 oh-story 的差别

| | [oh-story](./oh-story.md) | shuohao-skills |
|---|---|---|
| 目标 | 网文连载：扫榜、写作、去 AI 味、封面 | 小说 → **短剧**改编与分镜投产 |
| 主产物 | 章节正文 + 追踪文件 | 大纲/设定/剧本/分镜 JSON + HTML 报告 |
| 视觉 | 可选封面 | 美术板、参考图、分镜图是主链路一部分 |

## 限制

- 前期 skill 为主；**真正出成片视频**要另接 Seedance / H3 / ComfyUI 等（作者另有付费 Reelbench Studio）。
- 生图依赖你配置的出图后端（ComfyUI、Codex image、GPT Image API…），没配则参考图/分镜图环节受限。
- 站位与分镜之间目前是人工交接走位句，不是全自动一条龙。
- 改编质量仍取决于原文与模型；门禁管的是结构完整性，不是「必火」。

## 相关

- [oh-story](./oh-story.md) — 网文写作与连续性，不是短剧分镜流水线。
- [video/](../video/) — 成片渲染/代码做片工具；本包输出可喂进视频侧。
- ZenStory 的 `drama-skills` 等同赛道，未收录前可自行对比。
