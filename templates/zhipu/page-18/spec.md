# Zhipu AI Share Conversation UI

## Overview
A high-fidelity replica mirroring the `page-19` "分享对话" (Share Conversation) state. This interface represents a dark-mode active selection modal triggered over an existing conversation history, presenting a bottom-sheet with extensive social and system export routing options while allowing users to select specific Q&A message pairs to package.

## Visual Design Details

### Context Environment (Background)
- **Base Canvas**: The foundational view is a continuous chat thread overlaid atop a complex background image (anime character art). During the share state, the entire background and non-selected UI elements are heavily darkened (`bg-black/60`) focusing attention on the selection logic.
- **Top Header**: Operates as a solid dark navigation anchor (`bg-[#121215]`). Houses the active "取消" (Cancel) button mapped to `#3B4CF3` (Zhipu Blue) and standard central titling "分享对话" (Share Conversation).

### Message Selection Matrix
- **Pair Selection Logic**: The selection mechanics operate on Q&A pairs (Prompt + Response grouped together). 
- **Checkboxes**: Positioned fixed on the left margin (`pl-4`). 
  - Unselected: Empty structural ring (`border-[1.5px] border-[#A0A0A0]`).
  - Selected: Filled state using a solid white circle bounding a dark-grey checkmark.
- **Bubble Aesthetics**:
  - The chat bubbles leverage heavy glass-morphism to blend with the background art (`backdrop-blur-md`).
  - User Prompts (Right): Utilize a dark-indigo washed base (`bg-[rgba(50,60,95,0.85)]`).
  - AI Responses (Left): Utilize a dark-charcoal washed base (`bg-[rgba(30,30,30,0.85)]`).
- **Active State Highlighting**: Selected elements (specifically the AI response bound to the active checkbox) receive a distinct glowing selection border (`border-[1px] border-[#3B4CF3]`) to visually confirm selection tracking.

### Deep Bottom Sheet (Share Matrix)
- **Container**: A fixed bounding box sliding up from the bottom edge (`bg-[#18181A] rounded-t-[20px]`).
- **Selection Control Bar**:
  - Contains a global "全选" (Select All) checkbox alignment identical to the item nodes.
  - Terminated on the right by a neutral grey native `X` close icon.
- **Primary Export Row (Socials)**: 
  - A horizontal array of major platform destinations. Each node leverages a distinct vibrant brand color mapping inside a perfect circle `w-[52px] h-[52px]`:
    - 微信好友 (WeChat): `#0CD782`
    - 小红书 (RED): `#FF3344`
    - 微博 (Weibo): `#FF843B`
    - 朋友圈 (Moments): `#2CE7B4`
    - 社区 (Community): `#F8C035`
    - 更多 (More): `#333333`
- **Secondary Export Row (System Intents)**:
  - Utility actions sitting below the social ribbon. Uses uniform dark-grey circle nodes (`bg-[#333333]`):
    - 生成图片 (Generate Image - Long screenshot export)
    - 复制链接 (Copy Link)
- **Footer**: Standard iOS home indicator lock.
