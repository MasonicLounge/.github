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

| Version | Description | Status |
|---------|-------------|--------|
| **v0.1.0** | First release — full backend API (auth, CRUD, S3, WebSocket, admin, install wizard), frontend SPA (forum pages, auth, admin panel, themes), Docker Compose assembly, CI/CD to ghcr.io, integration tests | ✅ Shipped |
| **v0.1.1** | Frontend completeness — WebSocket client (realtime PMs, notifications, presence), i18n with Crowdin, profile editing, reusable component library, pagination UI, frontend tests. Backend: moderation log, S3 config fix | 🔄 In progress |
| **v0.1.2** | Security & admin — rate limiting, CORS, full-text search, bulk user operations, expanded forum settings, optional email verification | ⬜ Planned |
| **v0.1.3** | Performance & polish — response caching, DB pooling tuning, OpenAPI docs, structured audit logging, lazy loading, mobile responsive, accessibility | ⬜ Planned |
| **v1.0.0** | Stable release — full test coverage, deployment guide, API reference, security audit, migration guide | ⬜ Planned |

**Next / Дальше:** completing v0.1.1 features → community feedback → v0.1.2 security hardening.

**RU**

| Версия | Описание | Статус |
|--------|----------|--------|
| **v0.1.0** | Первый релиз — полный бэкенд API (auth, CRUD, S3, WebSocket, admin, установка), фронтенд SPA (страницы форума, авторизация, админка, темы), сборка Docker Compose, CI/CD в ghcr.io, интеграционные тесты | ✅ Выпущен |
| **v0.1.1** | Завершение фронтенда — WebSocket клиент (PM, уведомления, presence), i18n с Crowdin, редактирование профиля, библиотека компонентов, пагинация, тесты фронтенда. Бэкенд: лог модерации, исправление S3 конфига | 🔄 В процессе |
| **v0.1.2** | Безопасность и админка — rate limiting, CORS, полнотекстовый поиск, массовые операции с пользователями, расширенные настройки, опциональная верификация email | ⬜ Запланировано |
| **v0.1.3** | Производительность и полировка — кэширование ответов, тюнинг пула соединений, OpenAPI доки, аудит лог, ленивая загрузка, мобильная адаптация, доступность | ⬜ Запланировано |
| **v1.0.0** | Стабильный релиз — полное покрытие тестами, гайд по деплою, справочник API, аудит безопасности, гайд миграции | ⬜ Запланировано |

**Дальше:** завершение v0.1.1 → обратная связь от сообщества → v0.1.2 укрепление безопасности.

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
