# Edge24 Cloud Console

> Web console for operating an Edge24 device fleet: topology map, live device stats, tunnels, containers and agent onboarding.

![Status](https://img.shields.io/badge/source-private%20(GitLab)-FC6D26?style=flat-square&logo=gitlab)
![React](https://img.shields.io/badge/React-19-61DAFB?style=flat-square&logo=react&logoColor=black)
![TypeScript](https://img.shields.io/badge/TypeScript-5-3178C6?style=flat-square&logo=typescript&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-7-646CFF?style=flat-square&logo=vite&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind-4-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white)
![shadcn/ui](https://img.shields.io/badge/shadcn%2Fui-components-000000?style=flat-square)
![Leaflet](https://img.shields.io/badge/Leaflet-maps-199900?style=flat-square&logo=leaflet)
![Zustand](https://img.shields.io/badge/Zustand-state-443E38?style=flat-square)

## Overview
The single-page web application of the Edge24 platform. Operators sign in, see their edge devices on a map/topology
view, inspect real-time health, and manage tunnels and containerized services. It talks to the
[Edge24 Cloud API](../edge24-cloud-api/) and evolved from the earlier [ioEdge panel](../../ioedge/ioedge-ui-v1/).

## Key Features
- Sign-up and login with email OTP verification
- Geographic topology map of edges (Leaflet) with status pulse indicators and "last seen" labels
- Edge selector with hierarchical (tree) navigation
- Edge statistics panel with charts (CPU, memory, disk, network)
- Remote edge reboot
- Tunnel management panel
- Container / service management panel
- Agent registration panel guiding installation of the device agent
- Account and role management, light/dark theme

## Architecture
```mermaid
flowchart LR
    User[Operator browser] --> SPA[React SPA]
    SPA -- Axios / JWT --> API[Edge24 Cloud API]
    SPA --> Store[Zustand auth store]
    SPA --> Map[Leaflet topology map]
```

## Tech Stack
| Layer | Technologies |
|---|---|
| UI | React 19, TypeScript, shadcn/ui, Radix UI, Tailwind CSS 4 |
| State / data | Zustand, Axios, polling hooks |
| Visualisation | Leaflet / React-Leaflet, Recharts, React Flow, xterm |
| Tooling | Vite 7, ESLint, Prettier, pnpm |
| Delivery | Docker, docker-compose, GitLab CI |

## My Role
**Full-Stack Developer** — the console builds on the ioEdge panel codebase I started (layout, auth flow, edge tree, map view), connected to the Edge24 cloud API.

## 🔒 Source Code Access
The source code of this project is kept in a **private GitLab repository** (client / commercial project).
It is not published here. On request, I can walk through the codebase, architecture and live demo
in a **separate video call** for discussion.
