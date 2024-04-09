# Taski

![](https://github.com/dmBra1n/taski-docker/actions/workflows/main.yml/badge.svg)

## Описание проекта
Небольшое приложение, которое позволяет пользователям создавать собственные задачи и отслеживать их выполнение.<br>
Проект состоит из бэкенд-приложения на Django и фронтенд-приложения на React.

Приложение позволяет:
- Создать, удалить, изменить задачу, а также отметить её как выполненную.

Проект написан в рамках учебного курса "Python-разработчик" от Yandex.Practicum.<br>
Основные задачи бали: 
- развернуть fronend и backend на облачном сервере используя Docker;
- настроить автоматизацию деплоя CI&CD.

#### Инструменты и стек:
![Python](https://img.shields.io/badge/python-3670A0?style=flat-square&logo=python&logoColor=ffdd54)
![DjangoREST](https://img.shields.io/badge/DJANGO-REST-ff1709?style=flat-square&logo=django&logoColor=white&color=ff1709&labelColor=gray)
![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=flat-square&logo=docker&logoColor=white) <br>
![Nginx](https://img.shields.io/badge/nginx-%23009639.svg?style=flat-square&logo=nginx&logoColor=white)
![Gunicorn](https://img.shields.io/badge/gunicorn-%298729.svg?style=flat-square&logo=gunicorn&logoColor=white) 
![Actions GitHub](https://img.shields.io/badge/github%20actions-%232671E5.svg?style=flat-square&logo=githubactions&logoColor=white)

## Локальный запуск проекта
1. Склонировать репозиторий
2. В корне проекта создать и прописать файл _.env_
  
    ```env
    POSTGRES_USER=<имя_пользователя_БД>
    POSTGRES_PASSWORD=<пароль_БД>
    POSTGRES_DB=<имя_БД>
    DB_PORT=<порт_соединения_к_БД>
    DB_HOST=db
    
    SECRET_KEY=<django_secret_key>
    ```
3. В теменале, в корне проекта выполнить команду `docker compose up -d`
4. Вполнить миграции и собрать статику:
     ```
     docker compose exec backend python manage.py migrate
     docker compose exec backend python manage.py collectstatic
     docker compose exec backend cp -r /app/collected_static/. /backend_static/static/  
     ```
Сервер будет доступен по адресу: http://localhost:8000/

  ## Автор
Вадим Миронов - [ссылка на GitHub](https://github.com/dmBra1n)
