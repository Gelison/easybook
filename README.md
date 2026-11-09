# EasyBook

Проект платформы для читателей и авторов: поиск и публикация книг с планируемыми инструментами озвучивания и перевода.

**Статус: начальная стадия разработки.** В репозитории есть стартовые приложения Next.js и NestJS, конфигурация pnpm workspace и Docker. Пользовательские сценарии платформы пока не реализованы.

## Текущая реализация

| Часть | Состояние |
| --- | --- |
| Frontend | Стартовая страница Next.js App Router |
| Auth service | Стартовое NestJS-приложение с GET-маршрутом; авторизация ещё не реализована |
| Общие пакеты | Каталог `packages/common` с конфигурацией TypeScript |
| Инфраструктура | Dockerfile для frontend/backend и Docker Compose |

## Стек в репозитории

- **Frontend:** Next.js 15, React 19, TypeScript, Tailwind CSS 4.
- **Backend:** NestJS 11, TypeScript.
- **Инструменты:** pnpm workspaces, Docker, ESLint, Prettier; Jest в backend-приложении.

## Локальная разработка

Потребуются Git, Node.js, совместимый с Next.js 15 и NestJS 11, и pnpm.

```sh
git clone https://github.com/Gelison/easybook.git
cd easybook
pnpm install
```

Frontend:

```sh
pnpm dev:frontend
```

В отдельном терминале запустите backend:

```sh
pnpm dev:auth
```

По умолчанию frontend использует порт 3000, backend — 3001. Порт backend можно задать переменной окружения `PORT`.

## Команды

| Команда | Назначение |
| --- | --- |
| `pnpm dev:frontend` | Next.js в режиме разработки |
| `pnpm dev:auth` | NestJS в режиме разработки |
| `pnpm build` | Сборка workspace-пакетов |
| `pnpm --filter @easybook/auth-service test` | Тесты backend-приложения |

Docker-конфигурация находится в [docker/](docker/) и [docker-compose.yml](docker-compose.yml).

## Структура

```text
easybook/
├── apps/
│   ├── frontend/                       # Next.js App Router
│   └── backend/services/auth-service/   # NestJS
├── packages/common/                    # Заготовка общего пакета
├── docker/                             # Dockerfile и документация
├── docker-compose.yml
├── package.json
└── pnpm-workspace.yaml
```

## Планы

- Каталог, поиск и фильтрация книг.
- Регистрация, вход и профили пользователей.
- Публикация произведений авторами.
- Читалка и аудиоплеер.
- AI-озвучивание и перевод.
- Рекомендации, оценки, комментарии и аналитика для авторов.

GraphQL, PostgreSQL, MongoDB, Redis, RabbitMQ и Kubernetes рассматриваются в концепции проекта; их не следует считать готовыми интеграциями.
