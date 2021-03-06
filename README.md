![workflow status badge](https://github.com/madpenguinw/foodgram-project-react/actions/workflows/foodgram_workflow.yml/badge.svg?branch=master&event=push)
# Foodgram
[![Python](https://img.shields.io/badge/-Python-464646?style=flat-square&logo=Python)](https://www.python.org/)
[![Django](https://img.shields.io/badge/-Django-464646?style=flat-square&logo=Django)](https://www.djangoproject.com/)
[![Django REST Framework](https://img.shields.io/badge/-Django%20REST%20Framework-464646?style=flat-square&logo=Django%20REST%20Framework)](https://www.django-rest-framework.org/)
[![PostgreSQL](https://img.shields.io/badge/-PostgreSQL-464646?style=flat-square&logo=PostgreSQL)](https://www.postgresql.org/)
[![Nginx](https://img.shields.io/badge/-NGINX-464646?style=flat-square&logo=NGINX)](https://nginx.org/ru/)
[![gunicorn](https://img.shields.io/badge/-gunicorn-464646?style=flat-square&logo=gunicorn)](https://gunicorn.org/)
[![docker](https://img.shields.io/badge/-Docker-464646?style=flat-square&logo=docker)](https://www.docker.com/)
[![GitHub%20Actions](https://img.shields.io/badge/-GitHub%20Actions-464646?style=flat-square&logo=GitHub%20actions)](https://github.com/features/actions)
[![Yandex.Cloud](https://img.shields.io/badge/-Yandex.Cloud-464646?style=flat-square&logo=Yandex.Cloud)](https://cloud.yandex.ru/)
___
Проект был доступен по адресу http://51.250.31.172/recipes, но в данный момент сервер отключен, так как закончилась студенческая подписка.
___
Приложение «Продуктовый помощник»: сайт, на котором пользователи могут публиковать рецепты, добавлять чужие рецепты в избранное и подписываться на публикации других авторов. Сервис «Список покупок» позволяет пользователям создавать список продуктов, которые нужно купить для приготовления выбранных блюд, и скачать его перед походом в магазин.
___
### Технологии
Python 3.7, Django 2.2, DRF, Docker, Docker-compose, Djoser, NGINX, PostgreSQL, Gunicorn, Yandex.Cloud

### Суперпользователь
```
email mihlastik@gmail.com
password Sokolov
```

### Пользователь
```
email lmikhailsokolovl@gmail.com
password Thisispassword
```

### Шаблон наполнения env-файла
```
DB_ENGINE=django.db.backends.postgresql
DB_NAME=postgres
POSTGRES_USER=postgres
POSTGRES_PASSWORD=postgres_penguinw
DB_HOST=db
DB_PORT=5432
SECRET_KEY=default='df5(dqyv#d%x(q_t6zuj&4^tyemi$t7jb+s-m(9@lws55)+^6o'
```
### Последовательность действий для запуска проекта в dev-режиме
- Клонировать репозиторий и перейти в него в командной строке.
```
git clone https://github.com/madpenguinw/foodgram-project-react
```
- Из корневой директории перейти в папку infra
```
cd infra/
```
- Запустить контейнеры с проектом
```
docker-compose up
```
- Подготовить миграции
```
docker-compose exec backend python manage.py makemigrations 
```
- Выполнить миграции
```
docker-compose exec backend python manage.py migrate
```
- Создать суперпользователя
```
docker-compose exec backend python manage.py createsuperuser
```
- Собрать статику
```
docker-compose exec backend python manage.py collectstatic --no-input
```
- Сделать дамп базы данных
```
docker-compose exec backend python manage.py dumpdata > fixtures.json
```
- Теперь можно зайти на http://localhost/admin/ и создать новые записи или же прочитать документацию на  http://localhost/api/docs/. Основной сайт доступен по адресу http://localhost/recipes.
- Чтобы закончить работу необходимо остановить контейнеры
```
docker-compose stop
```
### Действия для установки виртуального окружения
- Из корневой папки проекта:
```
python -m venv venv
source venv/Scripts/activate
python -m pip install --upgrade pip
```
- Установка зависимостей
```
cd backend/
pip install -r requirements.txt
```
- Выход из виртуального окружения
```
deactivate
```

---

### Автор

Соколов Михаил

Проект сделан в рамках учебного процеса по специализации Python-разработчик (back-end) Яндекс.Практикум.
