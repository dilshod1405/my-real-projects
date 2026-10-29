# Monitoring Telegram Bot

> Telegram bot for Agrobank Mahallabay staff to submit field-monitoring reports from mahallas – location, assessment and photos – and to fill in low-income family survey forms with an e-signature step.

![Status](https://img.shields.io/badge/source-private%20(GitLab)-FC6D26?style=flat-square&logo=gitlab)
![Python](https://img.shields.io/badge/Python-3.11-3776AB?style=flat-square&logo=python&logoColor=white)
![aiogram](https://img.shields.io/badge/aiogram-3-26A5E4?style=flat-square&logo=telegram&logoColor=white)
![aiohttp](https://img.shields.io/badge/aiohttp-2C5BB4?style=flat-square&logo=aiohttp&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)

## Overview
A lightweight data-collection channel of the Mahallabay collaboration platform for staff who work from Telegram
rather than the [mobile app](../agro-mahalla-mobile/). Employees log in with their phone number, which is verified
against staff records in the [Collaboration API](../collaboration-api/); depending on their permissions they get a
menu for regional monitoring visits and/or the low-income family survey. All submitted data goes straight to the
API, where it appears in the [dashboard](../collaboration-dashboard/).

## Key Features
- **Phone-based login** with ownership check of the shared contact and permission-based menus.
- **Persistent sessions** stored in Redis, with restore on `/start`, logout and cancel at any step.
- **Monitoring visit flow**: cascading region → district → mahalla selection with paging, live location capture,
  suitability assessment, optional multi-photo upload and a confirmation summary before submission.
- **Low-income family survey**: guided multi-step questionnaire (family selection, status, yes/no questions, visit
  date validation, photos).
- **E-signature via Telegram Web App**: a signing page opens inside Telegram, linked to a short-lived signing session.
- **Active-user middleware** that re-checks access on each update.
- **Docker image** and GitLab CI deployment.

## Architecture
```mermaid
flowchart LR
    Staff[Staff on Telegram] --> Bot[Monitoring bot - aiogram]
    Bot --> Redis[(Redis sessions)]
    Bot -- REST --> API[Collaboration API]
    Bot --> WebApp[Signature Web App]
    WebApp --> API
```

## Tech Stack
| Layer | Technologies |
|-------|--------------|
| Bot framework | Python, aiogram 3 (FSM, routers, middleware, inline keyboards) |
| Web | aiohttp, Telegram Web App (HTML signing page) |
| Session storage | Redis |
| Integrations | Collaboration API (REST) |
| Delivery | Docker, GitLab CI/CD |

## My Role
Bot development and integration with the platform API: conversation flows, session handling, signing web app and
deployment.

## 🔒 Source Code Access
The source code of this project is kept in a **private GitLab repository** (client / commercial project).
It is not published here. On request, I can walk through the codebase, architecture and live demo
in a **separate video call** for discussion.
