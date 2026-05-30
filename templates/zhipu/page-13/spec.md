# Zhipu AI Drawing Chat UI

## Overview
A high-fidelity replica mirroring the `page-14` "AI画图" (AI Drawing) interface. This represents the primary prompt-to-image conversation module where users describe scenes triggering visual generative models, showcasing rich bubble layouts, photo grids, and an extensive action toolbar.

## Visual Design Details

### Application Header
- **Context Lock**: A sticky white bounding header isolating the AI identity.
- **Agent Identity**: "AI画图" mapped with a custom Zhipu glowing orb avatar (dark space blue gradients mixed with neon pink/blue crossover lines). Subtitled in grey text confirming the source "来自: 智谱清言".
- **Header Actions**: Features standard conversation management toggles including History (Clock), Audio muting (Speaker slashed), and More (Meatballs menu), all using crisp `#111` stroke icons.

### Conversation Trace (Canvas)
- **Prompt Bubble**:
  - The massive instructional chat bubble anchors to the left taking up max width (`mx-4`) representing the echoed prompt payload.
  - Housed inside a highly rounded blue-grey block (`bg-[#EBEEF6]`) with an intentional sharp `rounded-tl-[4px]` corner tracing the directional origin.
  - Typography is relaxed, tracking wide for readability (`leading-[1.65]`).
- **Generation Output Grid**:
  - Drops tightly (`mt-4`) below the prompt into a distinct 2-column image layout (`grid-cols-2`).
  - Gap spacing is tightly packed (`gap-[4px]`) pushing an edge-to-edge aesthetic.
  - The generated image proxies employ rich radial gradients resembling vibrant scenic outcomes.
  - Lower right bounding context introduces a unified white watermark element labeling "清言·AI生成".

### Quick Action Carousal & Footer
- **Floating Scroller**:
  - Pinned dynamically over the footer. Contains independent prompt-augmentation pills mapping functions like "AI特效" (AI Effects), "风格" (Styles), and "比例3:4" (Aspect Ratios).
  - Employs active logic shading (`bg-[#EDF0FF] text-[#3B4CF3]`) purely on the Ratio selector indicating its currently applied state.
  - Includes a bright green relative "新" (New) badge overlapping the first action for feature discovery bounding.
- **Input Terminal**:
  - A massive floating pill (`bg-white shadow-xl` and `bg-[#F8F9FB]` inner core) bounding the keyboard trigger zone.
  - The empty state placeholder uses welcoming conversational vernacular: "有什么问题尽管问我！".
  - Houses quick attachment logic `[+]` and vocal prompt triggers.
- **Mandatory Appliation Footer**: Contains the standard AI disclaimer text spanning horizontally across the lowest margin `内容由AI生成，仅供参考和借鉴`.

## Component Handling
- Designed cleanly utilizing absolute/sticky anchoring for the `Footer` module ensuring the chat elements dynamically scroll behind it with proper padding offsets. Overflow hiding ensures horizontal carousels behave precisely like native iOS elements smoothly.
