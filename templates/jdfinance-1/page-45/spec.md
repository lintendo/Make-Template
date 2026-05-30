# 定期理财页 (page-46) 规格文档

## 视图说明
`page-46` 呈现的是京东金融“定期理财”产品的聚合页。
页面顶部拥有非常强烈的品牌视觉区，通过 3D 渲染图表表现资金从活期向定期的流转过程。主体区域则是一个经典的理财产品垂直列表页（Yield List Grid）。整体采用极简但高对比度的橙/红暖色调包裹用户。

## 零资源前端重构技术概览

### 1. 标题排版引擎 (Mega Typography Engine)
首屏的视觉重心是巨大的 "定期理财" 四个字。这并非单纯的 HTML 文本框：
为了实现原图中加粗倾斜且带有外发光描边的厚重视觉感，使用 `.mega-slant-title` 进行了多维度的 CSS 骇客操作：
- `transform: skewX(-12deg)` 赋予文字前倾速度感。
- `text-shadow: 2px 2px 0px #ffe1b3, -1px -1px 0px #fff` 利用阴影阵列在右下方压出底色的“块面深度”，并同时做了一个细微的反向白色切边防止与背景糊接。
- 使用 `::after` 搭载同文克隆体置于底部层级（`z-index: -1`）并施加 `-webkit-text-stroke: 1px #d97706` 强行包裹一层橙色物理描线。

### 2.等距 3D 柱体系统 (CSS Isometric Geometry)
原设计图右上侧陈列了两个具备空间几何感的流转柱子（小金库 -> 定期理财）。在这里我们没有引入图片资源：
完全由 CSS `border-radius: 50%` 所带来的透视错觉实现。
- 每个对象 (`.cylinder-orange`, `.cylinder-red`) 分解为包含 `linear-gradient` 的主柱身底图。
- 伪类 `::before` 压在顶部构建顶部反射圆截面 (`radial-gradient`)。
- 伪类 `::after` 搭载 `box-shadow` 在底部构建厚度底托切面。
- 中间的折线转移箭头 (`.transfer-arrow`) 也是利用了 `border-right`, `border-top` 以及 `border-radius: 100%` 进行四分之一弯折处理，再加上 css triangle 切割成型。完美实现了场景抽象与叙事分离。

### 3. 数据网格复现 (Dynamic Product Listing)
底部的滚动条目使用了标准的单维度数据映射。对于理财组件内标签“福利”（`text-[#b57342] bg-white border`）应用了 `scale-90` 以在不降低浏览器基础 12px 字体门槛下仍能保持极致娇小的角标设计。
操作按钮 `.bg-gradient-to-r` 调配了向右渐近变暗的暖橘色物理渐变，引导强烈的交互点击感。
