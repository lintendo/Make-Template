# Zhipu AI Scheduled Task Configuration Modal

## Overview
A high-fidelity replica mirroring the `page-27` Scheduled Task Configuration state ("设置定时任务"). This represents a complex data-entry bottom sheet layered over the dimmed AI Search background. It provides robust form controls for date/time routing, frequency, categorized prompt selection, and external email syncing.

## Visual Design Details

### Modal Architecture (`设置定时任务`)
- **Masking Component**: Relies on the standard `bg-black/40` overlay to heavily dim the parent background context.
- **Root Geometry**: A massive bottom sheet (`rounded-t-[20px] bg-[#FFFFFF]`) originating from the bottom of the viewport and stretching approximately 85% up the screen height. 
- **Sticky Header**: 
  - Bold title (`text-[18px] font-bold`) and a prominent gray descriptive subtext explicitly explaining the automation behavior.
  - Right-bound `X` vector icon for closure.

### Form Control Blocks

**1. 首次执行时间 (First Execution Target)**
- Dual-input layout. 
- Primary Date Selector: "2025-07-22" mapped to a large pill selector `border border-[#E5E6EB] rounded-[10px]` occupying ~65% width. Custom `v` chevron right-aligned.
- Secondary Time Selector: "上午8:00" occupying the remaining width.

**2. 重复频次 (Frequency Matrix)**
- Full-width pill selector mapped identically to the Date Selector border style.
- Active value: "每天重复" (Repeat daily).

**3. 订阅内容 (Subscription Rules & Prompts)**
- Mandatory parameter marked with a Red Asterisk `*`.
- **Category Filter Tabs**: 
  - Horizontal scrolling row (`flex space-x-[8px] overflow-x-auto`).
  - Active Tab: "新闻日报" (Daily News) uses brand primary colors (`border-[#0D78FF] text-[#0D78FF]`).
  - Inactive Tabs: "每日运势", "学术日报", "今日天气" using neutral grey borders (`border-[#E5E6EB] text-[#4E5969]`).
- **Input Deck**:
  - A nested grey container (`bg-[#F7F8FA] rounded-[12px] p-[12px]`) acting as a multi-line input holding field.
  - Embedded Context Chips: Short prompt suggestions ("大模型行业", "科技领域") nested horizontally at the bottom of the input deck mapped as white pill-buttons.

**4. 同步发送至邮箱 (External Email Syncing)**
- **Header Control**: Label mapped against an iOS-style Toggle Switch. Currently in an inactive state (`未开启` alongside a grey toggle).
- **Disabled Input**: Email collection text field styled with visual depreciation (`opacity-50`) to reinforce the inactive toggle state.
- **Helper Description**: Muted footer text highlighting the limit logic (`可配置1个邮箱...` where `1个` is specifically highlighted in red).

### Footer Confirmation Action
- Standard sticky primary action button (`bg-[#0D78FF] text-white rounded-full w-full py-[14px]`). Pinned above the home indicator.
