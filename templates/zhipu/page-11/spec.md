# Zhipu Sidebar Drawer

## Overview
A high-fidelity replica mirroring the `page-11` left slide-out navigational side drawer. This view hosts user account status, global library routes (Works, Agents), and extensive chat history filtering overlaying the main agent application grid.

## Visual Design Details

### Application Mock Backdrop
- A lightly simulated dimming overlay (`bg-black/45`) masks the contextual base app.
- System metrics (top notification/signal indicators) remain absolute topmost rendered items (`z-50`).

### The Slider Drawer (Left)
- **Container Structure**: `w-[84%]` scaling limit constrained to typical mobile overlay dimension boundaries. Rounded heavily on the right side (`rounded-r-[24px]`).
- **User Banner**:
  - Signature Ginkgo/Heart orange avatar illustration.
  - Skewed silver `VIP` pill overlapping the avatar.
  - Thick bold identity "美叶" accompanied strictly by a small chevron `<`.
  - Gradient "福利中心" widget fixed prominently opposite the account name.
- **Premium Banner Sub-nav**:
  - Full-width deep purple (`from-[#4E5BFF] to-[#8032EC]`) active promotion banner offering VIP perks (`开通VIP，享高阶权益 >`).
- **Module Twin Nav**:
  - Dual action split-card wrapped tightly in a faint grey boundary stroke (`border-[#F2F3F5]`). 
  - Hosts `我的作品` (folder icon styling) and `我的智能体` (Bot dot styling), separated elegantly by a single vertical 1px divider trace.
- **History Log Core**:
  - Tab switcher locked vertically holding "最近对话" (Recent Chats, Active Bold underlined) and "最近智能体" (Recent Agents, Inactive Grey). Trailing action element triggers the blue "编辑" (edit) command.
  - Scrollable `line-clamp-2` white cards holding verbose interaction records separated into semantic topic + metadata components (agent tag, timestamp). 

## State Management
- Handled actively as a static preview component pinning the navigation array dynamically mapped inside an absolute wrapper context replicating a 'menu open' state perfectly.
