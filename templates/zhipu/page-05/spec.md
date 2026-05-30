# Zhipu Creator Community - Empty State Profile

## Overview
A high-fidelity standalone implementation of the "天气搭配师" (Weather Stylist) creator community profile page. It represents the fully visible (undimmed) empty state of the community board, featuring a central call-to-action to post. It also highlights a floating action button (FAB) at the bottom right, enriched with a vivid tooltip bubble encouraging the user to choose a posting mode.

## Visual Design Details

### Layout & Background
- **Root Background**: Appears primarily as a very light off-white/grey (`#F7F8FA`) but the top header contains subtle ambient glows of pink, blue, and purple imitating an airy gradient block behind the avatar and title.
- **Top Bar**: Standard `<` chevron navigation beneath an iOS status bar.
- **Profile Block**: Avatar showcasing styling elements, large bold title (`天气搭配师`), secondary info (`来自: 美叶 智能体热度: 0`), and community descriptions.
- **Empty State**: Centralized grey scale cube mascot accompanied by minimalist floating asterisks/dots, along with the text `快来抢占“沙发帖”吧` and a vivid blue `立即发帖` button.

### Floating Bottom UI
- **FAB (Floating Action Button)**: Positioned at the bottom right, rounded circular button painted in bright electric blue (`#3A45F6`) with a white sparkle-pen icon.
- **Tooltip Bubble**: Placed immediately to the left of the FAB, pointing to it:
  - Background: Bright blue gradient.
  - Text: Highlighted `两种发帖模式` (Two posting modes) in cyan (`#3FEDD9`), followed by `任你选，快来发布你的首帖吧！` in white.
  - Decor: A small floating 3D-styled magical pencil overlapping the bottom-right corner of the bubble.

### Components Structure
- `CreatorCommunityPage`: Main wrapper.
  - `Header`: Standard navigation area.
  - `AvatarSection`: The user profile information.
  - `EmptyState`: Central content prompting users to create the first post.
  - `FloatingActionBanner`: The FAB and animated Tooltip bubble overlay at the bottom.

## State Management
- Handled as a purely presentational layout.
