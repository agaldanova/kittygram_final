# Kittygram
Kittygram - веб-приложение для публикации фотографий котиков.
Финальный проект: контейнеры и CI/CD для Kittygram
## Workflow status
```
[![Main Taski workflow](https://github.com/agaldanova/kittygram_final/actions/workflows/main.yml/badge.svg)](https://github.com/agaldanova/kittygram_final/actions/workflows/main.yml)
```
## Технологии
- Python 3.12
- Django 5.1
- Django REST Framework
- PostgreSQL
- React
- Nginx
- Docker
- GitHub Actions

### Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

```
git clone https://github.com/agaldanova/kittygram_final.git
```

```
cd kittygram_final
```

Создайте файл .env и укажите необходимые переменные окружения:
```
USE_SQLITE=False
SECRET_KEY=YOUR_SECRET_KEY
DEBUG=False
ALLOWED_HOSTS=localhost

POSTGRES_USER=django_user
POSTGRES_PASSWORD=YOUR_PASSWORD
POSTGRES_DB=django

DB_HOST=db
DB_PORT=5432
```
Соберите и запустите контейнеры:
```
docker compose up -d --build
```
Примените миграции и соберите статику
```
docker compose exec backend python manage.py migrate
docker compose exec backend python manage.py collectstatic
docker compose exec backend cp -r /app/collected_static/. /backend_static/static/
```
Создайте суперпользователя:
```
docker compose exec backend python manage.py createsuperuser
```
Проект доступен по адресу: <http://localhost:9000`>.

## Автор
Амарсана Галданова
agaldanova@gmail.com
