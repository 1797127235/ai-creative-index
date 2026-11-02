# hallmark

[← 返回网页与 UI 设计](./README.md) · [仓库](https://github.com/Nutlope/hallmark) · [主题画廊](https://www.usehallmark.com/)

`MIT` · Together AI · 反 AI 味网页设计 skill · Claude Code / Codex / Cursor / OpenCode

## 它是什么

一套**拒绝看起来像 AI 生成**的设计 skill：先从 50 套「材质主题」里发三张给你选，再按「这页要干什么」（预订、下单、订阅……）铺版，最后在真浏览器里 lint 机造痕迹，并用新鲜上下文的 reviewer 做终审。

主题是**材质**（纸、字、色、表面、组件、纹理），不是版式模板：同一主题、两个 prompt 会做出两页不同结构。也可以说 **custom**，丢掉主题库，只靠地板规则 + 方向说明，从客户独有的一个点子撑起整页。

## 怎么跑通一页

1. **Pre-flight**：读项目（字体、色板、框架、锁定的 `design.md`），问一次要不要真照片/截图/真数字——不编造。
2. **发主题**：`scripts/theme.mjs deal` 出三套合适的；`draw` 按任务类型定页面骨架。
3. **先做 hero**：单独做出、渲染、冷审，过了再铺整页。
4. **Lint + 复审**：`scripts/sloplint.mjs --render` 在八个宽度检查；子 agent 再通读。

产出是**自包含 HTML/CSS**，首条 CSS 注释里盖上决策戳。

## 门槛分三级

| 级 | 含义 |
|---|---|
| Floor | 对比度、焦点、减少动效、捏造事实、手机版崩了 —— **绝不发船** |
| Reflex | 模型默认坏习惯；有理由可记在案后推翻一条 |
| Finish | 工艺细节，不挡发船 |

会抓的机造痕迹包括：标题上的 eyebrow、字距拉满的大写标签、标题里一个彩词、满页空框或只有照片、hero 没撑满屏、页尾永远邮箱注册、表单说谢谢却没真正提交等。

## 命令

- 从零建页：按 skill 流程选主题或 custom。
- `/hallmark redesign <path>` — 重做设计，**保留内容和接线**。
- `/hallmark audit <path>` — 只出报告，不改。
- 可对着 URL、dev server 或本机 app 自己截屏；附带 755 张开放许可照片按题材选用并署名。

## 限制

- 绑 coding agent 的 skill 机制；产物偏**营销/落地页式自包含页**，往复杂 App 壳里塞要自己接线。
- 主题与 lint 规则是英文语境下的「反 slop」美学，中文品牌要自己补文案与文化判断。
- 需要本机浏览器跑渲染检查；找图要联网。

## 相关

- [impeccable](./impeccable.md) — 命令式打磨现有组件，偏产品 UI 迭代。
- [taste-skill](./taste-skill.md) — 艺术指导 + 开放档案真图。
- [jakubkrehel/skills](./jakubkrehel-skills.md) — 界面工程 checklist。
