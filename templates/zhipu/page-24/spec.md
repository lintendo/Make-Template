# Zhipu AI History Log Empty State Modal

## Overview
A high-fidelity replica mirroring the `page-25` "历史记录" (History Record) layout. This view maps a full-height interactive bottom-drawer modal positioned over the dimmed primary `AI搜索` layout, illustrating the specific empty-state graphical logic when no historical data exists.

## Visual Design Details

### Absolute Modal Overlay Geometry
- **Dimming Protocol**: An `opacity-30` or `bg-black/30` static overlay shields the background, preventing context collision while preserving navigational awareness of the parent state.
- **Drawer Anchor**: 
  - Massive bottom sheet bounding specifically to `h-[calc(100vh-100px)]`, leaving exactly enough clearance to allow the underlying parent view's custom radial avatar header to remain partially visible.
  - Geometry is constrained by a heavy `rounded-t-[20px]` establishing the modal separation.

### Header Mechanics
- Deeply simplified navigation logic stripped of clutter.
- Massive, bold `历史记录` title pinned left (`text-[18.5px] font-[650]`).
- Clean, thin-stroked `X` exit path pinned right for immediate modal termination capability.

### Empty State Vector Composition
- Vertically and horizontally centered within the modal viewport (offset upwards slightly, about `pb-[20vh]`, to account for optical mobile centering).
- **Custom Dual-Bubble Illustration**:
  - Entirely constructed via native CSS layering.
  - **Left Base Layer**: Large, light neutral-grey `bg-[#F4F5F8]` speech bubble mapping native dark `bg-[#222]` indicator dots. Features characteristic non-uniform borders (`rounded-[24px] rounded-bl-[4px]`).
  - **Right Overlap Layer**: Smaller, slate blue `bg-[#AEC2DF]` overlay bubble. Features a hard `border-[2px] border-white` to create a visual knockout effect against the base layer.
- **Support Text**: Highly muted, widely tracked placeholder description `"暂无记录"` (No records yet) explicitly mapped to text grey (`#A6ABB5`).
