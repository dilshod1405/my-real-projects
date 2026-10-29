# Legal Consultation Bot (gulmira-bot)

> Telegram bot for a practising lawyer that sells paid consultations: clients pay, upload a receipt, ask their question and receive the lawyer's answer — all inside Telegram.

![Status](https://img.shields.io/badge/source-private%20(GitLab)-FC6D26?style=flat-square&logo=gitlab)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![aiogram](https://img.shields.io/badge/aiogram-3-2CA5E0?style=flat-square&logo=telegram&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=flat-square&logo=sqlite&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![GitLab CI](https://img.shields.io/badge/GitLab%20CI-FC6D26?style=flat-square&logo=gitlab&logoColor=white)

## Overview
An independent lawyer wanted to offer paid Q&A consultations without managing payments and questions across scattered chats. This bot acts as a structured intermediary between clients and the lawyer: it enforces "pay first, then ask", routes receipts and questions to the lawyer, and relays the lawyer's replies back to the right client while keeping the lawyer's personal account private. Built in 2026.

## Key Features
- **Request lifecycle state machine** — each client request moves through *waiting for receipt check → approved → in progress → completed* (or *rejected*), persisted in SQLite.
- **Payment receipt intake** — photo or PDF receipts (PDF detected by MIME type or file extension) forwarded to the lawyer with inline Approve / Reject buttons.
- **Status-aware guidance** — clients get context-specific instructions depending on where their request is (payment instructions, pending check, question already sent, etc.).
- **Question routing** — once payment is approved, the client's text question is delivered to the lawyer with a request reference.
- **Reply relay** — the lawyer simply replies to the forwarded question; the bot copies the answer (text or media) back to the correct client and closes the request.
- **Lawyer-side status captions** — approved / rejected marks appended to receipt messages, buttons removed after a decision.
- **Robust error handling** for blocked or unreachable chats without corrupting request state.
- **Docker image** built and published through GitLab CI.

## Architecture
```mermaid
flowchart LR
    Client[Client] -->|receipt / question| Bot[aiogram bot]
    Bot -->|forward + buttons| Lawyer[Lawyer]
    Lawyer -->|approve / reply| Bot
    Bot -->|status / answer| Client
    Bot --> DB[(SQLite: users, requests, message links)]
```

## Tech Stack
| Layer | Technologies |
|-------|--------------|
| Language | Python |
| Bot framework | aiogram 3 |
| Storage | SQLite |
| Config | python-dotenv |
| DevOps | Docker, Docker Compose, GitLab CI/CD |

## My Role
Freelance development for the client: workflow design, bot implementation, data model, deployment.

## 🔒 Source Code Access
The source code of this project is kept in a **private GitLab repository** (client / commercial project).
It is not published here. On request, I can walk through the codebase, architecture and live demo
in a **separate video call** for discussion.
