# Zhipu Configure Agent - Auto Generate Modal

## Overview
A high-fidelity standalone implementation representing the "AI自动生成配置" (AI Auto-Generate Config) modal view. It overlays the basic agent editor backdrop with a large interactive sheet, offering users a quick AI-assisted generation form.

## Visual Design Details

### Background Layer
- Top-level UI retains the main navigational `<X>` header, "配置智能体" title, and right-aligned "AI生成" generator button.
- The underlying application view is heavily masked by an ambient `bg-black/40` overlay covering the entire scrolling area beneath the status bar.

### Auto Generate Modal (Bottom Sheet)
- **Dominant Component**: A massive, rounded white drawer (`rounded-t-[20px]`) occupying ~88% of the vertical viewport.
- **Header Structure**:
  - Left-aligned title featuring the Zhipu AI sparkle icon alongside "AI自动生成配置" enclosed in bright blue text (`#3B4DF5`).
  - An accented underline bar sitting exactly beneath the title text simulating a focused active tab or branding element.
  - A subtle right-aligned "X" close dismissal button.
- **Form Layout**:
  - Subheading "一句话描述你的智能体" prominently introducing the input requirement.
  - **Example Container**: A light grey secondary block (`bg-[#F7F8FA]`) providing a soft contextual cue utilizing a lightbulb icon and placeholder roleplay description.
  - **Input Box**: A distinctly bounded rectangular area mimicking a large `textarea` bordered with soft grey outlines, containing ghosted placeholder instruction text (`text-[#999FA9]`).
- **Footer Interaction**:
  - A fixed submit container clamped to the bottom inside the drawer.
  - Contains a muted, inactive primary button state labeled "生成配置" (`bg-[#ACB5C6]`) communicating that input is required to proceed.

## State Management
- Displayed purely as a structural and presentational layout representing the empty/inactive placeholder state of the generator prompt.
