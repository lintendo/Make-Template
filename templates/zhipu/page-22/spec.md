# Zhipu AI Search Context and Toolkit Menu

## Overview
A high-fidelity replica mirroring the `page-23` AI Search module (`AI搜索`). This view demonstrates two core functional states: the complex generative "AI Reading/Citation" card layout representing multi-document web synthesis, and the active expanded "Input Toolkit Menu" sliding up from the bottom to offer file/media attachment workflows.

## Visual Design Details

### AI Search Header
- Custom Agent Nav mapping: Dedicated `AI搜索` target with its own distinct radial avatar (`bg-[#0D78FF]` dominant) encompassing a vector magnifying class geometry. Retains the standard transparent white iOS sticky header `bg-white` layout.

### Conversation Stream (Generative Search Layout)
- **User Prompt (Right)**: Handled via soft lavender-blue geometric blocks (`bg-[#E7EEFC] text-[#1D2129]`).
- **AI Synthesis Card (Left)**:
  - Discards the standard grey background chat bubble for a massive structured geometric container (`bg-white rounded-[16px] max-w-[95%] p-[16px] shadow-[0_2px_12px_rgba(0,0,0,0.03)]`).
  - **Meta Header**: "智能阅读85个网页" (Read 85 web pages) bounded by a checkmark loop to represent verification. Arrow collapse chevron `v` right-aligned.
  - **Citation Carousel**: 
    - A horizontally scrollable tape (`flex space-x-[8px] overflow-x-auto`) rendering specific source cards.
    - Each source card (`bg-[#F9F9FA] rounded-[8px] p-[10px] w-[140px]`) holds a heavily truncated headline (`text-[13.5px] line-clamp-2`) and a footer identifying the source agency (e.g., 腾讯网) alongside dynamic generation sparkles.
  - **Synthesis Body**: Returns to structural rich-text rendering the primary search return summary, supporting divider strokes (`border-t border-[#F2F2F2]`) and explicit list hierarchical numbering formats (e.g. "一、月最低工资").

### Deep Action Toolkit (Expanded Deck)
- **Anchoring Input Bar**:
  - Pushed upwards gracefully to accommodate the toolkit drawer.
  - Large white capsule (`bg-[#FCFDFE] shadow-sm border border-[#EFEFEF]`).
  - Retains the explicit left-bound associative trigger (`+` inside a structural ring) and native voice dictation vectors.
- **Toolkit Matrix**:
  - The floor area transitions into a grid mapping of upload parameters.
  - **Node Geometry**: `w-[64px] h-[64px] bg-white rounded-[16px] shadow-[0_4px_16px_rgba(0,0,0,0.05)] flex justify-center items-center` paired cleanly above standard mapped text labels (`text-[12px] text-[#8A8F99]`).
  - **Grid Payload**:
    - 相机 (Camera)
    - 照片 (Photos)
    - 本地文件 (Local Files)
    - 微信文件 (WeChat Files)
    - 面板 Row 2: 云知识库 (Cloud Knowledge Base).
