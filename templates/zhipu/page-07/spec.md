# Zhipu Configure Agent - Editor Page

## Overview
A standalone high-fidelity implementation of the fully actionable "配置智能体" (Configure Agent) scrollable form view. Unlike the modal variation, this screen displays the active editing state with a light-grey background bounding bright white form elements and a comprehensive system prompt text editor.

## Visual Design Details

### Theme & Colors
- **Main Background**: A cool light grey (`#EFEFF5` or similar), enabling individual form modules to float prominently.
- **Form Containers**: Pure white (`#FFFFFF`) with generous border radii (`[14px]` to `[16px]`).
- **Accent Red**: Asterisks indicating required fields are `#EE4D38`.
- **Primary Blue**: Badges, CTA buttons, and generated stars (`✨`) utilize the signature Zhipu blue (`#3B4CF3`).

### Core Page Structure
- **Global Layout**: A fully vertically scrollable view padded with safe area spacing.
- **Navigation Bar**: 
  - Left: A circular white button enclosing a black `X`.
  - Center: Main Title "配置智能体".
  - Right: "✨ AI生成" action indicating generative capabilities.
- **Avatar Profile**: High-contrast constructed CSS vector illustration of the 'Weather Stylist', overlaid with an active edit pencil badge (`absolute`).
- **Data Inputs**: 
  - "名称" (Name) input displaying "天气搭配师" in a white rounded container.
  - "简介" (Intro) text field displaying the catchy positive daily text.
- **Prompt Editor Area ("配置信息")**:
  - Starts with descriptive hinting and "示例" (Example) tags formatted as white capsules (`角色 >`, `游戏 >`).
  - Followed by a massive white card expanding downwards simulating a code/markdown `textarea`, filled with explicit agent role-play prompt text (`# 角色`, `# 工作任务`, etc.).

### Floating Navigation
- **Publish Button**: A floating, centrally aligned pill button (`发布智能体`) fixed at the bottom edge using an absolute wrapper. It features a bright `#3B4CF3` background and deep drop shadow mapping depth against the scrolling text behind it.

## State Management
- Handled purely as a presentational scrolling layout matching the visual data exactly as depicted in the original screenshot.
