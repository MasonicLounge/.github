<div align="center">

<img src="logo.png" alt="Masonic Lounge logo" width="160" />

# Masonic Lounge

**Open-source forum engine — self-hosted platform for building internet forums**

**Движок интернет-форумов с открытым исходным кодом — самодостаточная платформа для создания форумов**

[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)

</div>

---

## About / О проекте

**EN**
Masonic Lounge is a self-hostable, open-source engine for creating internet forums. It ships as a Docker Compose stack: Go API, Lit.js frontend, PostgreSQL 16 and MinIO (S3) storage. It includes an install wizard, a web-based admin panel, per-component versioning, automated DB migrations and a clean, themeable UI.

**RU**
Masonic Lounge — самодостаточный движок интернет-форумов с открытым исходным кодом. Поставляется как стек Docker Compose: Go API, фронтенд на Lit.js, PostgreSQL 16 и хранилище MinIO (S3). Включает мастер установки, веб-админку, независимое версионирование компонентов, автоматические миграции БД и чистый настраиваемый интерфейс.

---

## Features / Возможности

**EN**
- Forums organized in categories (groups → threads → posts)
- User system: registration, JWT auth (access + refresh), roles
- S3 media storage (avatars, attachments) via MinIO
- Realtime: private messages, notifications, presence over WebSocket
- Install wizard on first boot (`/install`)
- Admin panel: groups, users, roles, settings, media, version & changelog
- Light & dark themes, design tokens, inline SVG icon set
- i18n with Crowdin-compatible templates (source: English)
- Automated goose DB migrations; independent versioning per component
- Docker Compose distribution with healthchecks

**RU**
- Форум, организованный по категориям (группы → темы → посты)
- Пользователи: регистрация, JWT-аутентификация (access + refresh), роли
- S3-хранилище медиа (аватарки, вложения) через MinIO
- Realtime: личные сообщения, уведомления, присутствие через WebSocket
- Мастер установки при первом запуске (`/install`)
- Админка: группы, пользователи, роли, настройки, медиа, версия и changelog
- Светлая и тёмная темы, дизайн-токены, инлайновые SVG-иконки
- i18n с шаблонами, совместимыми с Crowdin (исходный язык: английский)
- Автоматические миграции БД (goose); независимое версионирование компонентов
- Дистрибуция через Docker Compose с healthchecks

---

## Tech Stack / Стек

| Layer / Слой | Technology / Технология |
|--------------|--------------------------|
| Orchestration / Оркестрация | Docker + docker-compose |
| Database / СУБД | PostgreSQL 16 |
| Media storage / Хранилище медиа | MinIO (S3-compatible) |
| Backend / Бэкенд | Go: `chi`, `pgx` (explicit SQL, no ORM), `goose`, JWT (argon2id), `minio-go`, WebSocket |
| Frontend / Фронтенд | Lit.js + TypeScript + Vite, `@vaadin/router`, inline SVG icons |
| Realtime | WebSocket (PMs, notifications, presence) |
| CI/CD | GitHub Actions → ghcr.io |
| i18n | Crowdin-compatible JSON/ICU templates |

---

## Repositories / Репозитории

