# Off-Plan Landing (off-plan-ui)

> Reusable, API-driven landing page template for promoting individual off-plan projects in Dubai and capturing buyer leads.

![Status](https://img.shields.io/badge/source-private%20(GitLab)-FC6D26?style=flat-square&logo=gitlab)
![Next.js](https://img.shields.io/badge/Next.js-16-000000?style=flat-square&logo=nextdotjs&logoColor=white)
![React](https://img.shields.io/badge/React-19-61DAFB?style=flat-square&logo=react&logoColor=black)
![TypeScript](https://img.shields.io/badge/TypeScript-5-3178C6?style=flat-square&logo=typescript&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind%20CSS-4-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white)
![Leaflet](https://img.shields.io/badge/Leaflet-maps-199900?style=flat-square&logo=leaflet&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)

## Overview
Earlier campaign pages ([damac-properties](../damac-properties/), [dubailand](../dubailand/),
[fairmont-downtown](../fairmont-downtown/), [dubai-island](../dubai-island/), [ramhan](../ramhan/)) were built as
separate static sites. This project replaces that approach with one Next.js template that loads a project by slug
from [mhp-api](../mhp-api/), so a new campaign page needs content in the admin rather than a new codebase.

## Key Features
- Project data (banner, info, gallery, highlights, amenities, floor plans, prices, location, agent) fetched from the API by slug
- Sections: hero slider, overview, highlights, amenities, floor plans, pricing, gallery, travel times, location map
- Interactive location map (Leaflet)
- Lead form with country picker and phone parsing to E.164, success modal and floating contact buttons
- Leads posted to the backend landing-form endpoint
- Marketing analytics: dataLayer events and Google Ads enhanced conversions
- Configurable theme and SEO metadata

## Architecture
```mermaid
flowchart LR
    Ad[Ad campaign] --> Page[Next.js landing]
    Page -->|project by slug| API[MHP API]
    Page -->|lead form| API
    Page --> Analytics[Tag manager / Ads]
    API --> Mail[Sales notification]
```

## Tech Stack
| Layer | Technologies |
|-------|--------------|
| Framework | Next.js 16, React 19, TypeScript |
| UI | Tailwind CSS 4, Swiper, Heroicons, react-icons |
| Data | Axios |
| Maps | Leaflet, React-Leaflet |
| Delivery | Docker, Docker Compose, GitLab CI, pnpm |

## My Role
Frontend development within the team: landing page sections, API integration and lead form.

## 🔒 Source Code Access
The source code of this project is kept in a **private GitLab repository** (client / commercial project).
It is not published here. On request, I can walk through the codebase, architecture and live demo
in a **separate video call** for discussion.
