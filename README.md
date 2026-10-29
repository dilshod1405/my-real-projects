<div align="center">

# 💼 My Real Projects

**Dilshod Normurodov** — Software Engineer · Tashkent, Uzbekistan

A showcase of the commercial and client projects I have worked on.
**54 repositories** across fintech, government, real estate, education, IoT/edge and automation.

![Projects](https://img.shields.io/badge/projects-54-0A66C2?style=flat-square)
![Source](https://img.shields.io/badge/source-private%20(GitLab)-FC6D26?style=flat-square&logo=gitlab)
[![GitHub](https://img.shields.io/badge/GitHub-dilshod1405-181717?style=flat-square&logo=github)](https://github.com/dilshod1405)

</div>

---

> [!IMPORTANT]
> **This repository contains documentation only — no source code.**
> All projects listed here are kept in **private GitLab repositories**, because they are client / commercial work.
> If you would like to see the code, architecture or a live demo, I am happy to walk you through it in a
> **separate video call** — just reach out via the contacts below.

## 📑 Contents

- [🏦 Agrobank — Mahallabay Department](#-agrobank--mahallabay-department)
- [🤝 Agrobank Mahallabay — Collaboration Platform](#-agrobank-mahallabay--collaboration-platform)
- [🎓 Edu NeoSoft — Online Education Platform](#-edu-neosoft--online-education-platform)
- [🏙️ Master Homes — Dubai Real Estate](#-master-homes--dubai-real-estate)
- [🏢 IMZA — Dubai Real Estate Agency](#-imza--dubai-real-estate-agency)
- [🛰️ Edge24 — EdgeOps Platform](#-edge24--edgeops-platform)
- [📡 ioEdge — Edge Device Management (v1)](#-ioedge--edge-device-management-v1)
- [🚗 Parking24 — Parking Management](#-parking24--parking-management)
- [🚆 Uzbekistan Railways](#-uzbekistan-railways)
- [📚 Nazar Education (nedu)](#-nazar-education-nedu)
- [🦸 HeroAcademy](#-heroacademy)
- [🦷 MediaStom](#-mediastom)
- [🤖 Telegram Bots](#-telegram-bots)

---

## 🏦 Agrobank — Mahallabay Department

Products built for the Mahallabay department of Agrobank, one of Uzbekistan's largest state banks, focused on
supporting farmers, small businesses and self-employed people at the neighbourhood (mahalla) level. The work spans
Agromakon, an agricultural marketplace with digital-signature sign-in, payments and signed sale contracts, and
Agrokredit, a configurable loan-origination platform; further products (Biznes Ayol, an internal ERP) are at the
repository-setup stage.

| Project | Description | Stack | Role |
| --- | --- | --- | --- |
| [Agromakon Core](agrobank/agromakon-core/) | Marketplace backend: catalog, seller onboarding, moderation, orders, payments, E-IMZO-signed contracts, admin API | Java 17, Spring Boot 4, Spring Modulith, PostgreSQL, Flyway, Testcontainers | Backend architecture & development |
| [Agromakon Web](agrobank/agromakon-web/) | Public storefront for buyers and sellers: catalog, cart, checkout, orders, seller area | Next.js 16, React 19, TypeScript, Tailwind CSS 4, Leaflet | Frontend development |
| [Agromakon Admin](agrobank/agromakon-admin/) | Staff panel for moderation, orders, deposits, users and stores with role-based access | React 19, TypeScript, Vite, TanStack Query, shadcn/ui, Tailwind CSS 4 | Frontend development |
| [Agrokredit API](agrobank/agrokredit-api/) | Loan-origination backend with versioned products, stop-factor, scoring, collateral, document and workflow engines | Python 3.13, Django 5.2, DRF, PostgreSQL, Celery, RabbitMQ, Redis | Backend architecture & development |
| [Agrokredit Infra](agrobank/agrokredit-infra/) | Docker Compose environment: PostgreSQL, Redis, RabbitMQ, API, Celery worker and beat | Docker Compose, PostgreSQL, Redis, RabbitMQ | Infrastructure setup |


## 🤝 Agrobank Mahallabay — Collaboration Platform

The Collaboration platform is an internal system for Agrobank's Mahallabay department, which coordinates the
head office, regional branches and bankers assigned to individual neighbourhoods (mahallas) across Uzbekistan.
It combines project and task management for office staff with field-work tooling for bankers (visits, credit
monitoring, citizen registers, geo-tracking), AI assistance and Telegram channels for residents and staff.
A Django REST API sits at the centre, with a React dashboard, a Flutter mobile app, Go and FastAPI microservices
and aiogram bots around it.

| Project | Description | Stack | Role |
|---------|-------------|-------|------|
| [Collaboration API](mahallabay-collaboration/collaboration-api/) | Core REST backend: projects/tasks, org structure, field visits, low-code forms, credits, chat, reports | Python, Django, DRF, PostgreSQL, Redis, Celery, Channels, Docker | Backend lead, API design, deployment |
| [Collaboration Dashboard](mahallabay-collaboration/collaboration-dashboard/) | Web dashboard for leadership, head office and branches, with maps, Kanban and document tools | React, TypeScript, Vite, Ant Design, Tailwind CSS, TanStack Query, Mapbox | Frontend development, API integration |
| [AI Agent](mahallabay-collaboration/ai-agent/) | Guarded LLM credit assistant for bankers and a sandboxed Excel/Word/PDF processing agent | Python, FastAPI, OpenAI API, Claude API, Redis, PostgreSQL, Docker | Service design and development |
| [Report Agent](mahallabay-collaboration/report-agent/) | Ingestion gateway validating report data captured by a browser extension before it reaches the backend | Python, FastAPI, Pydantic, pytest | Service design and development |
| [Mahallabay GeoTrack](mahallabay-collaboration/geotrack/) | Real-time location tracking service for field staff with live map streaming and route history | Go, PostgreSQL, PostGIS, Redis, WebSocket, k6 | Service design and development |
| [AgroMahalla Mobile](mahallabay-collaboration/agro-mahalla-mobile/) | Field app for mahalla bankers: visits, credits, acts, chat, training, AI assistant, background GPS | Flutter, Dart, SQLite, WebSocket | Mobile development, backend integration |
| [Mahallabay Main Bot](mahallabay-collaboration/mahallabay-main-bot/) | Telegram bot linking residents with their mahalla bankers, plus a dashboard-to-Telegram file relay bot | Python, aiogram, aiohttp, SQLite, pandas | Bot development, integration |
| [Monitoring Telegram Bot](mahallabay-collaboration/monitoring-telegram-bot/) | Telegram bot for staff field-monitoring reports and family surveys with e-signature | Python, aiogram, aiohttp, Redis | Bot development, integration |


## 🎓 Edu NeoSoft — Online Education Platform

Edu NeoSoft (edu.neosoft.uz) is an online education platform for Uzbek- and Russian-speaking learners, where mentors publish video courses and students buy, study and complete them. It is built as a set of services: a Django REST API at the core, Go microservices for real-time chat and notifications, and separate web clients for students and mentors, with local payment gateways (Payme, Click, Uzum, Multicard) and protected video streaming.

| Project | Description | Stack | Role |
|---|---|---|---|
| [Edu NeoSoft API](edu-neosoft/edu-neosoft-api/) | Core backend: courses, enrollments, payments, mentor contracts, notifications | Python, Django, DRF, PostgreSQL, Redis, Celery, Docker | Backend development, API design, integrations, deployment |
| [Edu NeoSoft Chat Service](edu-neosoft/edu-neosoft-chat-service/) | Real-time mentor-student chat per lesson over WebSocket | Go, Gorilla WebSocket, MongoDB, Docker | Service design and implementation |
| [Edu NeoSoft Notification Service](edu-neosoft/edu-neosoft-notification-service/) | Pushes notifications from Redis Streams to users over WebSocket | Go, Redis Streams, WebSocket, Docker | Service design and implementation |
| [Edu NeoSoft UI](edu-neosoft/edu-neosoft-ui/) | Student-facing website: catalogue, checkout, lessons, chat, dashboard | Next.js, React, TypeScript, Tailwind CSS, Zustand, next-intl | Frontend development and integration |
| [Edu NeoSoft Mentor UI](edu-neosoft/edu-neosoft-mentor-ui/) | Mentor dashboard for course/lesson management, students and chat | React, TypeScript, Vite, Ant Design, TanStack Query | Frontend development |


## 🏙️ Master Homes — Dubai Real Estate

Master Homes is a Dubai real-estate group with a property brokerage (Master Homes Properties) and a contracting arm
(Master Homes Contracting). The work below covers its full digital stack: a Django REST backend with a Go sync
service for the Property Finder portal, the public property website, an internal property-transactions tool, and a
series of campaign landing pages for off-plan launches with a small e-mail relay for lead delivery.

| Project | Description | Stack | Role |
|---------|-------------|-------|------|
| [MHP API](master-homes/mhp-api/) | REST backend for listings, off-plan projects, agents, lead forms and a property-transactions database | Python, Django, DRF, PostgreSQL, Redis, Celery, Docker | Full-Stack Developer |
| [MHP UI](master-homes/mhp-ui/) | Bilingual public website with property and project catalogue, maps and lead forms | Next.js, React, TypeScript, Tailwind CSS, TanStack Query, next-intl | Full-Stack Developer |
| [MHP CRM](master-homes/mhp-crm/) | Internal tool to search, filter, edit, import and export property-transaction records | React, TypeScript, Vite, Tailwind CSS, shadcn/ui, TanStack Query | Full-Stack Developer |
| [MHC UI](master-homes/mhc-ui/) | Marketing site for the group's contracting and fit-out services company | Next.js, React, TypeScript, Tailwind CSS, Framer Motion | Full-Stack Developer |
| [Off-Plan Landing](master-homes/off-plan-ui/) | API-driven landing page template for off-plan project campaigns | Next.js, React, TypeScript, Tailwind CSS, Leaflet | Full-Stack Developer |
| [PF Service](master-homes/pf-service/) | Go service syncing listings, agents and images from Property Finder | Go, GORM, PostgreSQL, Resty, Docker | Full-Stack Developer |
| [DAMAC Islands Landing](master-homes/damac-properties/) | Bilingual campaign page for the DAMAC Islands launch with lead capture | React, Vite, Sass, i18next, Nginx, Docker | Full-Stack Developer |
| [DAMAC Riverside Landing](master-homes/dubailand/) | Bilingual campaign page for DAMAC Riverside with floor plans and EOI forms | React, Vite, Sass, i18next, Nginx, Docker | Full-Stack Developer |
| [Fairmont Downtown Landing](master-homes/fairmont-downtown/) | Campaign page for a Fairmont-branded Downtown Dubai residence | React, Vite, Ant Design, Bootstrap, Sass, Nginx | Full-Stack Developer |
| [Dubai Island Landing](master-homes/dubai-island/) | Campaign page for Ellington Cove on Dubai Islands | React, Vite, Ant Design, Bootstrap, Sass, Nginx | Full-Stack Developer |
| [Ramhan Island Landing](master-homes/ramhan/) | Campaign page for a villa launch on Ramhan Island, Abu Dhabi | React, Vite, Sass, Nginx, Docker | Full-Stack Developer |
| [SMTP Service](master-homes/smtp-service/) | Minimal e-mail relay that delivers landing-page leads | Node.js, Express, Nodemailer, Docker | Full-Stack Developer |


## 🏢 IMZA — Dubai Real Estate Agency

IMZA (imza.ae) is a real-estate agency in Dubai, UAE. Its platform consists of a Django REST backend with a
bilingual admin panel for managing areas, developers, off-plan projects, properties, agents and a searchable
property-transactions dataset, and a Next.js public website that consumes that API. A separate CRM repository
has been created for internal agent workflows but has no code yet.

| Project | Description | Main stack | Role |
|---|---|---|---|
| [IMZA API](imza/imza-api/) | REST API and admin panel for listings, agents, PDF brochures, multi-currency prices and transactions search | Python, Django, Django REST Framework, PostgreSQL, Redis, Celery, Docker, GitLab CI | Backend development, API design, deployment |
| [IMZA Website (UI)](imza/imza-ui/) | Public agency website: services, areas, featured properties, team and contact form | Next.js, React, TypeScript, Tailwind CSS, Framer Motion, Axios, Docker | Frontend development, API integration |


## 🛰️ Edge24 — EdgeOps Platform

Edge24 is an EdgeOps platform for running and managing fleets of edge devices. It is built as three layers: a cloud
control plane (C++ API and React console), a lightweight on-device agent, and dedicated edge hardware (an SBC box with
UPS), together with a public marketing website. It is the successor of the earlier ioEdge product.

| Project | Description | Stack | Role |
|---|---|---|---|
| [Edge24 Cloud API](edge24/edge24-cloud-api/) | Control-plane backend managing edges, tunnels, containers, accounts and roles, with WebSocket links to agents | C++20, Drogon, WebSocket, JWT, WireGuard, CMake, Docker | Full-Stack Developer |
| [Edge24 Cloud Console](edge24/edge24-cloud-ui/) | Web console with topology map, live device stats, tunnels, containers and agent onboarding | React, TypeScript, Vite, Tailwind CSS, shadcn/ui, Leaflet, Zustand | Full-Stack Developer |
| [Edge24 Agent](edge24/edge24-agent-api/) | On-device agent that streams host health metrics to the cloud and executes commands (early stage) | C++20, Drogon, WebSocket, QUIC (lsquic), libserialport, CMake | Full-Stack Developer |
| [Edge24 Website](edge24/edge24-website/) | Marketing landing page presenting cloud, agent and hardware layers, pricing and FAQ | Next.js, React, TypeScript, Tailwind CSS, Framer Motion | Full-Stack Developer |


## 📡 ioEdge — Edge Device Management (v1)

ioEdge is an edge-computing management product that lets teams organise edge devices in a hierarchy, control who can
access them, and define the Docker services that run on each device. The v1 backend (Go) and web panel (React) were
the first implementation of the concept, later evolved into the Edge24 platform.

| Project | Description | Stack | Role |
|---|---|---|---|
| [ioEdge API (v1)](ioedge/ioedge-api-v1/) | Go backend with OTP/JWT auth, edge tree, role assignment and Docker service definitions over HTTP/2 and HTTP/3 | Go, SQLite, quic-go (HTTP/3), JWT, SMTP, Docker | Backend development |
| [ioEdge Panel (v1)](ioedge/ioedge-ui-v1/) | Web panel for edge hierarchy, map/topology views, roles, services and proxies | React, TypeScript, Vite, Tailwind CSS, shadcn/ui, Leaflet, Zustand | Frontend development |


## 🚗 Parking24 — Parking Management

Parking24 is a parking management platform covering parking permits, vehicle registries, payments and invoicing for
parking operators and drivers. The web dashboard combines map-based views of parking locations with real-time updates
and reporting/export tools.

| Project | Description | Stack | Role |
|---|---|---|---|
| [Parking24 Dashboard](parking24/parking24-ui/) | Real-time parking dashboard: permits, vehicles, watchlist, POS, invoices, payments and maps | React, TypeScript, Redux Toolkit, Ant Design, Sass, Yandex Maps, Leaflet, i18next, Docker | Frontend development |


## 🚆 Uzbekistan Railways

Projects built for Uzbekistan Railways, centred on the Bukhara Wagon (Carriage) Depot, which repairs freight wagons and maintains rolling stock. The work covers the depot's public bilingual website (Django REST backend plus Next.js frontend) and an AI workplace-safety service that detects missing safety helmets on camera feeds and identifies violators by face.

| Project | Description | Stack | Role |
|---------|-------------|-------|------|
| [VChD API](uzrailways/vchd-api/) | REST backend and admin panel for the Bukhara Wagon Depot website (services catalogue, multilingual content, contact form) | Python, Django, Django REST Framework, PostgreSQL, Docker, GitLab CI | Backend development, API design, deployment |
| [VChD UI](uzrailways/vchd-ui/) | Bilingual (Uzbek/Russian) corporate website for the Bukhara Wagon Depot | Next.js, React, Tailwind CSS, MUI, next-intl, Docker | Frontend development, i18n, API integration |
| [Helmet Detector](uzrailways/helmet-detector/) | Real-time helmet-compliance detection on IP cameras with face recognition and incident logging | Python, FastAPI, YOLOv8, DeepFace, PostgreSQL, pgvector, Docker, CUDA | Backend and ML integration, deployment |


## 📚 Nazar Education (nedu)

Nazar Education is an offline learning center in Chirchiq, Uzbekistan, preparing students for school exams, national certificates, IELTS and specialised schools. I am building its in-house management platform: a CRM + LMS + finance backend with a staff web panel, a teacher mobile app, a Telegram bot for passwordless login, and the public landing site that feeds leads into the CRM.

| Project | Description | Stack | Role |
|---|---|---|---|
| [Nazar Education — Backend](nedu/nedu-backend/) | CRM, academics, invoicing, cash desk and payroll REST API for an education center | Python, Django, DRF, PostgreSQL, Redis, Celery, Docker | Lead backend developer, architecture, CI/CD |
| [Nazar Education — Landing Website](nedu/nedu-website/) | SEO-optimised marketing site with a lead form wired into the CRM | Next.js, React, TypeScript, Radix UI, Docker | Front-end development, CRM integration |
| [Nazar Education — Administration Panel](nedu/nedu-administration/) | Role-aware staff panel for leads, finance, cash desk and payroll | React, TypeScript, Vite, Ant Design, Recharts | Front-end architecture and development |
| [Nazar Education — Teacher Mobile App](nedu/nedu-mobile-app/) | Flutter app for teachers: schedule, groups, attendance, salary | Flutter, Dart, Dio | Mobile development |
| [Nazar Education — Telegram Bot](nedu/nedu-telegram-bot/) | Bot that links Telegram accounts to phone numbers for OTP login | Python, aiogram, aiohttp, Docker | Bot design and implementation |


## 🦸 HeroAcademy

HeroAcademy is a language and test-prep academy (SAT, IELTS, General English). Its platform merges an online learning site with encrypted video lessons and tests, and an internal CRM and operations panel with lead-capture and telephony integrations. Two GitLab repositories hold the same monorepo (an earlier personal copy and the later organization copy), so they are documented as one project.

| Project | Description | Stack | Role |
|---|---|---|---|
| [HeroAcademy](hero-academy/heroacademy/) | Learning platform with protected HLS video and tests, plus a CRM / operations control panel | .NET 8, ASP.NET Core, EF Core, SignalR, Vue 3, TypeScript, Tailwind CSS, PostgreSQL, MinIO | Full-stack development |


## 🦷 MediaStom

MediaStom is a digital platform for a dental clinic in Uzbekistan. It replaces phone-and-notebook scheduling with online booking, digital patient cards with a tooth chart, automated SMS reminders and a waitlist that refills cancelled slots, all in one mobile-first Next.js application.

| Project | Description | Stack | Role |
|---|---|---|---|
| [MediaStom](mediastom/mediastom/) | Dental clinic booking, patient records and automated SMS reminder / waitlist platform | Next.js, React, TypeScript, Prisma, SQLite/Turso, Tailwind CSS | Full-stack development |


## 🤖 Telegram Bots

A set of Telegram bots and Telegram-account automations built for freelance clients and for personal use. They range from business-workflow bots (paid memberships, paid legal consultations, lead capture) to MTProto/Telegram Business tools that archive deleted messages or send away replies; all are written in Python and shipped as Docker containers via GitLab CI.

| Project | Description | Stack | Role |
|---------|-------------|-------|------|
| [Telegram Deleted Guard](telegram-bots/telegram-deleted-guard/) | Archives incoming private messages and alerts the owner with the saved copy when a sender deletes them | Python, Telethon, Telegram Bot API (Business), SQLite, Docker | Sole developer |
| [Telegram Auto-Reply](telegram-bots/telegram-autoreply/) | Away-message automation for a personal Telegram account based on inactivity, with per-contact cooldown | Python, Telethon, Docker | Sole developer (personal project) |
| [Royal Trade Bot](telegram-bots/royal-trade-bot/) | VIP-membership bot for a forex-trading community: receipt review, onboarding, subscription reminders, results gallery | Python, aiogram, Docker, GitLab CI | Freelance developer |
| [Legal Consultation Bot](telegram-bots/gulmira-bot/) | Paid lawyer Q&A bot: receipt approval, question routing and reply relay with request state tracking | Python, aiogram, SQLite, Docker | Freelance developer |
| [Clinic Assistant Bot](telegram-bots/doctor-odilbek-bot/) | Lead-capture and content-delivery bot for a medical practice with admin panel and broadcasts | Python, aiogram, Pydantic, Docker | Freelance developer |


## 🚧 In Setup

New products whose repositories have been created and are at the planning / initial-setup stage.
Detailed pages will be added once development is underway.

| Product | Client | Planned components |
| --- | --- | --- |
| Biznes Ayol ("Business Woman") | Agrobank — Mahallabay | Backend, web frontend, infrastructure |
| Agrokredit Web | Agrobank — Mahallabay | Customer web app for the [Agrokredit](agrobank/agrokredit-api/) credit platform |
| Agromakon Infra | Agrobank — Mahallabay | Deployment & CI/CD for [Agromakon](agrobank/agromakon-core/) |
| Enterprise Resource Planning | Agrobank — Mahallabay | Internal ERP for the department |
| StarSoft | StarSoft | Backend, web client, admin panel, AutoCAD component, plugin SDK |
| Bimuz | Bimuz education center | Core backend, admin UI, student UI |
| IMZA CRM | IMZA (Dubai) | CRM for the [IMZA](imza/imza-api/) real-estate platform |
| NeoSoft Admin Dashboard | Edu NeoSoft | Admin panel for the [Edu NeoSoft](edu-neosoft/edu-neosoft-api/) platform |
| Edge24 Assets | Edge24 | Shared brand & media assets |

---

## 🤝 Contact

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/dilshod-normurodov-0b886824b)
[![Telegram](https://img.shields.io/badge/Telegram-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white)](https://t.me/architect_developer)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/dilshod1405)
