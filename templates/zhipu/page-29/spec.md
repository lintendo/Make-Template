# Zhipu AI Core Persona Direct Chat Interface 

## Overview
A high-fidelity replica mirroring `page-30`. Unlike previous screens focusing on specific agents ("AI搜索"), this represents the baseline Core Persona ("清言") primary chat state. It highlights the advanced multi-modal prompt terminal, structured generative responses with interaction toolbars, predictive prompt cascading, and a distinct aesthetic baseline.

## Visual Design Details

### General Layout Context
- **Global Background**: A highly subtle cool-grey/white `bg-[#F4F5F8]`.
- **Top Header Boundary**: 
  - Minimalistic persona assignment: Replaces the custom agent radial gradient with the primary Zhipu brand logo (interlocked rings inside a solid blue `bg-[#3B53FF]` circle). 
  - Standardized rigid system controls remain strictly right-aligned (History, Mute, Menu).

### Conversation Stream Hierarchy
- **User Issuance (Right)**: Standard layout `bg-[#E8EEFC] text-[#111111]` with right-bound angular corner rounding (`rounded-[22px] rounded-tr-[4px]`).
- **AI Synthesis (Left)**: 
  - Massive structured white cards (`bg-[#FFFFFF] rounded-[22px] rounded-tl-[4px]`).
  - Contains rich generative paragraph output cleanly tracking user queries.
  - **Inline Action Toolbar**: Mapped inside the bubble's bottom edge. 
    - Left-bound: Dominant blue circular Text-to-Speech play trigger (`bg-[#EDF2FF] text-[#3B53FF]`).
    - Center/Right-bound: Utility matrix (Like, Dislike, Copy, Export PDF, Share) spaced evenly.
    - Right-bound watermark: `AI生成` (AI Generated) cast in muted grey (`text-[#D8DADC]`).

### Predictive Prompt Array (Floating)
- Situated tightly above the input terminal.
- **Vertical Stack**: A cascading list of single-tap prompt continuations (e.g., "祝福语更文艺一些" - Make it more artistic). 
- Styled as crisp white capsule buttons (`bg-white border border-[#E9EAEF] px-[14px] py-[10px]`).
- Bounded right by a floating circular anchor (`v`) allowing the user to immediately scroll to the newest input edge.

### Advanced Multi-Modal Input Deck
- **Pre-Input Skill Tape**: A horizontal scrollable injection row located directly above the primary input form. Houses modality triggers: "写作" (Write), "拍照解读" (Visual Analysis), "生视频" (Generate Video) inside tight, bordered pill buttons with leading monochrome icons.
- **Primary Input Block**:
  - Replaces the simple pill layout with a massive, distinct rectangular control deck (`bg-white rounded-[24px] border border-[#EFEFEF] p-[10px] shadow-sm`).
  - **Top Row**: Standard placeholder text bounding.
  - **Bottom Tool Row**: 
    - Left: Attachment trigger (`+`).
    - Middle: Stateful semantic routing tags. "推理" (Reasoning) and "沉思" (Deep Think) are inactive (`bg-[#F4F5F8]`). "联网" (Internet Browsing) is actively selected, highlighted by brand colors (`bg-[#ECF2FF] text-[#3B53FF]`).
    - Right: Dictation trigger locked to the corner.
