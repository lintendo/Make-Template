# Zhipu AI Generation Interruption State

## Overview
A high-fidelity replica mirroring the `page-28` "Generation in Progress" state. This layout surfaces the active generative stream view while introducing a localized, floating interruption control ("停止生成") allowing users to halt the active text/data synthesis mid-stream. 

## Visual Design Details

### Persistent Background Elements
- The layout relies entirely on the standard `AI搜索` workspace structure.
- **Top Header**: Standard custom radial Agent avatar and action anchors (`...` and clock) remain fully active and undimmed.
- **Generative Card**: The large Synthesis Response box (`bg-white rounded-[22px]`) continues to render the rich-text stream output.
- **Input Terminal**: The standard capsule-shaped terminal sits at the bottom edge containing the `+` attachment routing trigger and voice dictation nodes.

### "停止生成" Floating Interruption Node (Stop Generation)
- **Anchoring Strategy**: Horizontally centered within the viewport. Vertically pinned slightly above the Input Terminal Safe Zone (approx `bottom-[110px]`) allowing it to float dynamically above the generative text stream preventing overlap with static layout boundaries.
- **Node Geometry**: 
  - Standard white pill structure (`bg-[#FFFFFF] rounded-full h-[36px]`).
  - Utilizes a soft perimeter (`border border-[#EFEFEF]`) mixed with a highly subtle shadow diffusion (`shadow-[0_4px_16px_rgba(0,0,0,0.06)]`) to establish physical separation from the text behind it.
- **Graphical Content**:
  - Contains a specialized monochrome stop vector (a solid square `rect` centered inside an outline `circle`).
  - Left-aligned beside standard descriptive typography (`text-[13.5px] font-[450] text-[#111]`).
