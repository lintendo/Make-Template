# Zhipu AI Image Drawing Dashboard

## Overview
A high-fidelity replica mirroring the `page-17` AI Drawing Dashboard interface. This layout acts as the system's exploratory home state before prompts are generated, presenting users with structured modules of featured generative tools and a masonry-like grid of community stylistic inspirations.

## Visual Design Details

### Header Anatomy
- Matches the standard conversation header (`bg-white`) establishing the "AI画图" global identity.
- Contains identical top-level auxiliary actions (History, Mute, Meatballs).

### Section 1: 精选工具 (Featured Tools)
- **Title Block**: Characterized by a blue functional icon (`bg-[#34ADFF]`) wrapping an edit/wand graphic intersecting the bold header text.
- **Horizontal Gallery**:
  - Implements a fluid `overflow-x-auto` container snapping modular tool cards laterally.
  - **Card Structure**:
    - **Arch Graphic**: 84px wide block dominated by a distinct rounded-arch shape (`rounded-t-full`). Internal graphics (beach dogs, tarot cards, ramen, dolls) are simulated using rich gradient block layers to denote stylistic themes. Several assets are allowed to bleed/overlap outside the arch boundaries simulating depth.
    - **Pill Label**: Deep thematic context mapping tightly underneath the arch. Implements custom dynamic background colors linking directly to the visual identity of the arch graphic above it (e.g., `#FF9A56` for Beach, `#7B8B9B` for Tarot). Typography is uniformly bold white.

### Section 2: 一键生同款 (One-Click Inspired Generation)
- **Title Block**: Characterized by a deep purple celestial icon (`bg-gradient-to-r from-[#4A24BB] to-[#A45DFF]`) enclosing a generation spark.
- **Inspiration Grid**:
  - 2-Column layout parsing extensive generative photo examples (fireworks, scenic portraits).
  - Designed as structural containers featuring a dominant photo display block `aspect-[3/4]` bounded by a crisp `#F7F8FC` card base wrapper containing rounded geometries (`rounded-[16px]`).
  - **Interaction Footers**: Every card houses a bottom anchored action dock featuring right-aligned `bg-[#EEEEEE]` conversion pills labeled "✦ 画同款" (Generate Similar).

### System Floating Elements & Footers
- **Floating Anchor**: Simple white scroll-down arrow overlapping the mid-point of the interaction grid cleanly mapped with a robust drop-shadow `z-10`.
- **Sticky Terminal Module**: Functionally identical prompt-terminal mirroring `page-14`, retaining independent Quick-Action carousels ("AI特效", "AI编辑", "比例1:1") mapped neutrally across a continuous horizontal stream. Bounded above a thick soft-shadow white input container.
