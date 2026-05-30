# Zhipu AI Entry Hub & App Modality Drawer

## Overview
A high-fidelity replica mirroring `page-31`, representing the core application default state ("首页" - Home). The layout features the primary agent routing grid and an active, non-dimming bottom drawer expanding the specific "写作" (Writing) multimodal input configuration.

## Visual Design Details

### Root App Hub (Background Layer)
- **Global Background**: A flat, bright surface (`bg-[#F4F5F8]`). Notably, the bottom drawer does **not** trigger a black dimensional overlay (`bg-black/x`) here; the hub remains fully illuminated.
- **Top Navigation**: 
  - Left-installed hamburger menu sequence.
  - Centered semantic tabs: `首页` (Active, heavy font, bottom strict-black text underline locator) and `智能体` (Agents, inactive, neutral grey).
- **Core Agent Routing Card**:
  - `bg-white` container bounded aggressively with large `rounded-[24px]` radius corners.
  - **Hero Banner**: A rich blue technology gradient header (`AI智能体2025...`) filling the top block (`h-[80px]`).
  - **App Grid**: A dense, fluid `grid` matrix of 6 primary agent nodes (清影AI视频, AI画图, AI搜索, etc.), mapped structurally using uniform 44px circular vector assets combined with tight descriptive subtext (`text-[12px]`).

### Specialized Input Drawer ("写作" - Writing)
- Acts as a heavy structural bottom sheet (`bg-white rounded-t-[20px]`) permanently anchored to the bottom.
- **Drawer Header**: Left aligned title ("写作" next to a slanted pen icon) counter-weighted by a subtle grey circular close action (`bg-[#F2F3F5] rounded-full`).
- **Configuration Sections**:
  - Structured via muted header tags (`类型` and `要求` mapped to `text-[#8A8F99] font-[550] text-[13px]`).
  - **Type Form (类型)**: A wrapping flex-array of pill buttons mapping specific text formats ("祝福语", "标题", "作文" etc.), built using clean white capsules (`border-[#E9EAED]`).
  - **Requirements Form (要求)**: Secondary row of specialized dropdown chips ("风格 v", "长度 v").
- **Integrated Terminal**:
  - Lower boundary behaves like the standard chat input.
  - Hosts placeholder instructional text ("请输入你想写作的内容...").
  - Matches the standard semantic routing toggles (`推理`, `沉思`, `联网` active) mapped cleanly over the home safety zone.
