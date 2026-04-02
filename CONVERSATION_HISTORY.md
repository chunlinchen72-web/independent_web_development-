# ZHUOTAI Textile Independent Web Project - Development History Log

**Date:** February 26, 2026
**Project Location:** `C:\Users\chenchunlin\independent-web`
**Status:** Core Framework & Business Logic Implemented (MVP)

---

## 1. Project Objectives (Extracted from ZHUOTAI Doc)
- **Primary Goal:** Create a "Digital Sales + Customer Collaboration Platform".
- **Key Capabilities:**
  - **Automation:** Parameter-based automatic quoting system (similar to JLC PCB).
  - **Optimization:** SEO & GEO (Generative Engine Optimization) for AI search engines like ChatGPT/Copilot.
  - **Customer Portal:** Order lifecycle tracking, custom specifications (R&D), and data-driven insights.
  - **Security:** Hidden pricing logic and anti-scraping mechanisms.

## 2. Technical Stack
- **Framework:** Next.js 15 (App Router) + TypeScript.
- **Rendering Strategy:** Server-Side Rendering (SSR) to support deep indexing and AI crawling.
- **Styling:** Vanilla CSS (Global Variables) for high performance and brand consistency.
- **API Strategy:** Next.js API Routes (Serverless) for secure business logic.

## 3. Implemented Modules

### A. Core Quoting Engine (`/api/quote`)
- Implemented a secure backend API that calculates yarn prices based on:
  - Yarn Type (Compact, Ring Spun, etc.)
  - Count & Composition
  - Quantity Tiers (MOQ-1T, 1-3T, 10T+)
  - Risk & Random Buffer (Price Protection)

### B. Digital Catalog (`/products`)
- Parameterized product listing with a professional B2B filter sidebar.
- Grid-based product display showing technical specs (Count, Composition).

### C. Enterprise User System (`/login`, `/register`, `/dashboard`)
- **Dynamic Navbar:** A client-side component that detects login state via `localStorage` and updates UI (Login/Register vs. Username/Logout).
- **Registration:** Corporate account application flow.
- **Customer Portal:**
  - **Dashboard:** Strategic insights (Raw material trends).
  - **Order Tracking:** Visual progress bar (Production -> QC -> Shipped).
  - **Customization:** Advanced R&D request form for non-standard specs.
  - **Quote History:** Management table for tracking and converting quotes.

## 4. Key Files & Structure
```text
independent-web/
├── app/
│   ├── api/quote/route.ts      # Backend Quoting Logic
│   ├── dashboard/              # Customer Portal (Layout + Pages)
│   ├── instant-quote/          # Public Quoting Tool
│   ├── login/                  # Corporate Login
│   ├── products/               # Product Listing
│   ├── register/               # Account Application
│   ├── globals.css             # Industrial Brand UI System
│   └── layout.tsx              # SEO/GEO Metadata & Navbar Wrapper
├── components/
│   └── Navbar.tsx              # Dynamic Auth Component
└── tsconfig.json               # Path Alias: "@/*" -> "./*"
```

## 5. Important Fixes & Configurations
- **Path Aliases:** Fixed `Module not found` error by updating `tsconfig.json` to map `@/*` correctly to the root (as the project does not use a `/src` folder).
- **Price Protection:** Implemented a +3% to +8% random price float on the server to prevent competitors from reverse-engineering the cost model.
- **GEO Ready:** Injected `Schema.org` Organization JSON-LD into the root layout for AI-engine trust signals.

## 6. How to Resume Development
1. `npm install`
2. `npm run dev`
3. Access `http://localhost:3000`

## 7. Recent Updates (Feb 27, 2026)

### A. Instant Quote Page Enhancements
- **Dynamic Visual Preview:** 
  - Redesigned "Step 1: Define Your Requirements" with a responsive two-column layout.
  - Added a "Product Preview" image box that dynamically updates based on selected **Yarn Type** and **Yarn Count**.
  - Implemented placeholder logic using high-quality textile imagery (Unsplash) to represent different spinning technologies (Ring Spun, Compact, etc.).
  - Added interactive UI feedback (Hover scale effects, sticky positioning for the preview box).
- **Internationalization (i18n):**
  - Added missing translation keys (`selectTypeToPreview`, `productPreview`) across **EN, ES, and CN** locales in `lib/translations.ts`.
- **Bug Fixes:**
  - Corrected a data mapping error in the quoting form submission where `quantityKg` was incorrectly referenced as `yarnKg`.

---
*Log updated by Gemini CLI - Senior Software Engineer Assistant.*
