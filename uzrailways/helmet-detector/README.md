# Helmet Detector

> AI-powered video analytics service that detects workers without safety helmets on live IP-camera feeds, identifies them by face and logs safety incidents.

![Status](https://img.shields.io/badge/source-private%20(GitLab)-FC6D26?style=flat-square&logo=gitlab)
![Python](https://img.shields.io/badge/Python-3.12-3776AB?style=flat-square&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![YOLOv8](https://img.shields.io/badge/YOLOv8-Ultralytics-111F68?style=flat-square)
![DeepFace](https://img.shields.io/badge/DeepFace-face%20recognition-FF6F00?style=flat-square)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-pgvector-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![CUDA](https://img.shields.io/badge/NVIDIA-CUDA-76B900?style=flat-square&logo=nvidia&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)

## Overview
In railway repair depots, hard-hat compliance is a core workplace-safety requirement, but manual monitoring of every work area is impractical. This backend service consumes live IP-camera streams, runs object detection to find people and helmets, and when someone is not wearing a helmet it crops the face, matches it against the employee database and records an incident with a snapshot. It was built in summer 2025 for Uzbekistan Railways alongside the depot website ([vchd-api](../vchd-api/), [vchd-ui](../vchd-ui/)).

## Key Features
- **Real-time stream processing** of multiple IP cameras, each managed independently (add, start, stop, start-all-active, status).
- **Person and helmet detection** with a YOLOv8 model.
- **Face recognition** of violators using DeepFace, with employee face embeddings stored in PostgreSQL via pgvector.
- **Incident logging** — time, matched employee, camera location and saved evidence image.
- **Employee synchronisation** — scheduled / on-demand import of employee photos from an external HR API and embedding generation (APScheduler + httpx).
- **REST API** for cameras, employees and incidents, intended for an admin dashboard.
- **GPU acceleration** on NVIDIA GPUs (CUDA / cuDNN, NVIDIA Container Toolkit) with a CPU fallback mode for local development.
- **Database migrations** with Alembic; tests directory and Docker Compose setup for deployment.

## Architecture
```mermaid
flowchart LR
    Cams[IP cameras] --> CM[Camera manager]
    CM --> YOLO[YOLOv8 person / helmet detection]
    YOLO -->|no helmet| FR[DeepFace face recognition]
    FR --> DB[(PostgreSQL + pgvector)]
    FR --> Img[(Incident snapshots)]
    HR[External employee API] --> Sync[Employee sync job]
    Sync --> DB
    API[FastAPI REST API] --> DB
    API --> CM
    Admin[Admin dashboard] --> API
```

## Tech Stack
| Layer | Technologies |
|-------|--------------|
| Language | Python 3.12 |
| API | FastAPI, Gunicorn / Uvicorn |
| Computer vision | Ultralytics YOLOv8, DeepFace, ffmpeg |
| Data | PostgreSQL, pgvector, SQLAlchemy, Alembic |
| Background jobs | APScheduler, httpx |
| Infrastructure | Docker, Docker Compose, NVIDIA CUDA / cuDNN, GitLab CI/CD |

## My Role
Full backend and ML integration: video pipeline design, model integration (detection and face recognition), database and vector storage, REST API, employee data synchronisation, GPU-enabled containerised deployment.

## 🔒 Source Code Access
The source code of this project is kept in a **private GitLab repository** (client / commercial project).
It is not published here. On request, I can walk through the codebase, architecture and live demo
in a **separate video call** for discussion.
