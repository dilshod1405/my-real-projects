# ioEdge Panel (v1)

> Web panel for managing edge devices: sign-in, an edge hierarchy with map/topology views, roles, services and proxies.

![Status](https://img.shields.io/badge/source-private%20(GitLab)-FC6D26?style=flat-square&logo=gitlab)
![React](https://img.shields.io/badge/React-19-61DAFB?style=flat-square&logo=react&logoColor=black)
![TypeScript](https://img.shields.io/badge/TypeScript-5-3178C6?style=flat-square&logo=typescript&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-7-646CFF?style=flat-square&logo=vite&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind-4-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white)
![shadcn/ui](https://img.shields.io/badge/shadcn%2Fui-components-000000?style=flat-square)
![Leaflet](https://img.shields.io/badge/Leaflet-maps-199900?style=flat-square&logo=leaflet)

## Overview
Single-page frontend for the ioEdge product, consuming the [ioEdge API](../ioedge-api-v1/). Operators manage a tree of
edge devices, who has access to them, and which containerized services run on each. This codebase later became the
foundation of the [Edge24 Cloud Console](../../edge24/edge24-cloud-ui/).

## Key Features
- Sign-up and login with OTP code input
- Edge selector with hierarchical tree navigation
- Topology and geographic map views of edges (Leaflet, React Flow)
- Edge create/edit with role assignment to users
- Service management per edge (Docker image, registry, ports, environment, volumes)
- Proxy / port-forwarding entries per edge
- Embedded file manager and terminal components (xterm) for edge interaction
- Light/dark theme, shadcn/ui component system

## Tech Stack
| Layer | Technologies |
|---|---|
| UI | React 19, TypeScript, shadcn/ui, Radix UI, Tailwind CSS 4 |
| State / data | Zustand, Axios |
| Visualisation | Leaflet / React-Leaflet, React Flow, Recharts, xterm |
| Tooling | Vite 7, ESLint, Prettier, pnpm |
| Delivery | Docker, docker-compose, GitLab CI |

## My Role
Frontend development: initial project setup, authentication flow, edge tree and map views, API integration.

## 🔒 Source Code Access
The source code of this project is kept in a **private GitLab repository** (client / commercial project).
It is not published here. On request, I can walk through the codebase, architecture and live demo
in a **separate video call** for discussion.
