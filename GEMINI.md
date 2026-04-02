# ZHUOTAI Independent Web - Project Memory & Context

This file serves as the persistent memory for Gemini CLI. It defines the project's architecture, business logic, and current state to ensure seamless continuity across different machines and sessions.

## 1. Technical Core
- **Framework**: Next.js 15 (App Router) + TypeScript.
- **Styling**: Vanilla CSS with global variables in `app/globals.css`.
- **Language System**: Real-time multi-language architecture via `context/LanguageContext.tsx`. Supports **EN, ES, CN**.
- **Path Aliases**: Fixed in `tsconfig.json` as `@/*` -> `./*` (no `/src` folder used).
- **Navbar Sync**: Uses `window.dispatchEvent(new Event('storage'))` to trigger cross-component updates (e.g., when profile name is edited).

## 2. Business Logic & Security
- **Admin Identity**: Strictly locked to email `admin@zhuotai.com`.
- **Authorization**: Render-blocking Auth Guard in `app/admin/layout.tsx`. Redirects non-admins to home.
- **Quoting Engine**: Secure backend logic in `app/api/quote/route.ts` with randomized 3-8% price protection.
- **User Sessions**: Simulated via `localStorage` (key: `zhuotai_user`).

## 3. Key Modules Implemented
- **Instant Quote (v2)**: 
  - Advanced tile-based parameter selection (no defaults).
  - Dynamic "Other" input fields with focus persistence (via `OptionGroup` extraction).
  - Step 2: Logistics & Packaging (Incoterms, Shipping methods).
  - Conditional submit button (blue only when form is 100% valid).
- **Customer Dashboard**: 
  - Professional profile overview with shipping address.
  - **Separate Edit Page**: `/dashboard/profile/edit` for secure profile management.
- **Admin Suite**: Business analytics using custom SVG-based traffic and revenue trend charts.
- **UI Architecture**: Header/Navbar layer set to `z-index: 9999 !important` to prevent overlap by page content.

## 4. Current Development State
- [x] Full-site Multi-language (Real-time sync across all 10+ subpages).
- [x] Admin Security & Redirection.
- [x] Advanced Quoting UI (Tile selection + custom inputs).
- [x] Separate Profile Editing flow.
- [x] Enhanced Footer (B2B social links, material/app categories).

## 5. Development Guidelines for AI
- **Translations**: Always update `lib/translations.ts` for ANY new UI text.
- **Z-Index**: Keep header elements at 9000+ and dropdowns at 9999.
- **Components**: Keep `OptionGroup` and other reusable UI logic in `components/` or as stable top-level exports to avoid focus loss.

---
*Last Updated: 2026-02-27 | Compiled by Gemini CLI*
