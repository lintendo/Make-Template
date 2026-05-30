# Zhipu AI View & Export Modal

## Overview
A high-fidelity replica mirroring the `page-16` Image Preview and Action interface. This functions as the core unfiltered lightbox viewer allowing users to examine raw AI generative outputs without obstruction, providing immediate pathways to advanced pipelines like Ultra HD exports, Poster generation, and contextual AI editing.

## Visual Design Details

### Immersive Workspace Matrix
- **Global Canvas**: Defaults to a fully blacked-out immersive state (`bg-black`) to provide massive visual contrast and focus exclusively on the artwork.
- **Top Header**: Stripped back and minimalist.
  - Left Safe Zone: Single white `X` exit path.
  - Right Safe Zone: Contextual free-floating white paths for "Share" (`➦`) and "Download" mapping native OS expectations. Zero background pills are utilized here compared to other screens.

### Viewport Image Display
- Completely abandons horizontal padding constraints (`px-0`), spanning the image edge-to-edge relative to the device chassis frame.
- Uses an identical proxy aesthetic (`bg-gradient-to-br from-[#53BBEA] to-[#EB5852]`) simulating the primary raw scene generated previously, maintaining cross-page graphical consistency. No watermarks or typographic overlays are mapped in this state.

### Bottom Action Row (The Pipeline)
- Positioned deep into the bottom layout margin. Symmetric horizontal layout with 3 core action stacks.
- **Node 1: 超清下载 (4K Download)**: 
  - Graphic displays a rounded rectangle framing '4K' text.
  - Incorporates an absolute pinned quota-badge over its top-right margin ("10次") utilizing a high-contrast `#FFDF80` gold fill locked against a heavy black border stroke `border-black` matching Zhipu's quota systems perfectly.
- **Node 2: 海报 (Poster)**: 
  - Standard square picture-frame landscape graphic. Serves as the navigation anchor back to `page-15`'s template editor.
- **Node 3: AI编辑 (AI Edit)**: 
  - Custom SVG mapping an open block geometry intersecting with a magic sparkle `*` asset top-right, carrying the text `Ai` internally.

## Component Handling
- Designed strictly as a minimal overlay block. The full-width image acts as the primary layout driver stretching the relative `flex-1` zone perfectly while retaining absolute Header and Footer action heights preventing clipping on smaller displays.
