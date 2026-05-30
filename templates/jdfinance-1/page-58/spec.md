# 京东小金库促销弹窗页 (page-63) 规格文档

## 视图说明
`page-63` 并不是一个独立的全屏路由容器，而是一个半透明遮罩背景叠加 **Bottom Sheet（底部抽屉弹窗）** 的交互界面。
它用以模拟用户进入小金库并触发了“拉新体验促销”的流程，强调巨大的诱导红包与理财产品转化。该页面的构建包括了一个假想背景层的置底虚化，以及前端弹窗实体。

## 零资源前端重构技术概览

### 1. 双重背景隔离 (Dual-Layer Context)
- **模拟被压住的应用底板 (`.bg-underlay`)**：使用包含多色径向渐变的底层代码 `linear-gradient` 与 `radial-gradient` 重建了带有暗红色泛光的资产页背板，然后铺上一层包含 `backdrop-blur-md` 和白透处理 `.bg-white/70` 的框架容器骗过视觉，充当假应用背景。
- **全局沉浸遮罩 (`.dark-mask`)**：基于 `fixed` 与 `zh-index: 40` 在页面铺设一层透黑蒙版 `rgba(0,0,0,0.6)`，以将用户视觉完全逼入中央弹窗。

### 2. 金融票据解构 (Ledger Typography Component)
提取于金融发票/账本概念，将巨大的金额数字 "¥5.24" 衬于细线方格带下：
在 `.ledger-lines-behind::before` 中使用了 `linear-gradient(rgba(240,240,240,0.8) 1px, transparent 1px)` 背景参数绘制了密集的账本虚化辅助线，让巨型 `60px` Arial 数字漂浮在刻度线网络上，增加质感。

### 3. CSS 微交互：触控引导动效 (Touch Assist Animation)
为了精确重构截图右下角“手指按压按钮”的诱导提示，利用纯代码制作了微动作向导：
- **脉冲涟漪 (`.ripple-ring`)**: 利用 `@keyframes ripplePulse` 构建了一个由小变大并逐步消散缩略的光环 `transform: scale()`, `opacity`, 及 `border-width`。
- ** Emoji 视效替身 (`.mock-cursor-hand`)**: 由于无切图策略限制了加载外部真实手掌模型的可能性，直接注入原生 Apple Color Emoji `👆🏻`，并对其进行 `-15deg` 的自然倾斜并叠加巨大的文本高斯边缘阴影 `text-shadow`，使其模拟真实 3D 物体漂浮于按钮（`立即体验200元`）上方的质感。
