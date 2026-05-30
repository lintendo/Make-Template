# Zhipu AI Custom Agent Interface

## Overview
A high-fidelity replica mirroring the `page-20` Custom Agent conversational interface. Unlike the standard chat mode, this screen operates entirely via a transparent aesthetic overlaying a full-screen graphic wallpaper background, granting the custom persona ("炫酷logo设计大师") maximum visual branding control over the user experience.

## Visual Design Details

### Transparent Viewport & Background Proxy
- **Global Canvas**: Abandons solid color backgrounds for a rich, full-screen background image placeholder setup. Simulated natively using heavy layered gradients (`bg-gradient-to-br`) mixing dark greys and deep purples (`from-[#161921] to-[#0A0B0E]`) combined with radial lighting layers mimicking the underlying anime-character setup seen in the reference material.

### Navigation Header
- **Context Lock**: Drops the standard solid white header for an aggressive linear gradient fade stretching from pure black mapped at the top edge (`bg-gradient-to-b from-[rgba(0,0,0,0.85)] to-transparent`) ensuring the white text layers remain hyper-readable over any underlying artwork.
- **Agent Profile**: Custom detailed header identity block mapping the agent avatar alongside dual-line hierarchy (Agent Name `+` Creator String "来自: 波浪的魔术师"). 

### Conversation Bubble Mechanics
- **Glass-morphic Rendering**: All chat artifacts leverage heavy `backdrop-blur` and translucent `rgba` background handling.
- **User Prompt (Right)**: Anchored top-right utilizing a deep slate-blue translucent background (`bg-[rgba(40,48,70,0.85)]`). 
- **AI Response (Left)**: Anchored top-left utilizing a neutral dark-grey glass block (`bg-[rgba(30,30,30,0.7)]`). Includes a robust footprint containing a native audio-playback toggle icon alongside the standard 4-icon action rating array (Thumb-up, Thumb-down, Copy, Share).
- **Suggestion Pill Array**: 
  - Dynamic generation of 3 predictive prompt nodes stacked beneath the AI reply. 
  - Rendered flush-left matching the exact border-radius footprint of the AI bubble mapping an organic continuation of the system's thought process (`rounded-[18px] rounded-tl-[4px] bg-[rgba(60,60,60,0.6)]`).

### Dynamic Transparent Input Deck
- **Appreciation Node (`点赞`)**: A free-floating pill module hovering above the main input block allowing users to upvote the specific Custom Agent experience (`border-[0.5px] border-white/20`).
- **Terminal Container**: Replaces the standard white shadow box with an aggressive, floating translucent black pill `bg-[rgba(15,15,15,0.85)] border border-[rgba(255,255,255,0.15)]`.
- **Iconography**: Clean, high-contrast white vector strokes bounded natively by thin white structural rings representing attachment (`+`) and audio-dictation triggers.
