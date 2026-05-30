# Zhipu AI Agents Discover Home Tab

## Overview
A high-fidelity replica mirroring the `page-22` "智能体" (Agents Discovery) core routing tab. Unlike the dedicated search modal from `page-18`, this layout functions as the primary exploratory feed for community-created autonomous agents, driven by categorized horizontal tabs, editor-curated list injections, and a persistent floating creation action.

## Visual Design Details

### Global Navigation Hierarchy
- **Primary Tab Layout**: Replaces the generic back-arrow header with a top-level context switcher.
  - "首页" (Home - Unselected): Muted grey text (`#8A919E`).
  - "智能体" (Agents - Selected): Active black text (`#111111`) pinned with a thick black native underline indicator.
  - Features the standard hamburger sidebar toggle resting in the top-left corner.

### Sub-Navigation Routing (Horizontal Pill Array)
- Located immediately beneath the primary tabs, offering detailed filtering.
- **Pill Styles**:
  - Inactive bounds: `bg-white border border-[#E8EAEF] text-[#111111]`.
  - Active bounds ("精选推荐" / Featured): `bg-[#18191C] text-white border-none`.
- **Layout Logic**: Free-scrolling horizontal flex container seamlessly clipped by a right-aligned linear-gradient fade (`bg-gradient-to-l from-white to-transparent`) which simultaneously houses a sticky magnifying glass search icon.

### Agent Roster Architecture (Editor's Picks)
- **Section Declaration**: Bold standard title "`编辑精选 >`" (Editor's Picks) separating the navigation from the data.
- **Agent Node Identifiers**:
  - Closely matches structural components built in `page-18`, utilizing the same `w-[48px]` circular avatars bounding distinct visual data sets (Custom Photos, Text Badges, Graphic Illustrations).
  - Descriptions wrap effectively across 2 lines simulating heavy persona context (e.g., emojis and specific tone in the Concubine Simulator).
  - Right-bound action node universally displays the unfollowed conversion state (`bg-[#384CF3]` standard Zhipu blue `+` button).

### Floating Action Matrix (Create Agent)
- An absolute positioned wide pill resting centered slightly above the viewport floor.
- **Style Mapping**: `bg-gradient-to-r from-[#3C4EF4] to-[#763AF9]` combining the primary brand blue into a rich deep violet.
- **Shadow Bound**: Projects a heavy colored base shadow to emphasize z-depth above the crowded agent roster below it.
- **Label Payload**: Bold white `+ 创建智能体` (Create Agent) instruction centered inside.
