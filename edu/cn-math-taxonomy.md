# cn-math-taxonomy

[← 返回教育 / 课标数据](./README.md) · [仓库](https://github.com/xiaoyang111222/cn-math-taxonomy) · [在线试用](https://math.pansgo.com/) · [GitHub Pages 备份](https://xiaoyang111222.github.io/cn-math-taxonomy/)

`CC BY-NC 4.0` · 课标对齐知识图谱 · 题库 · 自适应前置诊断 · 静态站可自托管

## 它是什么

面向中国 K-12（并延伸到高中）的**学科知识图谱开源数据 + 诊断前端**：知识点、先修边（hard/soft）、课标条目映射、诊断题，以及可浏览的图谱页与自适应前置诊断工具。仓库名仍叫 `cn-math-taxonomy`，实际已不止数学——还覆盖英语、物理，并扩展语文、科学、历史、地理等（以仓库当前 `data/` 为准）。

典型用法：给 AI / 教学产品当「学什么、先修什么、错了回溯到哪」的结构化底座；数学答错可沿先修边从高中/初中回溯到小学具体点。英语、物理等与数学**分图**，物理用到的数学写在 `mathLinks`，不算先修边。

数据格式参考 [Marble os-taxonomy](https://github.com/withmarbleapp/os-taxonomy)（`topics` + `dependencies`）。

## 规模（会变，以仓库统计为准）

README 量级大致为：一千多个知识点、两千多条先修边、六千多道题、课标条目数百条；数学覆盖小学到高中选必，英语三年级到高中，物理初高中等。在线演示：[math.pansgo.com](https://math.pansgo.com/)。

## 怎么用

```bash
git clone https://github.com/xiaoyang111222/cn-math-taxonomy.git
cd cn-math-taxonomy
python3 scripts/validate.py          # 校验 JSON / 边 / 课标引用等
python3 -m http.server 8000          # 勿用 file://；首页 / 图谱 / 诊断
# http://localhost:8000/
# http://localhost:8000/explore/
# http://localhost:8000/diagnose/
# 英语等：?subject=english …
```

主要数据文件：`data/topics.json`、`dependencies.json`、`questions.json`、`cn-curriculum-standards.json` 等。生产站可用仓库 `./scripts/deploy-cf.sh` 发到 Cloudflare Pages。

## 限制

- **CC BY-NC**：个人学习、教学、研究可免费使用并署名；**付费课程 / App / 机构收费等商用需单独授权**（见仓库 README）。
- 先修边、掌握标准、部分教材目录与课标映射标有「待核」；作者明确希望一线教师审过再用于正式教学路径。
- 高中题与英语题未做盲解复核；部分册次目录来自第三方推定，以仓库「已知局限」为准。
- 英语不出听力/口语题；不是通用作文/网文创作工具。

## 相关

- 本索引其它领域做的是界面、视频、游戏等**创作产出**；本仓属于**教育数据与诊断**分区。
- 格式近亲：Marble [os-taxonomy](https://github.com/withmarbleapp/os-taxonomy)、中文分支讨论见原 README。
