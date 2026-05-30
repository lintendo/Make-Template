# Zhipu Configure Agent - Set Permissions Modal

## Overview
A high-fidelity standalone implementation of the "配置智能体" (Configure Agent) background, overlaid with the active "设置权限" (Set Permissions) bottom sheet modal. This screen manages the visibility and privacy settings before publishing an agent.

## Visual Design Details

### Background Layer (Configure Agent Form)
- **Root**: `#F7F8FA` or white base, overlaid with a heavy `bg-black/45` dim masking.
- **Top Navigation**: Replaces standard chevron with an `x` cancel button icon. Center title `配置智能体`, right action `AI生成` in blue with sparkles.
- **Avatar Setup**: A large circular avatar profile demonstrating the character design with a bottom-right attached edit badge (blue circle, pencil).
- **Form Controls**: 
  - Standardized label structures: `Title` + `<span class="text-red-500">*</span>`.
  - Input fields: Round-cornered rectangles (`#F4F5F7`), containing bold 15px text input values ("天气搭配师", etc.).
  - Hint text block: Greyed out instructional texts under "配置信息".
  - Small Example Chips: Pill-shaped suggestion buttons (`角色 >`, `游戏 >`, etc.).

### Bottom Sheet Modal (Set Permissions)
- **Container**: White modal snapping to the bottom with large top rounded corners (`rounded-t-[20px]`).
- **Header**: Left aligned bold title `设置权限` with a top-right `x` close button.
- **List Items**: 
  - Three distinct privacy options separated by 1px grey divider lines.
  - Each item contains a left graphic container (`bg-gray-100` circle with dark icon), central bold text title, and a right aligned custom radio selector.
  - The currently selected state (`公开 · 提交到智能体中心`) highlights the radio button with a thick bright-blue border (`#3B4CF3`).
- **Bottom Action**: A dominant full-width blue button `确认发布` securely locked above the home indicator space.

### Components Structure
- `SetPermissionsModalPage`: Main wrapper.
  - `DimmedBackgroundForm`: Contains the fully reconstructed Agent builder background.
    - `NavBar`: Cancel, Title, AI Generate.
    - `AvatarConfig`: Avatar UI with edit pencil badge.
    - `FieldSets`: Name, Intro, Config info with hint chips.
  - `PermissionsDrawer`: The active modal sheet.
    - `PermissionRow`: Reusable component for the settings radio list.
    - `ConfirmBtn`: The publish trigger button.

## State Management
- Handled purely as a presentational overlay matching the exact 1:1 state depicted in the screenshot.
