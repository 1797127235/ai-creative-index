# reanimate

[← 返回动效与动画](./README.md) · [仓库](https://github.com/NiazMorshed2007/reanimate) · [演示视频](https://reanimate.niazmorshed.dev/demo.mp4)

`MIT` · Claude Code skill · 逆向任意动画 · 复刻后逐帧比对

## 它是什么

给 agent 补上「看得见动作」和「知道自己差多远」两件事。你指一个链接、一段录屏、一个 mp4/gif、一个 Lottie，它把参考**录下来 → 拆成参数 → 用你项目现有技术重写 → 用同样的方法录一遍 → 对比 → 改最大的一处 → 再录**，通常 2–5 轮收敛；5 轮还差的地方会写进报告并说明原因。

和 [animate](./animate.md) 正好一攻一守：animate 从零生成新片，reanimate 把别人的动效抄到只剩参数。

## 五步

1. **Record** —— 无头浏览器固定视口和帧率录：视频、编号帧、找到的每条 CSS / Web Animations 动画、指定元素每帧位置。canvas/WebGL 另外追踪 GPU 调用（shader、uniform、draw call、three.js 场景），并把时钟变成逐帧推进的虚拟时钟，保证每次抓取完全一致。
2. **Spec** —— 每个元素每个属性一行：起止、时长、from → to、缓动、stagger；没读数的地方标 `?`。
3. **Build** —— 用你项目已有的技术写：CSS、Framer Motion、GSAP、three.js。
4. **Verify** —— 同样方式录副本，比时序、缓动、像素，出并排对比图。
5. **Repeat** —— 修最大差异再录，2–5 轮。

## 三档匹配强度

| 你说 | 档位 | 必须对齐 |
|---|---|---|
| 「clone this animation」 | 动得一样（默认） | 触发、顺序、stagger、时序 ±80 ms、缓动族、位移 |
| 「match it exactly」「pixel-perfect」 | 长得也一样 | 上面全部 + 字体字号颜色间距素材，平均像素差 ≤ 2% |
| 「clone X and add Y」 | 你的改动叠在上面 | 克隆部分按上面档位，新增部分单独保留 |

## 实测成绩（仓库自报）

14 个站点级动效，多数 30–90 分钟一次跑完：Vercel 工具栏 417/417 帧全同；Fluid ocean（262,144 个点）12 秒 0 px 差；速度表悬停 0 px；Stripe 发卡 tilt 落在 0.4 px 内；Resend 魔方 25 秒每次旋转精确。这些都是**作者自己跑的**，不是你的环境。

## 安装

```bash
npx skills add NiazMorshed2007/reanimate -g
```

需要 **Bun 1.1+**、macOS 或 Linux（Windows 未测）。首次运行会装静态 ffmpeg + Playwright Chromium，约 250 MB。**不需要 API key**。其他读 `SKILL.md` 的 agent 也能装，但只在 Claude Code 上测过。

## 限制

- 登录后的页面、YouTube、Loom 录不了，得先给录屏。
- 弹簧参数是从过冲和稳定时间**拟合**出来的，不是从源码读的。
- Worker 会被 seed 和追踪，但它们自己的时钟仍按真实时间走；iframe 里的 canvas 需要单独给 iframe 的 URL。
- 副本复现不了参考的随机数生成器时，粒子改成按密度/颜色/运动模糊比对，不再逐点比。
- `--gpu hardware` 走真 GPU（macOS Metal；Linux Vulkan 未测），默认 SwiftShader 更慢但每台机器像素一致。
- **版权**：它只克隆你指的东西；别人的字体、图片、代码仍归对方，能不能用要你自己判断。

## 相关

- [animate](./animate.md) —— 正向生成：一个 canvas + 程序化配乐渲成 MP4。
- [dimensional-drawing](../web-ui/dimensional-drawing.md) —— UI 规格图的笔绘 + 镜头动效。
- [scroll-world](../web-ui/scroll-world.md) —— 滚动 scrub 的整页动效，适合用 reanimate 逆向参考站。
- [gsap-skills](./gsap-skills.md) —— 克隆后的动效要写得对，靠这套官方 GSAP skill。