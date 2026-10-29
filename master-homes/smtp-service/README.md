# SMTP Service

> Small e-mail relay microservice that lets static landing pages send lead notifications without exposing mail credentials in the browser.

![Status](https://img.shields.io/badge/source-private%20(GitLab)-FC6D26?style=flat-square&logo=gitlab)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white)
![Express](https://img.shields.io/badge/Express-4-000000?style=flat-square&logo=express&logoColor=white)
![Nodemailer](https://img.shields.io/badge/Nodemailer-6-22B573?style=flat-square)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![GitLab CI](https://img.shields.io/badge/GitLab%20CI-FC6D26?style=flat-square&logo=gitlab&logoColor=white)

## Overview
The Master Homes campaign pages ([damac-properties](../damac-properties/), [dubailand](../dubailand/),
[fairmont-downtown](../fairmont-downtown/) and others) are static React builds with no backend of their own. This
service gives them a single HTTP endpoint for sending lead e-mails; SMTP settings are kept on the server side in
environment variables. It is intentionally minimal (one source file).

## Key Features
- One JSON `POST` endpoint that accepts sender, recipient, subject and text
- Validation of required fields with clear 400 responses
- SMTP delivery through Nodemailer, configured fully via environment variables (host, port, TLS, credentials)
- CORS enabled for browser-based landing pages
- Containerised with Docker and built by GitLab CI

## Architecture
```mermaid
flowchart LR
    L1[Landing page] --> Relay[SMTP relay service]
    L2[Landing page] --> Relay
    Relay --> SMTP[Mail server]
    SMTP --> Sales[Sales mailbox]
```

## Tech Stack
| Layer | Technologies |
|-------|--------------|
| Runtime | Node.js, Express 4 |
| Mail | Nodemailer |
| Middleware | cors, body-parser |
| Delivery | Docker, GitLab CI |

## My Role
**Full-Stack Developer** — development and deployment of the relay service.

## 🔒 Source Code Access
The source code of this project is kept in a **private GitLab repository** (client / commercial project).
It is not published here. On request, I can walk through the codebase, architecture and live demo
in a **separate video call** for discussion.
