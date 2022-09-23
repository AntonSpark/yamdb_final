![This is an image](https://github.com/AntonSpark/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg)

# api_yamdb

### Опиание проекта.
База отзывов пользователей о фильмах, книгах и др. Реализованы разные
права доступа для каждой категории пользователей. Целью проекта является сбор оценок и
комментариев о произведениях и формирование их усредненной оценки (рейтинга). 

### Мануал по устновке проекта

1. Клонировать репозиторий и перейти в него в командной строке:
```
git clone https://github.com/AntonSpark/api_yamdb.git
```
```
cd api_yamdb
```
2. Установить виртуальное окружение
```
python -m venv venv
```
3. Запустить виртуальное окружение
```
venv\Scripts\activate
```
4. Установить зависимости из файла requirements.txt:
```
python -m pip install --upgrade pip
```
```
pip install -r requirements.txt
```
5. Выполнить миграции:
```
python manage.py migrate
```
6. Запустить проект:
```
python manage.py runserver
```
### Реализация Docker:

1. Переходим в папку с файлом docker-compose.yaml:
```
cd infra
```
2. Пересобираем и запускаем docker-compose:
```
docker-compose up -d --build
```
3. Выполняем миграции:
```
- docker-compose exec web python manage.py makemigrations reviews
- docker-compose exec web python manage.py migrate
```
4. Создаем суперпользователя:
```
docker-compose exec web python manage.py createsuperuser
```
5. Собираем статику:
```
docker-compose exec web python manage.py collectstatic --no-input
```
6. Наполняем БД из файла фикстур:
```
docker-compose exec web python manage.py loaddata fixtures.json
```

## Шаблон наполнения .env файла:
```
- DB_ENGINE=django.db.backends.postgresql
- DB_NAME=postgres
- POSTGRES_USER=postgres
- POSTGRES_PASSWORD=postgres
- DB_HOST=db
- DB_PORT=5432
```
### Над проектом работал:

Антон Искров

![This is an image](https://github.com/AntonSpark/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg)
