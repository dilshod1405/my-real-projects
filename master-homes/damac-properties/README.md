# DAMAC Islands Landing (damac-properties)

> Bilingual campaign landing page used by Master Homes to promote the DAMAC Islands off-plan launch and collect buyer inquiries (EOIs).

![Status](https://img.shields.io/badge/source-private%20(GitLab)-FC6D26?style=flat-square&logo=gitlab)
![React](https://img.shields.io/badge/React-18-61DAFB?style=flat-square&logo=react&logoColor=black)
![Vite](https://img.shields.io/badge/Vite-6-646CFF?style=flat-square&logo=vite&logoColor=white)
![Sass](https://img.shields.io/badge/Sass-CC6699?style=flat-square&logo=sass&logoColor=white)
![i18next](https://img.shields.io/badge/i18next-26A69A?style=flat-square&logo=i18next&logoColor=white)
![Nginx](https://img.shields.io/badge/Nginx-009639?style=flat-square&logo=nginx&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)

## Overview
A marketing site built for a paid-traffic campaign by Master Homes, a broker selling the DAMAC Islands project
(townhouses and villas). Visitors read about the project, browse the gallery and floor plans, and leave their
details; each inquiry is forwarded by e-mail through the group's [smtp-service](../smtp-service/). The same
template was reused for [dubailand](../dubailand/).

## Key Features
- Hero section with starting price, payment plan and "Register your interest" call to action
- Sections: About, Gallery (carousel), Amenities, Floor plans and pricing, Economic / investment highlights, Location, Contact
- Brochure and floor-plan download requests gated by a lead form
- Lead form and modal form with international phone input and consent checkboxes
- English / Russian localisation with i18next (JSON translations, browser language detection)
- Dedicated route that opens the booking modal directly (for ad links)
- Google Tag Manager / Google Ads tracking
- Served as a static build from Nginx in Docker

## Tech Stack
| Layer | Technologies |
|-------|--------------|
| Framework | React 18, Vite 6, React Router 7 |
| UI | Sass, Swiper, react-slick, react-icons, react-toastify |
| Forms | react-phone-input-2, Axios |
| i18n | i18next, react-i18next |
| Delivery | Docker, Nginx, GitLab CI |

## My Role
Frontend development within the team: page sections, responsive layout, localisation and lead form.

## 🔒 Source Code Access
The source code of this project is kept in a **private GitLab repository** (client / commercial project).
It is not published here. On request, I can walk through the codebase, architecture and live demo
in a **separate video call** for discussion.
