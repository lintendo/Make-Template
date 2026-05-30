# Zhipu AI Seamless Authentication Flow (Login Page)

## Overview
A high-fidelity replica mirroring the `page-29` One-Click Authentication interface. This view acts as the front door gatekeeper for unauthenticated sessions, leveraging a pure white interface targeting local carrier data injection ("一键登录") to bypass manual credential entries.

## Visual Design Details

### Root Context
- A complete departure from the active chat layout, providing a pure solid `bg-[#FFFFFF]` full-viewport canvas.
- No navigation header bar exists; the only global control is a single absolute right-pinned `X` vector (`top-[60px] right-[24px]`) to exit the auth flow without converting.

### Brand Identity Lockup
- Centered horizontally, situated in the top 30% of the viewport.
- **Logo Configuration**: Extracted custom SVG representing the primary Zhipu intertwined rings (`fill-[#2746E5]`), positioned cleanly beside heavy corporate typography ("智谱清言", `text-[26px] font-[850]`).
- **Persona Subtitle**: "嗨👋 我是清言，你的全能AI助手". Sets a conversational baseline tone below the rigid lockup.

### Credential Target (One-Click Protocol)
- Centers upon masked string rendering the injected carrier phone number ("186****3352"). Uses a dramatically scaled typography (`text-[34px] font-[650] tracking-wide`).
- Immediately substantiated by the source provider label (`中国联通提供认证服务`, muted grey `text-[11.5px]`).

### Action Routing
- **Primary Authorization**: Massive pill button taking the full layout margins (`mx-[32px] bg-[#3B53FF] text-white py-[14px] rounded-full`). Triggers "本机号码一键登录".
- **Fallback Route**: Standalone raw text link enabling SMS failover ("短信验证码登录 >"). Mapped strictly to the primary interactive brand blue (`text-[#3B53FF]`).

### Legal Trace & Compliance (Footer)
- Anchored to the extreme bottom (`bottom-[40px]`).
- Utilizes a left-aligned custom checkbox (`w-[14px] h-[14px] bg-[#3B53FF]`) driving a tightly grouped block of compliance verbiage (`text-[11.5px] leading-relaxed`).
- Differentiates plain instructive text (`text-[#8A8F99]`) from bounded interactive TOS links (`text-[#3B53FF]`).
