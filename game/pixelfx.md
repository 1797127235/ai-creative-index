# pixelfx

[← 返回游戏](./README.md) · [仓库](https://github.com/patch-gg/pixelfx)

`MIT` · 244 个像素特效（纯代码）· 网页实时播 / 改色镜像 / 导出精灵图 · 附 Claude Code skill

## 它是什么

像素特效**不是贴图包**，每个效果是一小段 JS：在真像素分辨率里画，再最近邻放大。可以：

- 嵌进 canvas / Phaser / Pixi / Kaplay / three.js 等网页游戏循环；
- `node tools/render.mjs … --sheet` 导出透明精灵图 + Aseprite 风格 JSON，进 Godot / Unity / GameMaker 等；
- 换 `palette`（暗→亮色带）让同一火变蓝、同一治疗变粉，不用改效果源码。

分类覆盖：打击、弹道、出生死亡、奥术、神圣、暗影、状态、自然、天气、UI、拾取、转场、小生物等（完整表见 `docs/CATALOG.md`）。文件在 `src/fx/<category>/<name>.js`。

## 怎么用（代码）

```js
import { createFrame, clearFrame, createFx, composite } from "pixelfx";
import * as frostNova from "pixelfx/fx/ice/frost-nova";

const frame = createFrame(320, 180);
const img = new ImageData(320, 180);
const fx = createFx(frostNova, { x: 160, y: 140 }); // flip, angle, seed, palette, light…

function tick(dt) {
  fx.update(dt);
  clearFrame(frame);
  fx.draw(frame, "back");
  drawCharacters();
  fx.draw(frame, "front");
  composite(frame, img.data, backgroundColor);
  ctx.putImageData(img, 0, 0); // CSS: image-rendering: pixelated
}
```

安装：`npm i github:patch-gg/pixelfx`，或只拷 `src/core` 和需要的效果。

## 精灵图与演出

```bash
node tools/render.mjs ice/frost-nova --sheet
node tools/sheets.mjs   # 整库导出到 sheets/
```

很多带角色的效果还定义了 **act**（预备、命中冻结、后摇、受击位移），用 `createAct` 可连角色一起播，避免特效像贴纸。

## Claude Code skill

仓库附 skill：按像素美术师习惯 **草稿 → 渲染 → 看 → 修** 做新效果，而不是一次生成丢进库。适合在现有 catalog 风格上扩招。

## 限制

- 视觉是**程序化像素**，不是手绘 sprite 集；要手绘风得自己画或只当参考节奏。
- 网页路径零依赖；引擎路径靠导出 sheet，要自己接 atlas 导入。
- 新效果要会读 `act` / 分层 `back|front`，否则容易「只有光、没有打击感」。

## 相关

- [Claude-Code-Game-Studios](./Claude-Code-Game-Studios.md) — 整馆游戏制作流程；素材层可喂 pixelfx。
