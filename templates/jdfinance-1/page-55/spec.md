# 全量财富会员大厅页 (page-60) 规格文档

## 视图说明
`page-60` 是财富会员体系的核心主视觉体验页（Hero View）。
相较于之前的 `page-58` 和 `page-59` 只展示导航或权益，该页面在屏幕极顶端展开了一个巨大、具有深空主题氛围与 2 层 3D 特权卡片轮播区的震撼视觉模块。

## 零资源前端重构技术概览

### 1. 深度星云渲染器 (Procedural Starry Background)
我们摒弃了载入高像素背景图像贴图，完全依靠代码生成的宇宙。
- 采用 `.starry-universe` 类内部排布了由十余个 `radial-gradient` 组成的参数化发光白点阵列（尺寸分布 `1px` 到 `2px`，带柔和高斯模糊级不透明度），完全构建了模拟漫反射星空引擎效果。
- 底部利用 `linear-gradient(to bottom, transparent 30%, #0d0a08 90%)` 无缝把太空感过渡消失至平滑的深黑褐色主背景层。这一切均只需数十个字节。

### 2. 双通道无缝拟物卡片墙 (Double Offset Hero Carousel)
在屏幕中上部展示了两组相互错开、呈平行横向漂浮的卡片。
- 基于纯粹的 HTML 结构，赋予外框容器 `.card-purple`, `.card-cyan` 等基于斜向 `145deg` 的冷暖调色温色阶进行打底。
- 背景添加了极具高级感的透明字号叠加水印（通过 `color: rgba(255,255,255,0.035)`、`italic` 及 `48px` 字号来实现诸如 `VIP`, `Fina`, `Card` 的底纹文字）。

### 3. 微型全 CSS 数字雕塑 (Micro CSS-Object Sculpting)
为了保持 “零资产项目” 的严格指令，所有的卡片中央物品均由手作 CSS 画制或使用原生极简 SVG 装配。
- **理财师 (Financial Advisor)**：构建了由半圆脸庞、西装倒 V 字领构筑而成的拟物扁平化小金人化身。
- **京东 E 卡**：采用 `-rotate-[6deg]` 和边沿阴影，配置内发光黄金芯片电路 `.w-[12px].h-[8px].border-[#ffefa1].opacity-70`，以及标志性的 JD `font-black italic` 发光字标。
- **红包叠加与折角（Red Envelopes/Sacks）**：利用绝对定位叠层与深红、金黄色背景渐变构造伪 3D 纸张叠加形态。
- 一切渲染均实时运作，响应敏捷。 
