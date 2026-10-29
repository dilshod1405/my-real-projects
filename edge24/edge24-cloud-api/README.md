# Edge24 Cloud API

> Control-plane backend of the Edge24 EdgeOps platform: manages a fleet of edge devices, their tunnels and containerized services from one place.

![Status](https://img.shields.io/badge/source-private%20(GitLab)-FC6D26?style=flat-square&logo=gitlab)
![C++20](https://img.shields.io/badge/C%2B%2B-20-00599C?style=flat-square&logo=cplusplus)
![Drogon](https://img.shields.io/badge/Drogon-framework-2E7D32?style=flat-square)
![CMake](https://img.shields.io/badge/CMake-build-064F8C?style=flat-square&logo=cmake)
![WebSocket](https://img.shields.io/badge/WebSocket-realtime-010101?style=flat-square)
![JWT](https://img.shields.io/badge/JWT-auth-000000?style=flat-square&logo=jsonwebtokens)
![WireGuard](https://img.shields.io/badge/WireGuard-tunnels-88171A?style=flat-square&logo=wireguard)
![Docker](https://img.shields.io/badge/Docker-container-2496ED?style=flat-square&logo=docker)

## Overview
Edge24 is a three-layer edge computing product (cloud control plane, on-device agent, edge hardware).
This repository is the **cloud control plane**: a high-performance C++ server that exposes a REST API for the
web console ([edge24-cloud-ui](../edge24-cloud-ui/)) and keeps a persistent WebSocket channel to every device agent
([edge24-agent-api](../edge24-agent-api/)). It is the successor of the earlier ioEdge backend ([ioedge-api-v1](../../ioedge/ioedge-api-v1/)).

## Key Features
- Account management with registration, login and email one-time-password (OTP) verification
- Role-based access: users can be granted roles on specific edges
- Edge device CRUD and lifecycle (create, update, delete, remote reboot)
- Live edge statistics (CPU, memory, disk, network) pushed by agents over WebSocket
- Secure tunnel management per edge, with per-tunnel status and statistics
- Container / service management on edge devices (start, stop, restart, update)
- Offline-tolerant design: changes are applied when an edge reconnects
- Automatic WireGuard peer provisioning during the edge lifecycle
- JWT-protected HTTP API with request filters; SMTP mail plugin for notifications

## Architecture
The server is organised in the Drogon style: HTTP controllers (Account, Role, Edge, Tunnel, Container), a WebSocket
controller for agents, ORM models, request filters and long-lived plugins (edge session registry, OTP, SMTP).

```mermaid
flowchart LR
    UI[Cloud web console] -- REST / JWT --> API[Cloud API]
    API -- ORM --> DB[(Relational DB)]
    API -- SMTP --> Mail[Mail server]
    Agent1[Edge agent] <-- WebSocket --> API
    Agent2[Edge agent] <-- WebSocket --> API
    API -. WireGuard peers .-> Net[Tunnel network]
```

## Tech Stack
| Layer | Technologies |
|---|---|
| Language | C++20 |
| Framework | Drogon (HTTP, WebSocket, ORM, plugins) |
| Auth | JWT (jwt-cpp), email OTP |
| Networking | WebSocket, WireGuard, libcurl |
| Build | CMake |
| Delivery | Docker, GitLab CI |

## My Role
**Full-Stack Developer** — API development and the web console that consumes it; aligned the API contract with the earlier ioEdge backend and panel I built.

## 🔒 Source Code Access
The source code of this project is kept in a **private GitLab repository** (client / commercial project).
It is not published here. On request, I can walk through the codebase, architecture and live demo
in a **separate video call** for discussion.
