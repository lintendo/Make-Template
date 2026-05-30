# 维生素社区版 WMS 原型

## 📋 业务与功能

### 1.1 核心目标
将 Figma Make 导出的 WMS 多页面设计系统项目收敛为 Axhub 可直接消费的单入口原型，同时保留原始设计系统预览、业务页面示例和局部状态切换能力，确保后续 Axhub 预览与 Figma Make 导出共用同一套页面主体实现。

### 1.2 功能清单
- **设计系统总览**：展示颜色、阴影、间距、字体、图标、动画、数据格式、状态组件、设计模式和参考页面。
- **参考页面浏览**：以卡片目录方式浏览 20+ 个 WMS 示例页面，覆盖首页、入库、出库、库存、基础资料等模块。
- **单页面内切换**：通过组件内状态在“设计系统总览”和具体业务页之间切换，不依赖浏览器路由。
- **业务页复用**：复用 `src/pages/**` 和 `src/components/layouts/WMSLayout.tsx` 中的现有页面视觉与交互。
- **双入口同步**：根目录 `index.tsx` 与 `src/App.tsx` 共用 `src/components/WmsCommunityPrototype.tsx`，避免运行时入口漂移。

### 1.3 交互要点
- 在“参考页面”卡片区点击页面卡片，进入对应业务页面。
- 业务页面通过 `onNavigate` 回调触发本地状态切换，模拟原始路由跳转。
- 设计系统总览中的 Tabs 用于切换不同 Token 和模式预览模块。
- 根目录入口和 Figma 导出壳子均不自行维护业务视图，只挂载共享主体。

---

## 📊 内容规划

### 2.1 信息架构

```text
维生素社区版 WMS 原型
├── Axhub 运行时入口（index.tsx）
├── 样式桥接（style.css / src/index.css）
├── 共享主体（src/components/WmsCommunityPrototype.tsx）
│   ├── 设计系统总览
│   │   ├── Token 预览 Tabs
│   │   ├── 状态组件展示
│   │   └── 参考页面目录
│   └── 业务页面示例
│       ├── 首页工作台
│       ├── 入库 / 上架 / 到货扫描
│       ├── 出库 / 波次 / 播种 / 复核
│       ├── 库存查询 / 库存流水
│       └── 基础资料管理
├── Figma 导出壳子（src/App.tsx / src/main.tsx）
└── 原始页面与组件（src/pages/** / src/components/ui/** / src/components/wms/**）
```

### 2.2 数据来源
- **设计规范数据**：来源于 [DESIGN_SYSTEM_GUIDE.md](/Users/jianzhoulin/rd/Axhub Runtime/apps/axhub-make/src/prototypes/wms-by-vitamin-community/src/DESIGN_SYSTEM_GUIDE.md)、[TOKEN_REFERENCE.md](/Users/jianzhoulin/rd/Axhub Runtime/apps/axhub-make/src/prototypes/wms-by-vitamin-community/src/TOKEN_REFERENCE.md) 和 [globals.css](/Users/jianzhoulin/rd/Axhub Runtime/apps/axhub-make/src/prototypes/wms-by-vitamin-community/src/styles/globals.css)。
- **页面内容数据**：使用 `src/pages/**` 中的静态模拟业务数据。
- **关键字段**：
  - `id` / `name` / `category` / `description` / `tags`：用于参考页面目录展示和切换。
  - `currentPage`：共享主体内部的当前展示页面状态。
  - 各业务页内部列表、状态、统计字段：用于保留原始 Figma Make 页面内容密度。

### 2.3 内容示例
- 总览态默认展示 WMS Design System 的可视化预览。
- 参考页面目录包含“工作台”“入库单列表”“出库单列表”“库存查询”“客户管理”等业务入口。
- 详情页、操作页和管理页仍保留原始模拟数据、状态色和局部操作反馈。

### 2.4 工程结构
- 根目录 `index.tsx` 仅作为 Axhub runtime adapter。
- `src/App.tsx` 仅作为 Figma export shell。
- `src/main.tsx` 仅作为 Vite mount。
- 共享页面主体统一沉淀在 [WmsCommunityPrototype.tsx](/Users/jianzhoulin/rd/Axhub Runtime/apps/axhub-make/src/prototypes/wms-by-vitamin-community/src/components/WmsCommunityPrototype.tsx)。
- 样式通过根目录 [style.css](/Users/jianzhoulin/rd/Axhub Runtime/apps/axhub-make/src/prototypes/wms-by-vitamin-community/style.css) 和 [index.css](/Users/jianzhoulin/rd/Axhub Runtime/apps/axhub-make/src/prototypes/wms-by-vitamin-community/src/index.css) 桥接到 [globals.css](/Users/jianzhoulin/rd/Axhub Runtime/apps/axhub-make/src/prototypes/wms-by-vitamin-community/src/styles/globals.css)。

---

## 🎨 布局与结构

### 3.1 整体布局
- **布局模式**：桌面端信息密集型后台布局 + 设计系统目录页。
- **容器宽度**：总览页使用居中内容容器，业务页使用 `WMSLayout` 提供的侧边导航 + 顶栏 + 主内容区。
- **关键尺寸**：
  - 总览页顶栏：固定吸顶头部，承载标题与版本信息。
  - 总览页内容区：多卡片、多列网格，重点展示 Tokens 和参考页面。
  - 业务页主框架：左侧菜单约 240px，右侧为表格、卡片和详情内容区。

### 3.2 响应式适配
- **桌面端（≥1200px）**：优先保证 WMS 管理界面的信息密度和多列布局。
- **平板端（768-1199px）**：总览页卡片自然换行，业务页滚动展示表格与卡片。
- **移动端（<768px）**：不额外重构业务页结构，保持 Tailwind 自适应和滚动浏览能力，满足原型预览需求。

---

## 🎨 视觉规范

### 4.1 设计规范来源
**设计规范来源**：用户规范 [DESIGN_SYSTEM_GUIDE.md](/Users/jianzhoulin/rd/Axhub Runtime/apps/axhub-make/src/prototypes/wms-by-vitamin-community/src/DESIGN_SYSTEM_GUIDE.md)

**说明**：设计令牌由 [globals.css](/Users/jianzhoulin/rd/Axhub Runtime/apps/axhub-make/src/prototypes/wms-by-vitamin-community/src/styles/globals.css) 提供，使用紫色科技风、紧凑字号和高信息密度表格规范。

### 4.2 自定义设计要点
- **主题方向**：紫色品牌色 + 中性灰背景层次，符合原始 WMS Design System。
- **样式桥接策略**：
  - 根目录 `style.css` 第一行固定为 `@import "tailwindcss";`
  - `src/index.css` 仅作为 Figma Make 导出壳子的桥接层
  - 共享视觉样式和 Tokens 统一保留在 `src/styles/globals.css`
- **页面收敛策略**：不保留浏览器路由，改为共享主体内的状态切换。

### 4.3 组件状态
- **默认态（default）**：展示设计系统总览页。
- **浏览态（browse）**：显示参考页面目录卡片，可进入具体业务页。
- **页面态（page-active）**：展示某个业务页，并提供返回总览的入口。
- **加载态（loading）**：通过 `LoadingState` 组件演示。
- **空态 / 错误态**：通过 `EmptyState`、`ErrorState` 组件演示。
