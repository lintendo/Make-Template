# Zhipu AI Image Editor & Viewer

## Overview
A high-fidelity replica mirroring the `page-15` Image Editing / Preview interface. This dark-mode layout facilitates post-generation interactions allowing users to modify dynamic textual layouts, switch aesthetic templates, and export their generated AI photography.

## Visual Design Details

### Header Overlay
- **Context Lock**: Operates strictly in a pure black (`#000000`) dark mode canvas maximizing visual focus on the photography.
- **Top Bar**: Minimalist arrangement featuring a simple `X` Close boundary on the top-left safe area.
- **Action Node Anchors**: Two pronounced pill actions sit flush right:
  - "分享" (Share): A ghost pill leveraging `bg-[#333333]` with white native system-style curvy-arrow iconography.
  - "保存" (Save): The primary conversion CTA mapped using a vibrant continuous electric blue gradient (`bg-[#4939FF]`) to emphasize export actions.

### Main Viewport Canvas
- Constrains the primary generated output using an aspect ratio `[3/4]` card.
- Incorporates significant corner smoothing (`rounded-[12px]`) floating natively off the bezel bounds (`px-4`).
- **Interactive Modifiers overlaying the image**:
  - **Editable Selection Box**: Presents a dashed white bounding box mapping editable string "藏韵清风，笑映晴空". Includes 2 tactile hit-boxes appended to the external grid: A top-right `X` delete circle button and a bottom-right double-arrow bidirectional resize icon. All interactive controls use a `backdrop-blur` bounding wrapper over `bg-black/50`.
  - **Static AI Generated Texts**: Mockups of heavy custom typography "全力以赴 高考加油" generated as part of the image's thematic output layer.
  - **Watermark**: Anchors a subtle deep-blue shadow gradient baseline holding the logo vector and the branding script "清言 | 一起AI画图吧".

### Template Carousel
- Displayed uniformly beneath the canvas. 
- Implements 5 distinct style selectors mimicking various photo-frames or text-templates mapped over identical core AI output.
- **Active State Mapping**:
  - The focused template (Template 1) scales slightly applying an external structural `border-white`.
  - Confirmation is mapped directly beneath utilizing a solid electric-blue checkmark circle node (`bg-[#344DFB]`).
- **Inactive States**:
  - Lack borders. Unselected metrics are mapping an empty structural ring locator (`border-[#666]`).
