# taste-skill

[← 返回网页与 UI 设计](./README.md) · [仓库](https://github.com/Leonxlnx/taste-skill) · [网站](https://tasteskill.dev) · [TasteCode 桌面端](https://tastecode.dev)

`MIT` · Agent Skill：艺术指导 + 真图 + 浏览器自检 · 不做「平均落地页」

## 它解决什么问题

coding agent 默认会拼一张「谁都能用」的站：安全配色、通用区块、假图占位。Taste Skill 反过来给三样东西：

1. **艺术指导** — 这一页该长什么样，有明确方向，不是形容词堆砌。
2. **真照片** — 从开放档案找图并署名（见仓库 `examples/v2/CREDITS.md`），不是灰块或 AI 糊图。
3. **浏览器检查** — 在真 Chrome/Edge/Chromium 里看自己的活，而不是只读 HTML。

示例页（咖啡店、夜场日期等）都是**一条 brief** 做出来的；照片是档案图，不是生成图。

## 安装

```sh
npx skills add https://github.com/Leonxlnx/taste-skill --skill "design-taste-frontend"
```

- 跑脚本要 **Node 22+**，本机装好 **Chrome / Edge / Chromium**。
- 不装额外依赖、不要 API key；找图需要网络。
- Claude Code：`/plugin marketplace add Leonxlnx/taste-skill` → `/plugin install taste-skill@taste-skill`（命名空间 `taste-skill:`，不跟别的 skill 撞名）。
- Codex：`codex plugin marketplace add …` / `codex plugin add taste-skill@taste-skill`，新开会话后生效。
- 从 clone 装：`./install.sh`（可 `--codex` / `--all-agents`）做符号链接，`git pull` 即更新。

另有开源桌面端 **TasteCode**（tastecode.dev）：同一套 taste + 内置 design agent。

## 怎么用

装好后让 agent 按 skill 做站或 App 屏：给 brief（业态、受众、必须完成的动作），它会定艺术方向、找图、写页面，并在浏览器里自检。仓库 `examples/` 可当观感参考。

## 限制

- 强项是**有明确品牌/场所气质的营销页与屏**；后台表格、设计系统大规模重构要配别的工艺 skill。
- 依赖本机浏览器与联网找图；离线只能改已有页，找不到新档案图。
- 「有味道」仍是主观标准——skill 提高下限，终审还是你。

## 相关

- [hallmark](./hallmark.md) — 主题库 + 硬门槛 lint，流程更闸门化。
- [impeccable](./impeccable.md) — 对着现有组件点名打磨。
- [jakubkrehel/skills](./jakubkrehel-skills.md) — 同一作者生态下的 Interfaces 杂志向工艺合集（赞助页也互相挂）。
