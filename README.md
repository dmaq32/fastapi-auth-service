# study2

## Запуск проекта

```bash
pip install -r requirements.txt
docker compose up -d --build
alembic upgrade head
docker compose down
docker compose up -d --build
