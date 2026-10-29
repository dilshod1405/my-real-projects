# Fairmont Downtown Landing

> Campaign landing page for a Fairmont-branded residential project in Downtown Dubai, built to present the residences and capture buyer leads.

![Status](https://img.shields.io/badge/source-private%20(GitLab)-FC6D26?style=flat-square&logo=gitlab)
![React](https://img.shields.io/badge/React-18-61DAFB?style=flat-square&logo=react&logoColor=black)
![Vite](https://img.shields.io/badge/Vite-5-646CFF?style=flat-square&logo=vite&logoColor=white)
![Ant Design](https://img.shields.io/badge/Ant%20Design-5-0170FE?style=flat-square&logo=antdesign&logoColor=white)
![Bootstrap](https://img.shields.io/badge/Bootstrap-5-7952B3?style=flat-square&logo=bootstrap&logoColor=white)
![Sass](https://img.shields.io/badge/Sass-CC6699?style=flat-square&logo=sass&logoColor=white)
![Nginx](https://img.shields.io/badge/Nginx-009639?style=flat-square&logo=nginx&logoColor=white)

## Overview
One of several project landing pages that Master Homes ran for off-plan marketing campaigns. It showcases the
residences (1 to 5 bedroom layouts, rooftop and amenities), the payment plan and the location, and sends inquiries to
the sales mailbox through [smtp-service](../smtp-service/). Later campaigns moved to the API-driven
[off-plan-ui](../off-plan-ui/) template.

## Key Features
- Full-screen video hero with project branding
- Sections: Overview / residences, Highlights, Project amenities, Gallery, Prime location, Payment plan
- Floor-plan galleries per unit type (one to five bedrooms) with a downloadable floor-plan PDF behind a lead form
- "Enquire now" and "Download floorplan" modals sharing one lead form
- Lead form with international phone input, consent checkboxes and toast notifications
- Booking-modal deep link route for ad campaigns
- Google Tag Manager, Google Ads and web analytics tracking
- Static build served by Nginx in Docker

## Tech Stack
| Layer | Technologies |
|-------|--------------|
| Framework | React 18, Vite 5, React Router 7 |
| UI | Ant Design 5, Bootstrap 5, Sass, Swiper, react-slick, react-icons |
| Forms | react-phone-input-2, Axios, react-toastify |
| Delivery | Docker, Nginx, GitLab CI |

## My Role
**Full-Stack Developer** — layout, media galleries and lead form integration.

## 🔒 Source Code Access
The source code of this project is kept in a **private GitLab repository** (client / commercial project).
It is not published here. On request, I can walk through the codebase, architecture and live demo
in a **separate video call** for discussion.
