# Zhipu AI Official Agents Discovery List

## Overview
A high-fidelity replica mirroring the `page-18` "官方推荐" (Official Recommendations) interface. This view acts as a centralized directory to discover, search, and add various specialized AI agents (e.g., Translation Experts, Subject Tutors, Copywriters) to the user's primary interface.

## Visual Design Details

### Fixed Header Region
- **System Padding**: Sustains standard iOS status bar clearance mapping the top layer.
- **Search Component**: 
  - Central input bounds shaped by a soft grey pill (`bg-[#F4F5F7] rounded-[18px]`).
  - Native grey magnifying glass SVG anchored left inline with the placeholder "搜索智能体".
- **Dismiss Action**: Right-aligned active text "取消" utilizing the brand's primary interaction blue (`text-[#3B4CF3]`).

### Discovery Roster (Main Feed)
- **Section Declaration**: Isolated "官方推荐" text anchored top-left floating with significant padding, presented in secondary muted grey (`#8B919D`) to contrast against the dense row information below.
- **Agent Row Anatomy**:
  - Arranged as a vertically scrolling list utilizing large baseline gaps (`space-y-[26px]`) avoiding cramped data presentation.
  - **Left Avatar Block `w-[48px] h-[48px]`**: Custom stylized circles leveraging specific color gradients and typography (e.g. bold burgundy for Translation, deep space gradients for Drawing).
  - **Central Metadata Stack**:
    - Title Line: Heavy primary title paired alongside an official system badge (`bg-[#EEF1FF] text-[#3B4CF3] text-[9.5px]`).
    - Description: Muted grey text heavily compressed (`text-[13.5px]`) wrapping cleanly up to 2 lines mapping the agent's behavior.
    - Social Proof Footer: Small meta text mapped with a speech bubble icon containing interaction stats (e.g., "37.4w人聊过") and the author handle (e.g., "@智谱清言") in `#A6ABB5`.
  - **Right Action Node**:
    - **Inactive/Add State**: Solid blue circle (`w-[24px] h-[24px] bg-[#3B4CF3]`) containing a crisp white `+`.
    - **Active/Added State**: Muted grey circle (`bg-[#F4F5F7]`) holding a grey checkmark indicating the item is already installed into the user's workspace (e.g., AI Draw Agent).

## Component Handling
- The entire page utilizes a flex column architecture bound functionally to the viewport height `min-h-screen`, leaving the raw vertical scrolling behavior to native device standards (`overflow-y-auto`). Fully standalone from deeper complex templates.
