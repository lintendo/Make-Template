# 白金合伙人顶部首屏 (page-51) 规格文档

## 视图说明
`page-51` 是与 `page-50` 共享核心设计的“白金合伙人”顶部主屏部分。相比于中段的内容，本卡片承载了活动的首要转化入口——顶部的三项红包兑换卡片组件，以及带有强烈手绘记号笔风格的“战略攻略”大标题。

## 零资源前端重构技术概览

### 1. 手写粗糙下划线错觉 (Hand-Drawn Rough Underline)
在标题“白金合伙人攻略”底下，有一道像橙色记号笔随意横扫的粗斜线。我们使用了 `.rough-underline` 的纯 DOM 方法：
先设定主块偏移到底部 (`bottom: 2px`)，对其施加复合型三维扭曲矩阵 `transform: rotate(-3deg) skewX(-20deg)` 获得毛糙的透视倾斜感。同时为了模仿马克笔起笔或收笔时的“墨水倒流”停顿痕迹，利用伪类 `::after` 搭载了一块稍小但拥有反向旋转角 (`rotate(5deg)`) 的短柄块拼接在右下侧末端。从而完全实现了极简矢量风格的假手绘线条。

### 2. 微型结构复用与 DOM 层覆盖 (Macro Component Reuse & Z-INDEX Targeting)
在 `.css-hand-pointer` 指示器上，这一次被挂载在左侧的【小金库红包】去兑换按钮上方。
- 利用基于父容器卡片的 `relative` 定位，将指尖定位至 `absolute -bottom-[16px] right-[-10px]`。
- 为了控制 UI 的呼吸感，对其应用了 `scale-[0.8] origin-bottom-right` 进行微缩，而不破坏我们在 Page-50 研发出的精巧指节组装逻辑。

### 3. 多列横滑兑换台 (Scrollable Flex Columns)
顶部的三个抽屉卡片采用原生移动端滑动交互结构：
- `flex space-x-[12px] overflow-x-auto no-scrollbar`。
- 将每个 Item 置为 `flex-shrink-0` 及固定宽度 `w-[110px]` 定型。
- 【动态与静态】的视觉分离：激活状态采用了硬红边框 `#f04a4b` 搭配淡红透明阴影 `shadow-[0_4px_10px_rgba(240,74,75,0.15)]` 造成实体感；而未达到兑换标准的卡片则使用灰色边框和低限度阴影沉降以突出视觉层级。
