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

**Latest release / Последний релиз:** `release-0.1.0-0.1.0` (MasonicCore `v0.1.0` + MasonicSkin `v0.1.0`)

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
- [`masoniclounge/MasonicCore`](https://github.com/masoniclounge/MasonicCore) — Go REST API
- [`masoniclounge/MasonicSkin`](https://github.com/masoniclounge/MasonicSkin) — Lit.js application
- [`masoniclounge/release`](https://github.com/masoniclounge/release) — Docker Compose release assembly (pulls tagged images from ghcr.io)
- This profile repository — organization overview

**RU**
- [`masoniclounge/MasonicCore`](https://github.com/masoniclounge/MasonicCore) — Go REST API
- [`masoniclounge/MasonicSkin`](https://github.com/masoniclounge/MasonicSkin) — приложение на Lit.js
- [`masoniclounge/release`](https://github.com/masoniclounge/release) — сборочный Docker Compose релиз (подтягивает тегированные образы из ghcr.io)
- Этот репозиторий профиля — обзор организации

---

## Roadmap / Дорожная карта

**EN**

| # | Milestone / Веха | Status / Статус |
|---|------------------|-----------------|
| 1 | Planning & project memory | ✅ Done |
| 2 | Backend skeleton (Go: chi, pgx, goose, config, healthcheck) | ✅ Done |
| 3 | Backend auth — registration, login, JWT, roles | ✅ Done |
| 4 | Backend core CRUD — groups → threads → posts | ✅ Done |
| 5 | Backend S3 — avatars & attachments (MinIO) | ✅ Done |
| 6 | Backend WebSocket — PMs, notifications, presence | ✅ Done |
| 7 | Frontend skeleton (Vite + TS + Lit, themes, routing, icons) | ✅ Done |
| 8 | Frontend public pages — forums, threads, posts, profile | ✅ Done |
| 9 | Frontend install wizard `/install` | ✅ Done |
| 10 | Frontend admin panel — groups, users, roles, settings, media | ✅ Done |
| 11 | Release assembly — docker-compose, env, volumes, healthchecks | ✅ Done |
| 12 | CI workflows — backend/frontend → ghcr.io | ✅ Done |
| 13 | Polish — tests, docs, license, dev bootstrap | ✅ Done |
| 14 | First release — MasonicCore `v0.1.0`, MasonicSkin `v0.1.0` | ✅ Done |

**Next / Дальше:** push component tags to GitHub → CI publishes images to ghcr.io → announce the project.

**RU**

| # | Веха | Статус |
|---|------|--------|
| 1 | Планирование и память проекта | ✅ Готово |
| 2 | Скелет бэкенда (Go: chi, pgx, goose, конфиг, healthcheck) | ✅ Готово |
| 3 | Аутентификация бэкенда — регистрация, логин, JWT, роли | ✅ Готово |
| 4 | Ключевой CRUD бэкенда — группы → темы → посты | ✅ Готово |
| 5 | S3 бэкенда — аватарки и вложения (MinIO) | ✅ Готово |
| 6 | WebSocket бэкенда — ЛС, уведомления, присутствие | ✅ Готово |
| 7 | Скелет фронтенда (Vite + TS + Lit, темы, роутинг, иконки) | ✅ Готово |
| 8 | Публичные страницы фронтенда — форумы, темы, посты, профиль | ✅ Готово |
| 9 | Мастер установки фронтенда `/install` | ✅ Готово |
| 10 | Админка фронтенда — группы, пользователи, роли, настройки, медиа | ✅ Готово |
| 11 | Сборочный релиз — docker-compose, env, volumes, healthchecks | ✅ Готово |
| 12 | CI-пайплайны — backend/frontend → ghcr.io | ✅ Готово |
| 13 | Полировка — тесты, доки, лицензия, dev-запуск | ✅ Готово |
| 14 | Первый релиз — MasonicCore `v0.1.0`, MasonicSkin `v0.1.0` | ✅ Готово |

**Дальше:** пуш тегов компонентов на GitHub → CI публикует образы в ghcr.io → анонс проекта.

---

## Commit Activity / Активность коммитов

**EN**
Live organization activity timeline (powered by GitHub API via github-profile-summary-cards).

**RU**
Живой таймлайн активности организации (на основе GitHub API через github-profile-summary-cards).

[![Organization activity](https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=masoniclounge&type=organization)](https://github.com/masoniclounge)

---

## Contributors / Контрибьюторы

[![Contributors MasonicCore](https://img.shields.io/github/contributors/masoniclounge/MasonicCore)](https://github.com/masoniclounge/MasonicCore/graphs/contributors)
[![Contributors MasonicSkin](https://img.shields.io/github/contributors/masoniclounge/MasonicSkin)](https://github.com/masoniclounge/MasonicSkin/graphs/contributors)
[![Contributors release](https://img.shields.io/github/contributors/masoniclounge/release)](https://github.com/masoniclounge/release/graphs/contributors)

**EN**
Interested in contributing? Open an issue in the relevant repository or submit a pull request. Every change follows the project's conventions (bilingual changelog, per-repo commits, explicit SQL, no ORM).

**RU**
Хотите поучаствовать? Откройте issue в соответствующем репозитории или отправьте pull request. Каждое изменение следует конвенциям проекта (двуязычный changelog, коммиты по репозиториям, явный SQL, без ORM).

---

## License / Лицензия

**EN**
GPL v3.0 — copyleft license. All derivative works and distributions must be released under the same license. The `LICENSE` file is published in each repository (MasonicCore, MasonicSkin, release).

**RU**
GPL v3.0 — лицензия с копилефтом. Все производные работы и распространения должны публиковаться под той же лицензией. Файл `LICENSE` опубликован в каждом репозитории (MasonicCore, MasonicSkin, release).
