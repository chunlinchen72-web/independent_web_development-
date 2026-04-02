# Changelog - ZHUOTAI Independent Web Project

All notable changes to this project will be documented in this file.

---

## [0.5.0] - 2026-02-27
### Added
- **Industry Consulting Module**: Created `/industry-consulting` route with market trends, raw material trackers, and expert insights to increase B2B user engagement.
- **Professional About Us Page**: Implemented `/about` with sections for Company Overview, Team Strengths, and Future Vision to build global buyer trust.
- **Admin Authorization Guard**: Added a security layer in `app/admin/layout.tsx` that forces a redirect to the home page if a non-admin user (non-`admin@zhuotai.com`) attempts to access management routes.
### Changed
- Refactored "How It Works" navigation to "Industry Consulting" across Header and Footer for better business alignment.
- Updated `Navbar.tsx` to conditionally render the "Admin" link based on user email.

## [0.4.0] - 2026-02-26
### Added
- **Admin Management Platform**: Created a dedicated `/admin` suite including:
  - **Admin Overview**: Business KPIs (Users, Orders, Revenue).
  - **User Management**: Enterprise profile auditing and status control.
  - **Transaction Monitor**: Real-time production and shipping status tracking for global sales.
- **Enhanced User System**: Integrated registration flow (`/register`) and dynamic Navbar user states using `localStorage`.

## [0.3.0] - 2026-02-26
### Added
- **Customer Portal (Dashboard)**: Implemented specialized user areas:
  - **Order Tracking**: Visual production-to-delivery lifecycle monitoring.
  - **Product Customization**: R&D request system for bespoke yarn specs.
  - **Quote History**: Table-based management for past estimates and repeat ordering.
- **Login System**: Basic `/login` functionality with session simulation.

## [0.2.0] - 2026-02-26
### Added
- **Core Quoting System**: Developed `/api/quote` backend with hidden cost logic and `/instant-quote` frontend form.
- **Digital Product Catalog**: Created `/products` with B2B-specific parameter filters (Yarn type, Count, Composition).
### Fixed
- **Build Error**: Resolved `Module not found` for `@/*` aliases by correctly re-mapping paths in `tsconfig.json`.

## [0.1.0] - 2026-02-26
### Added
- **Project Scaffold**: Initialized Next.js 15 (App Router) with TypeScript.
- **Brand UI System**: Defined global CSS variables (Industrial Blue/Technical Grey) and responsive base layout.
- **SEO/GEO Optimization**: Integrated Schema.org (Organization) metadata for AI search engine trust signals.

---
*Last updated by Gemini CLI - Senior Software Engineer Assistant.*
