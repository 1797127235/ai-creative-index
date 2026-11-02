# logo-design-skill

[← 返回图像生成与编辑](./README.md) · [仓库](https://github.com/kaankiziltug/logo-design-skill)

`MIT`（不覆盖参考库里的真实商标）· Agent Skill · 标识别设计全流程 · 1,400+ logo 参考库

## 它是什么

把 agent 变成「守规矩的标识设计师」：从 brief 到可直接生产的 SVG、品牌规范。它不是「给我画个 logo」，而是把标识设计拆成可检查的步骤，并在关键处停下来等人拍板。

流程固定五步：

1. **Brief** —— 提问或明说假设（行业、气质、使用场景）。
2. **查同类** —— 在参考库里查该品类的惯例，避免做出「和别家撞脸」的形状。
3. **概念** —— 先给 8–12 条一句话概念，挑 3 条做成 SVG。
4. **测试与打磨** —— 跑审计（锚点数、近差角度、微小细节、居中）、16px 像素测试、单色/反白、眯眼、镜像、场景、竞品货架测试。
5. **检查点** —— **一定停在这里**：把概念拼成一张总览图 + 一个推荐 + 是否要完整 kit。kit 是大头，只有方向被认可后才做。

「kit」= 配色、横竖组合、客户提案板（含六个行业特定 mockup）、favicon/应用图标/web manifest 全套、品牌规范。

## 参考库

1,400+ 个 SVG、约 1,200 个品牌；233 个品牌同时有组合标和独立图标。按标型/技法/几何/题材/字体/气质/行业分类，命令行可查，也有本地 `assets/library/gallery.html` 可浏览。

分布：abstract 24%、combination 21%、pictorial 20%、letterform 15%、wordmark 10%、emblem 4%、mascot 4%、lettermark 3%；中位 2 色、75% ≤3 色、19% 用渐变；141 个被标为教学范例。

用途是**研究构造、摸品类惯例、避开相似**，不是拿来抄。

## 工具（纯标准库 Python，3.8+）

```bash
cd skills/logo-design
python3 scripts/search_library.py --technique negative-space --exemplary
python3 scripts/svg_audit.py my-logo.svg          # 输出 production-readiness 分数
python3 scripts/concept_sheet.py a.svg b.svg c.svg --names A B C --recommend 1 -o concepts.png
python3 scripts/preview_sheet.py my-logo.svg --refs-industry developer-tools -o preview.html
python3 scripts/render_png.py my-logo.svg --size 512 -o my-logo.png
python3 scripts/export_variants.py my-logo.svg --mono "#0F7C80" --web-icons
```

`svg_audit.py` 会给出类似 `production-readiness score: 76/100` 的判定，并逐条列出「374 个锚点，多于 95% 同类」「6 个小于画布 1/48 的碎形」这类问题。

## 安装

```text
/plugin marketplace add kaankiziltug/logo-design-skill
/plugin install logo-design@logo-design-skill
```

或手工 `cp -r logo-design-skill/skills/logo-design ~/.claude/skills/logo-design`；Claude.ai / Desktop 从 Releases 下 `logo-design.zip` 上传到 Skills（超限用 `logo-design-lite.zip`）。Gemini CLI / Codex / Cursor / Copilot 走各自的 skills 装法。

## 限制

- **只出矢量标识**，不做位图插画、字体设计、整套 VI 执行；画风类需求走 [handraw-style](./handraw-style.md)。
- PNG/ICO 导出依赖本机有 `cairosvg`、`rsvg-convert`、Inkscape、Chromium 系浏览器或 macOS Quick Look 之一。
- 审计是启发式规则，不是审美裁判；分数高不等于客户会买。
- 参考库里是**真实品牌商标**，不在 MIT 范围内（见 `TRADEMARKS.md`）：可研究，不可再分发、不可直接改一点当自己的标。
- 示例里的品牌（Kiln、Zestly…）都是虚构 brief，用于展示流程。

## 相关

- [handraw-style](./handraw-style.md) —— 画风/插画提示词库，不涉及标识构造。
- [diagram-design](../diagram/diagram-design.md) —— 同为「有明确规则的出图 skill」，一个出标识，一个出示意图。
- [impeccable](../web-ui/impeccable.md) —— 设计品味/界面评审，与标识的品类惯例互补。