**EN**
- [`masoniclounge/backend`](https://github.com/masoniclounge/backend) — Go REST API
- [`masoniclounge/frontend`](https://github.com/masoniclounge/frontend) — Lit.js application
- [`masoniclounge/release`](https://github.com/masoniclounge/release) — Docker Compose release assembly (pulls tagged images from ghcr.io)
- This profile repository — organization overview

**RU**
- [`masoniclounge/backend`](https://github.com/masoniclounge/backend) — Go REST API
- [`masoniclounge/frontend`](https://github.com/masoniclounge/frontend) — приложение на Lit.js
- [`masoniclounge/release`](https://github.com/masoniclounge/release) — сборочный Docker Compose релиз (подтягивает тегированные образы из ghcr.io)
- Этот репозиторий профиля — обзор организации

---

## Roadmap / Дорожная карта

**EN**

| # | Milestone / Веха | Status / Статус |
|---|------------------|-----------------|
| 1 | Planning & project memory | ✅ Done |
| 2 | Backend skeleton (Go: chi, pgx, goose, config, healthcheck) | ⬜ Next |
| 3 | Backend auth — registration, login, JWT, roles | ⬜ |
| 4 | Backend core CRUD — groups → threads → posts | ⬜ |
| 5 | Backend S3 — avatars & attachments (MinIO) | ⬜ |
| 6 | Backend WebSocket — PMs, notifications, presence | ⬜ |
| 7 | Frontend skeleton (Vite + TS + Lit, themes, routing, icons) | ⬜ |
| 8 | Frontend public pages — forums, threads, posts, profile | ⬜ |
| 9 | Frontend install wizard `/install` | ⬜ |
| 10 | Frontend admin panel — groups, users, roles, settings, media | ⬜ |
| 11 | Release assembly — docker-compose, env, volumes, healthchecks | ⬜ |
| 12 | CI workflows — backend/frontend → ghcr.io | ⬜ |
| 13 | Polish — tests, docs, license, dev bootstrap | ⬜ |

**RU**

| # | Веха | Статус |
|---|------|--------|
| 1 | Планирование и память проекта | ✅ Готово |
| 2 | Скелет бэкенда (Go: chi, pgx, goose, конфиг, healthcheck) | ⬜ Следующий |
| 3 | Аутентификация бэкенда — регистрация, логин, JWT, роли | ⬜ |
| 4 | Ключевой CRUD бэкенда — группы → темы → посты | ⬜ |
| 5 | S3 бэкенда — аватарки и вложения (MinIO) | ⬜ |
| 6 | WebSocket бэкенда — ЛС, уведомления, присутствие | ⬜ |
| 7 | Скелет фронтенда (Vite + TS + Lit, темы, роутинг, иконки) | ⬜ |
| 8 | Публичные страницы фронтенда — форумы, темы, посты, профиль | ⬜ |
| 9 | Мастер установки фронтенда `/install` | ⬜ |
| 10 | Админка фронтенда — группы, пользователи, роли, настройки, медиа | ⬜ |
| 11 | Сборочный релиз — docker-compose, env, volumes, healthchecks | ⬜ |
| 12 | CI-пайплайны — backend/frontend → ghcr.io | ⬜ |
| 13 | Полировка — тесты, доки, лицензия, dev-запуск | ⬜ |

---

## Commit Activity / Активность коммитов

**EN**
Live commit & contribution activity for the organization (powered by GitHub API):

**RU**
Активность коммитов и вклад в организацию в реальном времени (на основе GitHub API):

[![GitHub activity graph](https://github-readme-activity-graph.cyclic.app/graph?username=masoniclounge&theme=react&hide_border=true&area=true)](https://github.com/masoniclounge)

[![GitHub contributions](https://ghchart.rshah.org/masoniclounge)](https://github.com/masoniclounge)

---

## Contributors / Контрибьюторы

**EN**
Interested in contributing? Open an issue in the relevant repository or submit a pull request. Every change follows the project's conventions (bilingual changelog, per-repo commits, explicit SQL, no ORM).

**RU**
Хотите поучаствовать? Откройте issue в соответствующем репозитории или отправьте pull request. Каждое изменение следует конвенциям проекта (двуязычный changelog, коммиты по репозиториям, явный SQL, без ORM).

---

## License / Лицензия

**EN**
GPL v3.0 — copyleft license. All derivative works and distributions must be released under the same license. License text will be published in each repository once initialized.

**RU**
GPL v3.0 — лицензия с копилефтом. Все производные работы и распространения должны публиковаться под той же лицензией. Текст лицензии будет опубликован в каждом репозитории после их инициализации.