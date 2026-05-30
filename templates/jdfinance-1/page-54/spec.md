# 财富会员可选权益页 (Lv Selector View) - page-59 规格文档

## 视图说明
`page-59` 是 `page-58` 理财 Hub 页面的顶部极限卷动视图 (Scrolled to Top)。
该页面揭示了隐藏在全局顶部的主横向导航栏（Member Level Selector）：一组排列紧密的 Lv1 到 Lv6 的等宽交互胶囊。

## 零资源前端重构技术概览

### 1. 顶部视口重排 (Viewport Repositioning)
与 page-58 的悬浮导航栏不同，由于本页展示的是完整页面顶部内容，原来的返回键 `<` 和省略号 `...` 已经退回标准文档流中。
- 保留 `pt-[52px]` 以避开真机环境的刘海屏区域。
- 采用 `.section-divider` 左右挂载水平渐变收口来生成中心文字 "财富会员可选权益" 的经典金融质感装饰栏。

### 2. 差集滚动胶囊 (Differential Scroll Pills)
向顶端注入了全新的 `.lv-pill` 混合体系组件群：
- **闲置标（Lv.1, Lv.2, Lv.4...）**: 使用 `.lv-pill-idle` 采用透明背景加微弱的描边 `#332d29` 呈现低光抑制。
- **高活跃标（Lv.3）**: 注入 `.lv-pill-active` 采用深邃的 `#2a1508` 背景，加橙金调色的边框 `#7c4826`，以及高亮的品牌辅色文本，并将其安插在基于 `no-scrollbar` `overflow-x-auto` 驱动的横卷轴中。

### 3. 复用体系验证 (Component Resilience Test)
借由创建这个上游位移视口页面，我们在 page-58 中设计的功能性模块经历了严密的测试：
- **倒角凸起（Upward Fold Tab）**: 基于逆向 CSS `box-shadow` 的反向切角没有因为滚动区域向下推移而出现任何穿模问题，依然完美融合于白色卡牌与黑色流背景。
- **轻量栅格（11-Grid Module）**: 第 4 选项（应急金图标）的绿点事件角标在该截图中处于“已查阅”状态，我们无缝移除了状态角标 `badge-dot-green`，SVG 线稿无任何位置畸变。 
