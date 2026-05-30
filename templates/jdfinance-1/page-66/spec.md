# 白条权益页-V1解禁态 (page-71) 规格文档

## 视图说明
`page-71` 为京东金融“白条权益”页面轮播至 V1 用户级别时的展示切片。
与之前的 V2 冰蓝未解锁状态不同，此态下的色调转变为生机勃勃的湖青色（Teal）。最重要的展示逻辑变化是：由于 V1 作为基础等级已经被用户点亮，下方的所有券包操作动作从蒙版上锁态被批量替换为大红色的“选这个”交互态。

## 零资源前端重构技术概览

### 1. The Teal Ice Palette (薄荷冰川环境场切换)
由于卡片与页面的互动，整个屏幕的统领色系发生移位。
- 底层渲染器 `.bg-ice-page` 从 `#dbefff` 更新为 `#dcf0eb` 的薄荷绿高光过渡。
- VIP主容器 `.vip-card` 收敛为 `linear-gradient(135deg, #effcf6 0%, #e2f4f2 100%)`。所有的颜色重置都被提纯在 `style.css` 中，这为将来支持根据不同卡片滑动而平滑插值演变整个 App 背景颜色的动效打下了代码级的数据基座。

### 2. State Mapping & Centered Anchor (状态映射与中心锚点抽离)
进度条 UI 此刻 V1 取代了 V2 成为了屏幕的正中央锚点：
- **物理填补**: 在 `.v-track-container` 中，为了在保持响应式均分的条件下将左数第一个组件强行逼进中央，插入了空节点 `<div className="v-node"></div>` 占据了 `-1` 位，使得 V1 成功顶入 `0` 位中轴。
- **进度轨阻断**: 原本从左至右长条连贯的氛围线 `.v-line` 也因为没有了前置条件，它被截断修改为从屏幕圆心出发向右衰减 (`left: 50%; width: 50%; background: linear-gradient(#8cd1c2, transparent);`) 表现这正是起始之基。

### 3. Red-Pill Ticket Activation (券池满血激活态)
所有被锁定的灰色打孔券按钮 `.btn-lock` 在 V1 状态中激活：
- 组件级替换成了 `.btn-red-pill`，挂载了高强度对比度的主红色渐变 `linear-gradient(to right, #fc584f, #f53d31)` 以及对应的深红色阴影反馈，并在组件层面上赋予了对应的 `cursor-pointer active:opacity-80` 真机点按阻尼仿真。 
