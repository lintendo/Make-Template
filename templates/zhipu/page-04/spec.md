# Zhipu Creator Community - Post Action Modal

## Overview
A high-fidelity replication of the Zhipu "Creator Community" (创作者社区) view in a modal-active state. The background features a specific agent profile ("天气搭配师" - Weather Stylist) in an empty community state. Overlaid on top is an active bottom sheet menu providing post creation options ("图文帖子" and "对话分享帖子") and a cancel button.

## Visual Design Details

### Layout & Background
- **Root Background**: Off-white/slate gradient. The background page contains an agent profile header, description texts, and an empty state illustration (grey monochrome version of the Zhipu mascot).
- **Dim Overlay**: A `bg-black/60` overlay covers the entire screen, dimming the background content to focus attention on the modal.
- **Bottom Sheet**: A white drawer sliding up from the bottom with generous `rounded-t-[20px]` corners.

### Typography
- **Titles**: Agent name ("天气搭配师") and Community title are bold and prominent (`~18-20px`).
- **Dimmed Text**: Background subtitles and descriptions are greyed out by the overlay.
- **Modal Items**: 
  - Main titles: `16px`, semi-bold, `#222222`.
  - Subtitles: `13px`, regular, `#999999`.
- **Cancel Button**: `16px`, semi-bold, `#222222`.

### Colors
- **Action Icons bg**: Soft light-grey (`#F5F6F8`).
- **Cancel Button bg**: Light-grey (`#F5F6F8`).
- **Icons stroke**: Dark-grey/black.
- **Primary Page Button**: Dark blue (`#24357B`) (visible through dim overlay).

### Components Structure
- `CreatorCommunityModal`: Main wrapper managing the fixed screen space.
- `BackgroundPage`:
  - `Header`: Back chevron.
  - `ProfileBlock`: Avatar and text details.
  - `EmptyState`: Central grey mascot illustration and prompt text.
  - `ActionBtn`: The dark blue "立即发帖" button.
- `DimOverlay`: The dark mask.
- `BottomSheet`: 
  - `PostOption`: Reusable component for the two post actions. Contains a circular icon container and text block.
  - `CancelButton`: Bottom action to dismiss the sheet.

## State Management
- Replicated as a static visual 1:1 match of the provided screenshot, capturing the modal in its open state.
