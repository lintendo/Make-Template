# Zhipu AI Header Logic Menu (Dropdown Popover)

## Overview
A high-fidelity replica mirroring the `page-26` Header Action Menu state. This interface demonstrates the standard context-menu logic triggered from the top-right `...` header icon, surfacing a floating popover array of system and agent-specific management actions over the undimmed active chat layout.

## Visual Design Details

### Context Retention (Non-Dimmed)
- Unlike the heavy modal sheet in `page-24`, this dropdown does **not** rely on a full-screen `bg-black/40` overlay. The active AI Search list remains fully bright and legible, with the popover simply relying on a heavy drop-shadow to separate itself along the z-axis.

### Popover Container Architecture
- **Anchoring**: Positioned absolutely near the top-right margin (`top-[96px] right-[16px]`), aligning underneath the trigger button.
- **Form Factor**: A highly vertical rectangle `w-[175px]` shaped natively with iOS-style heavy bounding radius (`rounded-[16px]`).
- **Surface**: Pure solid white `bg-[#FFFFFF]` rendered with an aggressive shadow diffusion (`shadow-[0_10px_40px_rgba(0,0,0,0.12)]`) creating organic depth over the chat text beneath it.

### Action Item Matrix
- A contiguous vertical flex structure rendering 6 distinct management nodes. 
- No explicit divider lines between objects, relying instead on clean, uniform vertical padding (`py-[14px]`).
- **Internal Row Composition**:
  - Left-bound monochrome SVG vector (`w-[20px] h-[20px]`, stroke `#111111`).
  - Right-bound structural label (`text-[15.5px] font-[450] text-[#111]`).
- **Payload Data**:
  1. **创建新对话** (Create New Chat): Chat bubble + plus.
  2. **历史记录** (History): Clock dial.
  3. **分享智能体** (Share Agent): Curved export arrow.
  4. **评分与反馈** (Rating and Feedback): Star encased in a ribbon.
  5. **添加到桌面** (Add to Desktop): Rounded square + plus.
  6. **固定在首页** (Pin to Home): Assorted grid format configuration.
