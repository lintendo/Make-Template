# 家庭应急金 - 保自己 (page-27) 规格文档

## 视图说明
本页面展现了京东金融APP“家庭应急金”板块中，横向 Tab 导航切换到“保自己” (Self Allocation) 视角的交互形态。
由于它是 `page-26` 同级姊妹模块，其底部双层浮动导航架构完全一致；但在视觉内容上引入了内联高亮的 Tab 切换吸顶菜单（Sticky Header）以及新的结构化导购组合。

## 布局体系与核心异构复现

1. **吸顶导航池构建 (Sticky Nav Matrix)**
   - 除了极简的 `top-0` 纯白标题栏外，此模块增设了一层全局子菜单横向 TabBar (`保自己`, `保父母`, 等)。
   - 对这个子级菜单应用了 `sticky top-[52px]` 的接力吸顶交互栈，配合原生的 `overflow-x-auto scrollbar-hide`，完美实现了在短屏手机下的横向滑动切换能力。
   - 对当前激活态 `保自己` 采取了 `20px`大字重和底部附着的物理粗下划线 (`absolute bottom-[-5px]`) 渲染法。

2. **多态推荐卡堆叠 (Polymorphic Recommendation Grid)**
   - 包含两大区块的复现，针对 `推荐` 区与 `优先配置医疗险` 区进行了精准拆解。
   - 第一区块主图是医生肖像，在此继续沿用极低成本的 0 文件架构（Zero Asset Layout）。我新建了专属的 `.mock-photo-doc` CSS 蓝白冷色系渐变，用于模拟高像素的医疗专业影像。

3. **越界视觉标签刺穿 (OOB Clipping Tag)**
   - 在主推的“惠民保”医生卡片左上角，存在一个 “健告宽松” (Loose Health Constraints) 的警告贴片。
   - 这并非普通的内嵌 tag，而是利用了 `absolute top-0 left-0` 强行覆盖在图片的切口圆角上，并且手工赋予它 `rounded-br-[6px] rounded-tl-lg` 的异形边界，形成无缝咬合在图片相框内的强迫式视觉刺穿效果，1:1 完全仿制了原稿中的压迫式营销排版。
