# Zhipu Personal Center (个人中心)

## Overview
A high-fidelity standalone replication of the personal center ("个人中心") screen for the Zhipu application. This page features a soft user-profile card promoting VIP upgrade, followed by categorized lists of account settings, application settings, and legal/help documents, ending with a logout button.

## Visual Design Details

### Layout & Spacing
- **Container**: Standard responsive column layout, maintaining a minimum viewport height, with a light gray background (`#F5F6F8`).
- **Top Bar**: Standard iOS status bar with time (18:13), cellular, Wi-Fi, and battery.
- **Navigation Bar**: Clean top bar with a back chevron on the left and the bold title "个人中心" center-aligned.
- **Profile Card**: A blue gradient card containing the avatar, username ("美叶"), status ("非会员"), privileges descriptions, and an eye-catching call-to-action button to upgrade.
- **Settings Groups**: Items are grouped into three main white blocks with rounded corners (`rounded-2xl`). Each block contains individual rows with bottom borders separating them.
- **Logout Button**: A simple white card block at the bottom containing centered "退出登录" text.

### Colors
- **Page Background**: Light gray `bg-[#F5F5F5]`.
- **Primary Cards**: White `bg-white`.
- **Top Navigation text**: Black `#000000`.
- **Profile Card Background**: Gradient from soft purple-blue to light blue (`from-[#8E9BCE] to-[#A1B1DE]`).
- **Profile Card Text**: White and soft off-white.
- **VIP Upgrade Button**: Yellow-gold gradient (`from-[#FEEBA5] to-[#F8D271]`) with dark brown text (`#66460D`).
- **VIP Badge**: Silver/metallic gradient (`from-[#F2F4F7] to-[#C9CED6]`).
- **List Text**: Main title is dark `#222222`, secondary hints are gray `#999999`.

### Typography
- **Nav Title**: Sans-serif, bold, ~18px.
- **Card Name**: Bold, ~18px.
- **List Item**: Medium, ~15px.
- **Secondary Hint**: Regular, ~14px.
- **Upgrade Button**: Bold, ~13px.

## Components Structure
- `PersonalCenter`: Main container.
  - `StatusBar`: Static top indicators.
  - `NavBar`: Back button and title.
  - `ProfileCard`: Blue hero banner with avatar and VIP upgrade prompt.
  - `ListGroup`: Reusable container for grouped list rows.
  - `ListItem`: Reusable row component taking a title, optional trailing text, optional trailing toggle, and default right chevron.
  - `LogoutButton`: Final action button block.
  - `HomeIndicator`: Bottom structural bar.

## State Management
- Purely presentational components, strictly visual replication. No global state needed.
