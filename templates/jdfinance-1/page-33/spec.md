# 基金档案 - 完整卷轴 (page-34) 规格文档

## 视图说明
`page-34` 展示了 `page-33` 的“天灵盖”也就是真实的卷轴最顶端。
它揭示了“基金档案”这四字的真正阵列内容：深度图表式的数据大盘，以及基金管理人的信息看板。在完成这一页之后，这份金融档案面板获得了逻辑闭环。

## 零资源图表组件重构 (Zero-Asset Data Visualization)

这页最核心的难点在于左右排布的微型可视化图表区。常规操作必然导致引入 `Recharts` 或者 `ECharts` 这类的巨型图表库。但在移动端极限 UI 复刻中，我仅仅通过原生 CSS 在 React 树内渲染完成了它们。

1. **内联微缩柱状图 (Inline Micro Bar Chart)**
   - 处于左侧的“基金规模”下方有四根逐渐登高的柱子。
   - 使用了极致简洁的 Flexbox `items-end` 将底部锚定。
   - 针对四根柱石使用按比例的绝对高度 `h-[15%]` 至 `h-[95%]` 控制。
   - 第四根核心柱石单独赋予 `bg-gradient-to-t` 红晕渐变与微量的红色倒影盒阴影 (`shadow-[0_-2px_10px_...]`)，复刻出了数据可视化的高端氛围且体积为零。加上按比例的 `group-hover` 高度位移变换，它仿佛是自带呼吸逻辑的组件。

2. **现代 CSS 半弧线图 (Modern Conic Gradient Half-Donut Chart)**
   - 右侧“机构占比”部分需要一个完美平滑的圆弧进度条。
   - 不选择使用繁重的 SVG `<path>` 画弧与描边技术。我定义了 `.donut-chart-modern`：纯正的现代 CSS 魔法——使用 `conic-gradient()` ！
   - 通过映射圆周角：`conic-gradient(from 270deg, #f7ac53 0%, #f7ac53 8.79%, #eaebf0 8.79%, #eaebf0 50%, transparent 50%)`，极其精准的切割出橙色的 8.79% 进度，背景留灰。
   - 最后叠加一个 `.donut-chart-cutout` 纯色遮罩罩在中央底部掏空，瞬息之间成就了一张原生 UI 级别的数据透视环。

3. **化身裁剪 (Avatar Silhouettes)**
   - 基金经理照片占位处再一次利用到了复合叠加 `background: radial-gradient` 与 `#22232a` 的西装边缘。即使你没有配置外部图片，原生的代码也构成了一个具有体量感的“西装高管”视觉占位符。
