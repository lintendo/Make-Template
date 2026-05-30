# 车险免息券权益详情页 (page-57) 规格文档

## 视图说明
`page-57` 是一张全新的独立详情二级页面，名为 "权益说明" (Equity/Privilege Details)。
页面主要结构分为三个层级：顶部的水平滚动权益列表（带黑色渐变背景）、中段悬浮的浅黄色权益激活 Banner（具有巨幅的水印），以及底部的纯文本长规则列表区域。

## 零资源前端重构技术概览

### 1. 结构级视差嵌套与曲线缝合 (Visual Hierarchy Stitching)
本页的布局并没有采用粗放的模块拼凑，而是在 Banner 与 Navbar 之间实施了精准的 “视觉下钻” 效果。
- **暗黑导航区**: 使用 `.dark-equity-header` 铺垫具有金属黑褐光泽的底层背景。
- **白洞突破区 (Banner)**: 利用负值的 `mt-[-35px]` 与 `rounded-t-[25px]` 的属性，强制让白金权益主横幅从纯白背景中延展上来生硬地遮盖掉黑褐背景的直男硬边界，创造了极度圆润优美的曲线过渡。
- 采用 `.equity-hero-banner::before` 的复合径向渐变伪层模拟光晕，以此代替大型背景贴图的导入负担。

### 2. 多态等比图标与视觉降级 (Multi-state Icon Component)
在顶部的水平组件流中包含当前选中态的 “车险免息券” 以及待查阅的其他周边产品标签。
基于 CSS 面向对象的设计思想，我们没有暴力拆解为独立类，而是设计了变体结构：
- **闲置状态（Idle）**: 通过 `.equity-icon-idle` 压缩内部光源内阴影 (inset shadow)、应用深黑色调并结合默认的 `transform: scale(0.85)` 与 `opacity` 设置被动弱化视觉等级。
- **高光焦点（Active）**: `.equity-icon-active` 利用了反向发散光 `box-shadow` 以及浅一色阶的背板颜色（`#5c4331`），且包含特有的外发框 `outline outline-[#fbd6ac]/30` 达成浮雕高亮反馈。内部图形全部替换为 Tailwind 原生 SVG 以免除向服务请求图像。

### 3. 排版体系与巨幅水印系统 (Typography & Watermark)
- 详情正文排版（Rules/Description Area）：将原图中不同权益等级（Lv.6 - Lv.1）对颜色明度的阶梯下降表现做代码枚举式映射：`lv-dark`, `lv-mid`, `lv-light`。利用一致的 flex 框架确保数据呈现完美对齐对账簿形态。
- 通过 `.section-title::after` 无损制作出具有荧光效果的底端黄标下划线。
- 在 Banner 左边，生成了巨大的 `.watermark-text` 挂载着 `EQUITY`；它凭借巨大的字号并使用混合纯白字体的手段，实现了和传统 iOS 透明蒙版一致的高定视觉效果。 
