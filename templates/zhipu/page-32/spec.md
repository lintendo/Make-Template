# Zhipu AI Main App Hub (Default State)

## Overview
A high-fidelity replica mirroring `page-33`, which represents the absolute default application entry state ("首页"). It is the unified structure merging the Top Application Discovery Board (seen in `page-31`) and the Advanced Multi-Modal Input Terminal (seen in `page-30`), creating a dual-anchored layout centered by empty breathing space.

## Visual Design Details

### Spatial Geometry
- **Global Context**: The background remains a continuous flat off-white/grey (`bg-[#F4F5F8]`).
- **Layout Distribution**: Extremely top-and-bottom heavy. The Agent Discovery grid is absolute-positioned or flex-pinned to the top, while the input terminal is sticky-anchored to the bottom, leaving the exact middle of the screen entirely empty.

### Top Application Discovery Board
Identical mapping to `page-31`.
- **Top Navigation**: Hamburger menu block (left), Semantic Routing Tabs `首页` / `智能体` (centered).
- **Agent Matrix**: A large `bg-white` container housing the specialized CSS gradient hero banner ("AI智能体2025开发大师赛") and a 6-node grid representing specific active modalities (AI Video, Draw, Search, etc.).

### Advanced Multi-Modal Input Terminal
Heavily derived from `page-30`, with stateful visual modifications denoting "idle" vs "active" chat engagement.
- **Pre-Input Skill Tape**: A horizontally-wrapping scroll array just above the main deck. Hosts quick skill triggers like "写作" (Write), "拍照解读" (Photo analysis), constructed as bordered white capsule buttons (`bg-white border-[#E5E6EB] px-[12px] py-[6px]`).
- **Primary Text Deck**: 
  - Substantive rectangular field (`bg-white rounded-[24px] shadow-sm`).
  - **Placeholder Shift**: Text explicitly reads "输入你的问题..." (Enter your question...), shifting appropriately from the conversation-active placeholder used in deeper states.
  - **Semantic Action Row**: 
    - Left-bound attachment trigger (`+`).
    - Standard internal routing toggles (`推理`, `沉思` inactive, `联网` natively active using the `bg-[#EEF2FC] text-[#3B53FF]` brand color layout).
    - **Idle Dictation Shift**: The bottom-right dictation anchor is structurally inverted from the active-chat state. Instead of a solid black fill, it is rendered "hollow/idle" (`bg-transparent border border-[#333]`), utilizing a dark `#333` interior vector instead of white.

### Legal Anchor
- Standard system footer safety zone overlay text ("内容由AI生成...") bounding above the hardware safe-area mask.
