# Zhipu AI Custom Agent Welcome Interface

## Overview
A high-fidelity replica mirroring the `page-21` Custom Agent welcome/empty state. Directly preceding the chat state mapped in `page-20`, this interface establishes the agent's persona and introduces users to its capabilities through rich transparent text overlays and interactive predictive prompt routing over the custom generative wallpaper background.

## Visual Design Details

### Persistent Immersive Layout
- Reuses the full-screen anime proxy background via identical heavy `bg-gradient-to-br` and deep radial lighting filters established for the Custom Agent profile mapping.
- Header and Footer terminal geometries remain completely persistent, ensuring a seamless aesthetic transition when the user initiates a prompt to switch states.

### Core Welcome Messaging
- **Persona Introduction Document**: 
  - Rendered plainly natively over the darkened backdrop instead of constrained inside a chat bubble.
  - Large, highly legible stark white typography (`text-[16px] leading-[1.6]`) documenting the functional intent of the agent ("这是一款专注于现代极简风格..."). Accompanied by aggressive drop-shadow logic (`drop-shadow-md`) to separate the text visually from busy wallpaper zones.

### Interactive Demonstration Array
- **Call-to-Action Label**: Positioned beneath the intro. Maps a delicate semi-transparent hollow star asset (`stroke="rgba(255,255,255,0.7)"`) alongside muted instruction text ("不知道如何开始? ...") to drive engagement.
- **Predictive Routing Matrix**:
  - Displays exactly 4 example prompts the user can execute with a single tap.
  - **Component Structure**: Unlike the flush-left pills in `page-20`, these operate as deep block-level containers stretching across the active canvas `w-[calc(100%-32px)]`.
  - **Design Mechanics**: Glass-morphism (`backdrop-blur-xl bg-[rgba(60,60,60,0.45)]`) featuring highly rounded borders (`rounded-[20px]`). 
  - **Internal Layout**: A basic flex mapping the suggestion syntax on the left, and a native structural outward navigational arrow (`↗`) anchored securely on the right edge.
