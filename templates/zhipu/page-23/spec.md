# Zhipu AI Global Share Bottom Sheet

## Overview
A high-fidelity replica mirroring the `page-24` Global Share Modal state. This interface suspends the active AI Search stream behind a darkened overlay and surfaces a standardized iOS-style bottom sheet for social routing and system clipboard utilities.

## Visual Design Details

### Context Suspension (Dark Mode Overlay)
- The entire application instance (`AI搜索` layout) is shifted into an inactive visual state.
- **Mask Logic**: A full-height `fixed` or absolute overlay spanning the viewport, structured as `bg-[rgba(0,0,0,0.4)]` (`bg-black/40`) to dim underlying generative responses while maintaining spatial awareness.

### Bottom Sheet Architecture (`分享至`)
- **Container Geometry**: Anchored strictly to the bottom viewport edge. Utilizes heavy top-rounding (`rounded-t-[24px]`) and a pure white background (`bg-[#FFFFFF]`) to pop aggressively against the darkened background.
- **Header Structure**:
  - Title: Bold, left-aligned standard "分享至" (Share to) text (`text-[17px] font-[600]`).
  - Action: Right-aligned crisp exit node (`X`), cleanly ending the modal state without cluttering.

### Social Routing Matrix (Row 1)
- Highly colorful, prominent circular launch targets (`w-[60px] h-[60px]`).
- Maps exact brand color backgrounds housing white SVG vectors:
  - **微信好友** (WeChat): Classic green `#07C160`.
  - **微博** (Weibo): Vibrant red/orange `#FF5733`.
  - **朋友圈** (Moments): Distinctive cyan/teal `#31C27C`.
  - **更多** (More System Options): Neutral `#F2F3F5` with bold black ellipsis `...`.

### Utility Routing Matrix (Row 2)
- Secondary functionality focusing on flat file and link creation rather than instant network export.
- Standardized to neutral grey circles (`bg-[#F2F3F5] text-[#111111]`).
  - **生成名片** (Generate Namecard): Invokes image rendering workflows.
  - **复制链接** (Copy Link): Direct clipboard write.

### Layout Flow
- The matrices are padded properly from the sides (`px-[24px]`) preventing edge-collision, and utilize `gap-x` and `gap-y` effectively establishing a rigid grid logic for immediate scanning.
