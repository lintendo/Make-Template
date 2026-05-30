# 白条权益-新手引导弹层 (page-72) 规格文档

## 视图说明
`page-72` 展示了京东金融在用户激活白条权益时触发的强打断式新手引导体验（Walkthrough Overlay）。
全屏幕被暗色蒙层覆盖，页面中央出现核心交互文案与发光滚动提示，并在底部滑出一个圆角的卡片式服务聚合面板（Bottom Sheet Modal）。面板右侧还有一只携带奖杯浮出水面的嘲讽感动态大鹅。这一切都在无本地文件支援的单薄网络请求下，依靠 CSS 重绘来一比一构建。

## 零资源前端重构技术概览

### 1. The Faux Backdrop (伪装底层屏障)
为了在不复制整个巨大而复杂的 `page-71` 组件栈代码的前提下渲染这一个 Overlay，我将背景简化为一个只具备核心外轮廓节点的“影子层”（Shadow DOM Dummy），在绝对定位的 `.dark-mask` 遮罩（`bg-black/85`）下，用户依然能隐约看到模糊且不可交互的 Header、卡券网格和标题，以此营造真实的前后景空间跨栏分离效果，大大减轻了 UI 树的渲染负担。

### 2. Emissive Spotlights (自发光光纤指示器)
在教学提示的最下方有一根极具科技感的发光箭头向下滑动：
我利用了一个 `.glow-dot`（设置 `box-shadow: 0 0 12px white, 0 0 24px rgba(255,255,255,0.8)`）放置于半空的垂直线条 `.glow-line`（`linear-gradient(to bottom, white, transparent)`）顶点，模拟出了强烈带光晕聚焦的下拉锚点针，并在下方的弹窗绑定了一个自下而上的抛物线缓动函数 `animation: slideUp 0.35s cubic-bezier(0.16, 1, 0.3, 1)` 以接管用户的视觉落点。 

### 3. CSS Die-cast 3D Geometry (CSS 压铸立体图标体系)
对于下半部网格化陈列的产品特权小卡片里的 3D 素材，我们重头建立了一套免图片伪 3D 渲染库：
- **Shopping Cart (点我退)**: 应用 `.icon-mock-cart` 对正方形背景使用 `transform: rotate(-10deg) skewX(5deg)` 加不均匀的 `.border-radius` 构建侧面斜切角，配合系统字体的特制 Emoji 实现提物体验。
- **Desk Calendar (延期还款)**: 应用 `.icon-mock-calendar` 利用边框嵌套并在 `::before` 和 `::after` 定位两条穿梭缝引脚圆柱，结合 `#ebf2ff` 渐变色，精确投射出物理日历框台账的质感。
- 除此之外同样附带了右下角漂浮大鸭子的 Emoji 化组装（🦆 + 🕶️ + 🏆）。全程无文件开销实现高保真度。 
