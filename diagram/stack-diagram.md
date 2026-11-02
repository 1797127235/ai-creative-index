# stack-diagram

[← 返回示意图 / 信息图](./README.md) · [仓库](https://github.com/caru-ini/stack-diagram) · [画廊](https://stacks.caru.moe)

`MIT` · Agent Skill · 一句话 → 带官方 logo 的架构图 · 自包含 HTML

## 它是什么

「Diagram our stack: Next.js and a Hono API on Vercel. Postgres on Neon, auth with Clerk, payments with Stripe.」——一句话，出一张架构图，节点上是**各家官方 logo**。

和 [diagram-design](./diagram-design.md) 的分工：diagram-design 管「编辑向示意图」的视觉判断（象限、时序、泳道…）；stack-diagram 只管**技术架构这一种图**，但把两件事做到位：

- **logo 是真的**。按 svgl → devicon → gilbarbara/logos → 品牌自己的仓库 的顺序取，AWS 图标用 AWS 官方包，**从不改色、不重画**。
- **线不穿字**。连线绕开标签走，出图前 agent 自己渲染看一遍再交付。

## 输出形态

同一份图渲染出四种：

| 形态 | 用途 |
|---|---|
| 自包含 HTML（默认） | 字体和 logo 内联，断网也能打开；可直接当 Claude artifact 发链接、塞进仓库或 wiki |
| PNG | 文档、PPT |
| 无依赖 React 组件 | 直接进产品文档站 |
| Artifact | 分享 |

每张图同时出浅色和深色两版：色块保持白底以保住 logo 本色，分组标签换成该品牌深色主题的 logo。

## 用法

```text
Draw our monorepo tooling: a pnpm workspace with Turborepo, Biome, Vitest and Lefthook. GitHub Actions runs CI and publishes to npm.
Draw our docs chatbot: Next.js on Vercel searches Supabase pgvector and answers with Claude. Inngest syncs Notion every night.
Draw our app on AWS: CloudFront in front of S3 and an ALB in a public subnet. Fargate, RDS and ElastiCache sit in a private subnet.
```

它不只画云，开发工具链、AI 应用、AWS 官方图标体系都能画。

## 安装

```bash
npx skills add caru-ini/stack-diagram
```

支持 Claude Code、Codex、Cursor 等读写 `SKILL.md` 的 agent；Claude 应用里从 Releases 下 `stack-diagram.zip` 作为 skill 上传。

环境：**Python 3.9+**，取 logo 需要联网；导出 PNG 需要 Playwright + Chromium。

## 画廊与隐私

画完会**只问一次**要不要发到公开画廊 `https://stacks.caru.moe`：先展示将公开的内容（浅/深 PNG、英文标题、技术栈、显示名），**你连说两次同意才发**；你的原始提示词从不发送。GitHub 登录可选，仅用于以后删除帖子。

## 限制

- logo **不随包分发**，构建时从 svgl / devicon / gilbarbara / AWS / Lucide 或品牌站点下载；断网装不了图。
- 只擅长「技术栈拓扑」这一类图；要象限、时序、用户旅程、Sankey 请用 diagram-design。
- 品牌名与 logo 是各自持有者的商标，出现在图里不代表背书。
- 节点太密时仍需人判断该拆图；它保证的是「logo 对、线不压字」，不是「这张图讲得清」。

## 相关

- [diagram-design](./diagram-design.md) —— 45 种编辑向图型，重排版与品牌配色，logo 不是重点。
- [anatomy](../3d/anatomy.md) —— 等轴测实体插画，讲机制而不是讲拓扑。
- [impeccable](../web-ui/impeccable.md) —— 页面与界面审美；图示本身不归它管。