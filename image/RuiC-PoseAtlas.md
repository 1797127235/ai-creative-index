# RuiC-PoseAtlas

[← 返回图像生成与编辑](./README.md) · [仓库](https://github.com/HRuiCcc/RuiC-PoseAtlas) · [在线图鉴](https://hruiccc.github.io/RuiC-PoseAtlas/)

`MIT`（站点代码）· 图片另有版权约定 · 姿态 / 衣装 / 人像三图鉴 · 纯静态零依赖

## 它是什么

给 AI 作图用的**视觉参考站**：把「人体怎么摆」「衣服怎么穿」「脸长什么样」收进同一套静态站。中 / 英 / 日切换，可搜索筛选、键盘浏览、下原图。**不生成图像**——你挑好参考，再丢进自己的生图工具（垫图、ControlNet、角色一致性等）。

典型用法：**姿势定骨架 → 衣装定皮相 → 人像定脸**，三份参考一起喂模型。

## 三个图鉴

| 图鉴 | 规模（约） | 特点 |
|---|---|---|
| 姿势 | 288 组 × 5 视角，共 1439 张 | 去脸人台线稿；正面 / 斜侧 / 侧面 / 俯视 / 仰视同卡可比 |
| 衣装 | 1407 套，8 分类，86 个三语标签 | **无人**整身穿搭；颜色 / 材质 / 版型 / 鞋包可检索，可直接套角色 |
| 人像 | 1499 张（脸部 893 + 造型 606） | AI 虚构人像；按发型筛选；脸部偏固定角色脸，造型偏氛围 |

资源也提供夸克网盘打包（姿势 / 服装 / 脸库体积较大）；站点本身只依赖静态托管。

## 怎么用

```sh
git clone https://github.com/HRuiCcc/RuiC-PoseAtlas.git
cd RuiC-PoseAtlas
# 任意静态服务器，例如：
python3 -m http.server 8080
```

或直接打开 [在线演示](https://hruiccc.github.io/RuiC-PoseAtlas/)。也可部署到 GitHub Pages / Cloudflare Pages / Netlify 等。

## 限制与合规

- **面向成年创作者**；部分衣装分类偏成人向，请按当地法规与平台规范使用。
- 图像均为 **AI 生成的虚构素材**，勿用于冒充真人等违规用途。
- **MIT 只覆盖代码 / 样式 / 脚本 / 文档**；`img/`、`thumbs/` 等图片与部分原始数据**禁止再分发、转载、转售图片数据本身**（创作参考与商用边界以仓库 README「致谢与版权」为准；人像原站多为 CC0，但仍请求勿转载全尺寸文件）。

## 相关

- [handraw-style](./handraw-style.md) — 风格编号 → 双语提示词 Skill；本仓是可浏览的垫图参考库。
- [scenario-labs/skills](../studio/scenario-skills.md) / [Easel](../studio/easel.md) — 出图工作流；可拿本图鉴当参考输入。
