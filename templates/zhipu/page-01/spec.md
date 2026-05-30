# Zhipu Splash Screen

## Overview
A high-fidelity standalone replication of the Zhipu application splash screen. This page features a minimalist clean background, a central 3D-styled glassmorphism illustration of an AI assistant character surrounded by floating functional icons, and the brand logo securely positioned at the bottom.

## Visual Design Details

### Layout
- **Container**: Full-width, full-height (`w-screen h-screen`), flex column navigation.
- **Top Bar**: Standard iOS status bar with time (17:51), cellular, Wi-Fi, and battery icons.
- **Main Content**: Centered vertically and horizontally. Contains the main mascot illustration.
- **Footer**: Brand logo centrally aligned near the bottom.
- **Bottom Bar**: Standard iOS home indicator.

### Colors
- **Background**: Solid White (`#FFFFFF`).
- **Logo Mark**: Deep Blue (`#2B52FF`).
- **Logo Text**: Very Dark Blue / Black (`#111111`).
- **Mascot Base**: Light Blue gradient with a glassy appearance.

### Typography
- **Status Bar**: System Font, bold, ~15px.
- **Logo Text**: Sans-serif, Bold, ~24px, closely tracking.

## Components Structure
- `SplashScreen`: Main functional component.
  - `StatusBar`: Reusable top bar.
  - `MascotIllustration`: A composite of HTML/CSS and SVGs forming the 3D AI assistant character and surrounding floating tool elements.
  - `FooterBrand`: SVG logo mark and the text "智谱清言".
  - `HomeIndicator`: bottom horizontal bar.

## State Management
- Purely presentational component, no internal state needed.
