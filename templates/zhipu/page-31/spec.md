# Zhipu AI Left Navigation Drawer State

## Overview
A high-fidelity replica mirroring `page-32`, which illustrates the global side navigation drawer triggered from the hamburger menu. The state heavily relies on spatial separation, pinning an unauthenticated persona context alongside quick-access route hubs over an empty conversation history layout, while pushing the main application background into a dimmed, inactive state.

## Visual Design Details

### Spatial Architecture
- **Dimensional Lockout**: The primary viewport is suppressed using a heavy structural dim (`bg-black/40`), exposing only a sliver of the underlying interface on the far right.
- **Drawer Geometry**: The active surface maps to a left-anchored absolute panel spanning ~85% viewport width (`w-[310px] bg-white h-full`).

### Header Authentication Hub
- **Avatar Assembly**: Renders a placeholder silhouette. Mapped using a light brand-tinted circle (`bg-[#F0F4FF]`) wrapping a bold, generic user stroke vector (`stroke-[#3B53FF]`).
- **Call-to-Action**: "点击登录 >" (Tap to Login) using heavy structural typography (`font-bold text-[18px]`).
- **Marketing Badge**: Absolute positioned beside the login action. "福利中心" (Welfare Center) utilizing a vibrant, warm gradient (`bg-gradient-to-r from-[#FFE5C9] to-[#FFD5BA] text-[#D25114]`) contrasting against the cool brand colors.

### Core Routing Deck
- Situated directly below the auth lockup as a unified dual-action card. 
- **Card Styling**: Full-width container mapped with a soft blue backdrop (`bg-[#F8F9FE] rounded-[16px]`).
- **Data Nodes**:
   1. **我的作品 (My Works)**: Mapped to a blue folder/star vector.
   2. **我的智能体 (My Agents)**: Mapped to the inverse Zhipu Ring icon.
- Features a subtle central vertical divider element.

### History Filtering Sub-Navigation
- **Tab Structure**: Standard Zhipu tab array mapping.
  - Active: "最近对话" (Recent Chats). Uses `#111` heavy type and the signature black bounding underline.
  - Inactive: "最近智能体" (Recent Agents). Standard `#7A808C` mute mapping.

### Empty State Canvas
- Dominates the lower 60% of the drawer layout.
- **Vector Composition**: 
  - Background Node: Pale grey (`bg-[#F2F3F5]`) dialogue bubble pointing left.
  - Foreground Node: Muted blue (`bg-[#A2B3D4]`) dialogue bubble pointing right, overlaying the background shape.
- **Microcopy**: Instructional routing string ("快去开启新对话吧～") safely spaced below the graphic loop.
