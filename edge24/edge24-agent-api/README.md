# Edge24 Agent

> Lightweight on-device agent for Edge24 edge appliances: reports host health to the cloud and executes control commands.

![Status](https://img.shields.io/badge/source-private%20(GitLab)-FC6D26?style=flat-square&logo=gitlab)
![C++20](https://img.shields.io/badge/C%2B%2B-20-00599C?style=flat-square&logo=cplusplus)
![Drogon](https://img.shields.io/badge/Drogon-framework-2E7D32?style=flat-square)
![QUIC](https://img.shields.io/badge/QUIC-lsquic-4B32C3?style=flat-square)
![WebSocket](https://img.shields.io/badge/WebSocket-client-010101?style=flat-square)
![CMake](https://img.shields.io/badge/CMake-build-064F8C?style=flat-square&logo=cmake)
![Linux](https://img.shields.io/badge/Linux-edge-FCC624?style=flat-square&logo=linux&logoColor=black)

## Overview
The agent is the **data-plane** component of Edge24. It runs on each edge device (single-board computer inside the
Edge24 box), opens an authenticated WebSocket connection to the [Edge24 Cloud API](../edge24-cloud-api/), and streams
device statistics while receiving commands such as configuration updates. The project is in an early stage of development.

## Key Features
- Persistent, authenticated WebSocket client connection to the cloud control plane
- System monitor collecting host info (OS, kernel, architecture, uptime, load averages)
- CPU usage, RAM / swap, process count
- Disk capacity, inode usage and per-second disk read/write rates
- Per-second network RX/TX throughput
- Command protocol for edge updates and statistics reporting
- Experimental QUIC server (lsquic) and serial-port support for attached hardware

## Architecture
```mermaid
flowchart LR
    HW[Host OS / hardware] --> Mon[System monitor]
    Mon --> Agent[Agent plugin]
    Agent <-- WebSocket --> Cloud[Edge24 Cloud API]
    Agent -. serial / QUIC .-> Dev[Local devices]
```

## Tech Stack
| Layer | Technologies |
|---|---|
| Language | C++20 |
| Framework | Drogon (plugins, WebSocket client) |
| Transport | WebSocket, QUIC (lsquic), OpenSSL |
| Hardware I/O | libserialport |
| Build / Delivery | CMake, Docker, GitLab CI |

## My Role
Member of the Edge24 product team (platform context and integration with the web console that displays agent statistics).

## 🔒 Source Code Access
The source code of this project is kept in a **private GitLab repository** (client / commercial project).
It is not published here. On request, I can walk through the codebase, architecture and live demo
in a **separate video call** for discussion.
