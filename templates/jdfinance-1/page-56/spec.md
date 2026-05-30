# 我的小金库账单页 (page-61) 规格文档

## 视图说明
`page-61` 是“我的小金库”账户的核心账单列表页 (Account Ledger / Transaction History)。
该页面结构清晰，呈现典型的金融账簿流水态：顶部的固定吸顶 Header，灰紫色的大底盘画布，包裹着一个带有 `border-radius: 12px` 倒角的巨幅纯白容器。账单明细被按月份切分流式排布在容器中。

## 零资源前端重构技术概览

### 1. 结构级画布重塑 (Canvas Reset)
相比于之前 58-60 极度黑暗的曜石黑底色，这一页猛然转变为极度明亮的高反差数据表态。
- 根容器 `.bg-canvas` 设置大面积低饱和度浅暖灰紫 `#f7f6fb`。
- 将白色数据容器 `bg-white` 通过 `px-[14px]` 压出左右边距，使白色框体如同浮在背景上一般；由于下方没有被截断的组件，我们利用 `flex-1` 与 `min-h-full` 使白框跟随数据流自然延伸到底。

### 2. 多态列表矢量图标库 (Polymorphic SVG Icons)
在这个长名单结构中，图标复用率极高。
为了彻底杜绝资源文件的拉取，采用了伪元素纯 CSS 进行文字图标生成：
- **还款 `icon-repay`**: 利用 `width: 40px`, `border-radius: 50%`，底板填充 `#ffbf00`，通过 `::after { content: '还' }` 配合绝对对齐，模拟了高清金融 App 的原生圆角图标。
- **转账 `icon-transfer`**: 利用相似逻辑构建了更素雅的香槟褐底色和二字居中。这套模式极大节省了 DOM 节点数量，同时保持了文字的高清抗锯齿能力。

### 3. 数据层级与文字防伪 (Typography Ledgers)
流水列表是金融类产品的核心模块。字体的对比度直接决定了信噪比。
- 大额加粗体 `.item-amount` 限定为安全稳定的 `Arial, sans-serif` 以对抗多平台不同系统字体的数字占宽漂移，维持金额数字的对齐基线。
- 对于附属时间列和余额附属文本（`.item-time`, `.item-balance`），因为无法强制 11px 以下字体尺寸（受限于部分浏览器内核限制），采用了 `transform: scale()` 进行整体缩放，并在 `item-time` 配置了 `transform-origin: left` 而在 `item-balance` 采用了 `transform-origin: right` 确保左贴齐和右贴齐的格式。 
