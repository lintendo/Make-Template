# Zhipu AI Eraser (Dark Mode Image Editor)

## Overview
A high-fidelity replica mirroring the `page-12` "AI消除" (AI Eraser) interface. This represents the application's native dark mode image editing and manipulation canvas, specifically displaying the empty state before a source image is uploaded.

## Visual Design Details

### Global Canvas
- **Background Layer**: The app operates in a pure black (`#000000`) immersive full-screen context denoting an editor mode.
- **Top Header**: Minimalist overlay featuring a solitary white structural 'Close' (`X`) action button aligned to the top-left safe area margins.

### Image Working Area
- Represents the visual boundaries of the user's canvas.
- **Surface Geometry**: Massive central block (`flex-1`) featuring significant `rounded-[24px]` corner softening to separate it from the device bezel.
- **Gradients**: Employs an ultra-deep slate violet gradient (`from-[#12162B]` to `#1A1B29`) serving as the darkroom backdrop.
- **Empty State Indicator**:
  - Center-mounted custom SVG icon depicting an image frame intertwined with a glowing `+` emblem. Colors map natively to the glowing Zhipu blue brand tone (`#7186F2`).
  - Directly beneath, the instruction "请先上传图片" (Please upload an image first) leverages the identically vibrant electric blue contrast text.

### Toolbar Architecture
The bottom console manages the editing lifecycle using a layered approach.
1. **Brush Parameters Row**:
   - Left toggler (`bg-[#1F1F1F]` pill): Two-state switch managing brush vs. selection modes, showing a light grey active state enclosing a squiggle icon.
   - Scale Slider: A horizontal scrubber bar (`bg-[#333]`) featuring an active progress fill and a high-contrast circular tracking knob (`border-[#999]`).
   - "重做" (Undo/Remake): Inactive grey clock arrow denoting non-destructive revision control.
2. **Global Action Row**:
   - Oversized pill CTA button holding the primary "开始消除" (Begin Eraser) action. Employs a deep jewel-toned purple/blue interactive gradient (`from-[#2135A1] to-[#4527A1]`), currently text-muted (`#7A8ADD`) reflecting its empty blocked state constraint.
3. **Primary Edit Modes**:
   - Navigation anchoring the layout baseline mapping exactly two modes: `AI消除` (Active, Solid White, Dot underlined) and `局部重绘` (Inactive, `#8A8A8A`).
   - The active mode carries a unique golden payload badge "10次" (`bg-[#FFDE81]`) indicating usage quotas remaining to the user.

## Component Handling
- Designed entirely as a stateless visual component. Built using deeply nested specific Tailwind CSS mappings avoiding any extraneous graphic dependency mapping.
