# DAMAC Riverside Landing (dubailand)

> Bilingual campaign landing page used by Master Homes to promote the DAMAC Riverside off-plan launch and collect expressions of interest.

![Status](https://img.shields.io/badge/source-private%20(GitLab)-FC6D26?style=flat-square&logo=gitlab)
![React](https://img.shields.io/badge/React-18-61DAFB?style=flat-square&logo=react&logoColor=black)
![Vite](https://img.shields.io/badge/Vite-6-646CFF?style=flat-square&logo=vite&logoColor=white)
![Sass](https://img.shields.io/badge/Sass-CC6699?style=flat-square&logo=sass&logoColor=white)
![i18next](https://img.shields.io/badge/i18next-26A69A?style=flat-square&logo=i18next&logoColor=white)
![Nginx](https://img.shields.io/badge/Nginx-009639?style=flat-square&logo=nginx&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)

## Overview
A one-page marketing site for the DAMAC Riverside project (apartments and townhouses), built on the same template as
[damac-properties](../damac-properties/). It presents the project, prices and floor plans, and turns ad traffic into
leads that are e-mailed to the sales team through [smtp-service](../smtp-service/).

## Key Features
- Hero with starting price, payment plan and EOI call to action
- About, Gallery, Amenities, Floor plans and pricing, Economic highlights, Location and Contact sections
- Per-unit-type cards (1-2 BR apartments, 4-5 BR townhouses) with floor-plan request buttons
- Brochure download and "request units and prices" flows through a lead modal
- Lead forms with international phone input and consent checkboxes
- English / Russian translations loaded at runtime with i18next
- Google Tag Manager / Ads tracking; static build served by Nginx in Docker

## Tech Stack
| Layer | Technologies |
|-------|--------------|
| Framework | React 18, Vite 6, React Router 7 |
| UI | Sass, Swiper, react-slick, react-icons, react-toastify |
| Forms | react-phone-input-2, Axios |
| i18n | i18next, react-i18next, http backend, language detector |
| Delivery | Docker, Nginx, GitLab CI |

## My Role
**Full-Stack Developer** — content sections, localisation and lead capture.

## 🔒 Source Code Access
The source code of this project is kept in a **private GitLab repository** (client / commercial project).
It is not published here. On request, I can walk through the codebase, architecture and live demo
in a **separate video call** for discussion.
