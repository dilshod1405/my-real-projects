# Agromakon Admin

> Back-office panel for Agromakon moderators and administrators: seller and product moderation, orders, deposits, users and stores.

![Status](https://img.shields.io/badge/source-private%20(GitLab)-FC6D26?style=flat-square&logo=gitlab)
![React](https://img.shields.io/badge/React-19-61DAFB?style=flat-square&logo=react&logoColor=black)
![TypeScript](https://img.shields.io/badge/TypeScript-5.9-3178C6?style=flat-square&logo=typescript&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-8-646CFF?style=flat-square&logo=vite&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind%20CSS-4-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white)
![TanStack Query](https://img.shields.io/badge/TanStack-Query%20%26%20Table-FF4154?style=flat-square&logo=reactquery&logoColor=white)
![shadcn/ui](https://img.shields.io/badge/shadcn%2Fui-000000?style=flat-square&logo=shadcnui&logoColor=white)

## Overview
The internal staff panel of the Agromakon marketplace. Only users with the MODERATOR or ADMIN role can sign in; buyers
and sellers are rejected immediately after authentication. It is a single-page application on top of the
[agromakon-core](../agromakon-core/) admin and moderation APIs, complementing the public
[agromakon-web](../agromakon-web/) storefront.

## Key Features
- **Dashboard**: queue counters (new seller applications, products awaiting moderation), today's orders and totals,
  active/verified stores and a recent-activity feed
- **Seller application moderation** in a split view: queue, application details, uploaded documents, history,
  approve / reject with reason
- **Product moderation**: gallery, price, classification codes, variants and attributes; approve, reject or unpublish
- **Orders**: global order table with filters and a side detail panel; staff cancellation with reason
- **Deposits**: track seller sale deposits by payment ID / contract number, confirm receipt, refund or withhold
  (admin-only rate settings)
- **Users & staff**: search, edit contact data, block/unblock (including bulk), soft delete with a moderator-request /
  admin-approval flow, pre-create accounts, assign staff roles
- **Stores**: deactivate/activate with reason, "verified store" badge (admin only)
- **Role-based UI** mirroring backend permissions; keyboard-driven moderation (next/previous, approve, reject) and a
  global command search
- Filters, selection and opened items persisted in the URL for shareable links
- **Mock mode**: a full in-memory demo backend (lazy-loaded) so the panel can be shown without the API

## Architecture
Typed API layer with a single `AdminApi` contract and two implementations — HTTP (against the core) and mock — selected
at build time. All server state goes through TanStack Query hooks; routes are lazy-loaded and protected by role guards.

```mermaid
flowchart LR
  Staff[Moderator / Admin] --> SPA[React SPA]
  SPA --> Contract[AdminApi contract]
  Contract --> Http[HTTP client] --> Core[agromakon-core /api/v1]
  Contract -.demo.-> Mock[In-memory mock]
```

## Tech Stack
| Layer | Technologies |
| --- | --- |
| UI | React 19, TypeScript 5.9, Tailwind CSS 4, shadcn/ui (Radix), lucide-react, sonner |
| Routing / data | React Router 7 (data router), TanStack Query 5, TanStack Table |
| Forms | react-hook-form, zod |
| Build / tooling | Vite 8, ESLint 9, npm |

## My Role
Frontend development: panel architecture, API contract and data layer, moderation and admin workflows, role-based
access in the UI, and the mock demo mode.

## 🔒 Source Code Access
The source code of this project is kept in a **private GitLab repository** (client / commercial project).
It is not published here. On request, I can walk through the codebase, architecture and live demo
in a **separate video call** for discussion.
