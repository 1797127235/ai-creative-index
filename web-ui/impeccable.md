# impeccable

[← 返回网页与 UI 设计](./README.md) · [仓库](https://github.com/pbakaus/impeccable) · [文档](https://impeccable.style/docs)

`Apache-2.0` · 设计词汇 + 审稿 + 确定性 slop 检测 · 装进 Claude Code / Cursor / Codex 等 coding agent

## 它是什么

给 coding agent 一套**能点名的设计动作**：`/impeccable bolder`、`polish`、`critique`、`audit`……不是「做得好看一点」，而是每条命令带自己的 playbook，对着具体组件或页面动手。

同一模型、同一 brief：没装它时常见奶油底 + 细衬线 + 圆角卡片；装上后会围着一张主导视觉（产品/场所）来铺版。最强在**已有界面上迭代**；从零开页也能用，但要按文档走「先定方向再铺」。

## 它提供什么

| 类别 | 命令 | 干什么 |
|---|---|---|
| 控方向 | `bolder` / `quieter` / `distill` / `colorize` / `typeset` / `layout` / `animate` / `delight` / `overdrive` | 放大、收束、去冗余、上色、排版、节奏、动效、个性、甚至 shader/弹簧 |
| 审稿 | `critique` / `audit` | UX 打分排序；无障碍/性能/主题/响应式，P0–P3 |
| 收尾 | `polish` / `harden` / `clarify` / `adapt` / `optimize` / `onboard` | 上线前过一遍、错误态/i18n、文案、多端、性能、首启 |
| 现场改 | `live` / `generate` | 浏览器里点元素换变体，或批量出变体 |
| 立项 | `init` / `document` / `shape` / `extract` | 写 `PRODUCT.md` / `DESIGN.md`、先规划 UX、抽设计系统 |

另有 **62 条确定性规则**（不走 LLM）抓常见 AI 味：Inter 全家桶、紫蓝渐变、卡片套卡片、色底灰字、圆方角图标块等。可在 agent hook、CLI、CI 里跑。

## 安装与用法

```sh
npx impeccable install
# 重载工具后
/impeccable init          # Codex 上用 $impeccable init
/impeccable critique the pricing cards
/impeccable polish settings
```

`init` 读你的代码，只问推不出来的事（给谁用、要干什么、约束），写出 `PRODUCT.md`；后续命令都读它。`document` 把现有视觉收成 `DESIGN.md`，改动不跑偏品牌。

支持面很宽：Claude Code、Cursor、Codex、Copilot、Gemini CLI、OpenCode、Pi 等（见官网列表）。

## 限制

- 强项是**改现有 UI**；空白页要先定产品与视觉方向，否则仍可能落到「安全默认」。
- `live` 只适合本地 checkout，别往生产站注入；Apply 可能拉起本机 `codex`/`claude` 且关掉沙箱，陌生仓库先审 `impeccable:manual-edit-validate`。
- slop 检测是规则引擎，抓「机造痕迹」；审美高下仍靠 `critique` 和你自己点头。

## 相关

- [hallmark](./hallmark.md) — 另一套反 slop：50 主题 + 浏览器 lint，偏从零建页。
- [taste-skill](./taste-skill.md) — 艺术指导 + 真图 + 浏览器自检。
- [jakubkrehel/skills](./jakubkrehel-skills.md) — 排版/色/无障碍等工艺 checklist。
