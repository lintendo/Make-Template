# 白金合伙人 (page-50) 规格文档

## 视图说明
`page-50` 是专门用来阐述“白金合伙人”如何通过（打白条 + 小金库攒钱）双管齐下赚取双倍金币收益的营销概念长页。
页面中段（也是视觉中心点）设计了 4 颗悬浮的动态气泡球，分别展示了四大赚钱路径所获的金币资产。底部的流程图块通过结构线串联起两个大圆球 icon 进行核心模式总结。

## 零资源前端重构技术概览

### 1. 悬浮金币气泡的物理模拟 (Floating Coin Bubbles)
中段的 `.floating-coin-bubble` 群组不依赖 SVG 或任何位图。
- 采用 `radial-gradient` 对背景着色，制造出一个发光球体错觉；配合内外阴影 `box-shadow: inset ...` 构建出了玻璃弹珠的折射质感。
- 其中镶嵌的“金币” `.css-gold-coin` 更是百分百 CSS 渲染。使用了 `linear-gradient` 的对角线映射（135度），辅以硬描边内发光来打造金属反射。
- 为了赋予气泡生命力，配置了 3 组速度、延迟各异的 `float-up-down` `@keyframes` 浮空动画（`animate-float-slow/fast/slower`），让并排的四个球产生无序但不杂乱的漂浮水泡物理效果。

### 2. 虚拟交互手势指针 (Virtual Hand Pointer)
在第四个最大的气泡旁边有一个“手指点击”的视觉暗示。在缺少素材图的情况下，我编写了 `.css-hand-pointer` 组件。采用主盒子加两组伪类，通过精算的角度旋转（`transform: rotate(-15deg)`）和非对称多边形弧度，拼贴出了具有二维透视感的肉色三维手指模型图，指向主收益气泡。

### 3. 可伸缩微图腾阵列 (Scalable Micro-Totems)
- 文案段落中不仅有文字，还内联了极小尺寸的插图来辅助阅读。
- 比如硬文案中的“200金币”，其后方紧贴了一个缩小版金牌 `.inline-flex.items-center.justify-center... scale-[0.6]`。
- 同样，底部模式总结卡片中的超级大图标（红白条 `.css-doc-icon` 和 笑脸包 `.css-wallet-icon`）全部使用基础的 border 压角技术和伪类附加层搭建，它们能够与 `currentColor` 保持环境统一，展现极简响应特征。 
