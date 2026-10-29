# Nazar Education — Teacher Mobile App

> Flutter app that gives teachers of the Nazar Education center their schedule, groups, attendance and salary on their phone.

![Status](https://img.shields.io/badge/source-private%20(GitLab)-FC6D26?style=flat-square&logo=gitlab)
![Flutter](https://img.shields.io/badge/Flutter-02569B?style=flat-square&logo=flutter&logoColor=white)
![Dart](https://img.shields.io/badge/Dart-3-0175C2?style=flat-square&logo=dart&logoColor=white)
![Dio](https://img.shields.io/badge/Dio-HTTP-0175C2?style=flat-square)
![Android](https://img.shields.io/badge/Android-3DDC84?style=flat-square&logo=android&logoColor=white)
![iOS](https://img.shields.io/badge/iOS-000000?style=flat-square&logo=apple&logoColor=white)

## Overview
A cross-platform (Android / iOS) mobile client of the Nazar Education system, currently focused on the teacher workflow. It talks to the same REST API as the staff web panel ([../nedu-backend/](../nedu-backend/), [../nedu-administration/](../nedu-administration/)) and uses the same Telegram-based login ([../nedu-telegram-bot/](../nedu-telegram-bot/)). The project is in active, early development.

## Key Features
- Phone-number login with a Telegram one-time code; tokens kept in secure device storage.
- Role-aware app shell and navigation.
- Teacher home screen with summary stats and today's lessons on a day timeline.
- Weekly calendar and weekly overview of the teaching schedule.
- Group list and per-group student lists with quick contact actions (call / message).
- Attendance marking for a lesson.
- "My salary" screen.
- Loading skeletons, error views and a lightweight request cache.

## Tech Stack
| Layer | Technologies |
|---|---|
| Framework | Flutter, Dart 3, Material Design |
| Networking | Dio |
| Storage | flutter_secure_storage |
| Other | url_launcher, GitLab CI |

## My Role
Mobile development: app structure, authentication flow and API integration, teacher-facing screens.

## 🔒 Source Code Access
The source code of this project is kept in a **private GitLab repository** (client / commercial project).
It is not published here. On request, I can walk through the codebase, architecture and live demo
in a **separate video call** for discussion.
