# Zhipu VIP Subscription Page (开通会员)

## Overview
A high-fidelity standalone replication of the VIP subscription / upgrade screen ("开通会员") for the Zhipu application. This page aims to convert free users to VIP members by showcasing subscription tiers, exclusive privileges, and a detailed feature comparison table.

## Visual Design Details

### Layout & Spacing
- **Container**: Mobile viewport (`w-full h-full`), fixed header, scrollable content.
- **Hero Background**: Vibrant purple-to-blue gradient spanning the top third of the screen, featuring glowing stars and a glassy 3D shield graphic.
- **Content Overlay**: A white card with rounded top corners (`rounded-t-[20px]`) that pulls up over the hero background.
- **Plans Carousel**: A horizontally scrolling list of subscription options. The selected option is highlighted with a gold border and yellow gradient background.
- **Privileges List**: A 4-column grid of circular gold icons with dark-brown titles and light-brown subtitles.
- **Comparison Table**: A stylized alternating row table with a warm off-white background and gold accents to compare "VIP" vs "Non-member".
- **Bottom Bar**: A fixed bottom panel (or just at the bottom of the scroll view) containing the main "开通会员" CTA button and agreement checkboxes.

### Colors
- **Header & Hero**: Deep purplish-blue gradients (`from-[#331DC2] via-[#6136EE] to-[#AE62F5]`). Text is `white`.
- **Content Base**: Solid `white`.
- **Selected Plan Card**: Background `bg-gradient-to-b from-[#FFFDF2] to-[#FCE5AA]`, Border `#E5D397`, Red Tag `bg-[#F14D3E]` / `bg-gradient-to-r from-[#F0553C] to-[#EE3527]`.
- **Unselected Plan Card**: Background `white`, Border `#E8DFCB`, Text `#333`.
- **Privileges Title Text**: `#976D2C`.
- **Table Background**: Section headers & top row `bg-[#FDF6E1]`, body rows `bg-[#FAF7F0]`.
- **CTA Button**: Soft gold `bg-[#FCE198]` with dark text `#4F3707`.

### Components Structure
- `SubscriptionPage`: Main wrapper.
  - `Header`: Status bar and Nav bar with inverted (white) colors.
  - `HeroSection`: User profile avatar, current status, and 3D graphic.
  - `OverlaySheet`: The main white container.
    - `SubscriptionOptions`: Horizontal scrollable list `SubscriptionCard`s.
    - `BillingHint`: Small helper text.
    - `PrivilegesSection`: 4 icon buttons.
    - `ComparisonTable`: Structured grid comparing features.
    - `BottomAction`: The main CTA and agreement checkbox.

## State Management
- Replicated purely visually. No active application state or logic attached.
