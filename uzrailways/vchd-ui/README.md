# VChD UI — Bukhara Wagon Depot Website

> Bilingual (Uzbek / Russian) corporate website for the Bukhara Wagon (Carriage) Depot of Uzbekistan Railways.

![Status](https://img.shields.io/badge/source-private%20(GitLab)-FC6D26?style=flat-square&logo=gitlab)
![Next.js](https://img.shields.io/badge/Next.js-15-000000?style=flat-square&logo=nextdotjs&logoColor=white)
![React](https://img.shields.io/badge/React-19-61DAFB?style=flat-square&logo=react&logoColor=black)
![Tailwind CSS](https://img.shields.io/badge/Tailwind%20CSS-4-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white)
![MUI](https://img.shields.io/badge/MUI-7-007FFF?style=flat-square&logo=mui&logoColor=white)
![next-intl](https://img.shields.io/badge/next--intl-i18n-0070F3?style=flat-square)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)

## Overview
The depot repairs freight wagons and performs on-site technical maintenance; it needed a public web presence describing its work, services and leadership, with a way for visitors to get in touch. This repository is the frontend: a single-page, locale-routed Next.js site that pulls services from the Django backend ([vchd-api](../vchd-api/)) and submits contact-form messages to it.

## Key Features
- **Locale-based routing** (`/uz`, `/ru`) with next-intl middleware and per-language message catalogues.
- **Landing sections** — hero banner, statistics counters, about, photo gallery, leadership, services, useful government links and footer.
- **Dynamic services block** loaded from the backend REST API via a shared Axios client, with loading state.
- **Contact / feedback form** posting visitor enquiries to the backend.
- **Gallery and carousels** built with Swiper; scroll and entrance animations with AOS and Framer Motion.
- **Responsive UI** combining Tailwind CSS 4 utilities with MUI components and icon sets (MUI Icons, Lucide, React Icons).
- **Containerised build** with a Dockerfile and GitLab CI pipeline.

## Architecture
```mermaid
flowchart LR
    Browser --> MW[next-intl middleware]
    MW --> Pages["App Router - [lang] page"]
    Pages --> Components[Section components]
    Components -->|Axios| API[Django REST API]
```

## Tech Stack
| Layer | Technologies |
|-------|--------------|
| Framework | Next.js 15 (App Router, Turbopack), React 19 |
| Styling | Tailwind CSS 4, MUI 7, Emotion / styled-components |
| i18n | next-intl (Uzbek, Russian) |
| UI / motion | Swiper, AOS, Framer Motion, Lucide, React Icons |
| Data | Axios |
| Tooling | ESLint, Yarn |
| DevOps | Docker, GitLab CI/CD |

## My Role
Frontend development: page layout and components, internationalisation, API integration with the backend, animations and responsive design, containerised deployment.

## 🔒 Source Code Access
The source code of this project is kept in a **private GitLab repository** (client / commercial project).
It is not published here. On request, I can walk through the codebase, architecture and live demo
in a **separate video call** for discussion.
