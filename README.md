# FastAPI Auth Service

Небольшой учебный сервис аутентификации на FastAPI с PostgreSQL и Alembic.

## Что внутри

- `project/app/` - приложение FastAPI;
- `project/migrations/` - миграции Alembic;
- `project/docker-compose.yml` - локальный запуск сервиса и базы данных;
- `project/Dockerfile` - контейнеризация приложения.

## Возможности

- регистрация пользователя;
- получение JWT-токена;
- проверка подключения к базе данных;
- просмотр списка пользователей.

## Локальный запуск

Все команды ниже выполняются из директории `project/`.

```bash
cd project
cp .env.example .env
pip install -r requirements.txt
docker compose up -d --build
alembic upgrade head
```

После запуска сервис доступен по адресу `http://localhost:8000`.

## Конфигурация

Основные параметры вынесены в переменные окружения:

- `DATABASE_URL`
- `SECRET_KEY`
- `JWT_ALGORITHM`
- `ACCESS_TOKEN_EXPIRE_MINUTES`
- `POSTGRES_USER`
- `POSTGRES_PASSWORD`
- `POSTGRES_DB`
- `POSTGRES_PORT`
- `APP_PORT`

## Примечания

- Проект ориентирован на локальную разработку и учебное использование.
- Для публичного репозитория добавлен шаблон конфигурации `.env.example`; реальные секреты в репозиторий не кладутся.
- В публичной версии репозитория не хранятся локальные кэши, виртуальные окружения и прочие generated-файлы.
