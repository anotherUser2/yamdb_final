# Проект yamdb_final

Проект представляет собой API к базе произведений с жанрами, категориями и отзывами.
Текущий адрес проекта: http://51.250.16.171/redoc/

# Локальная сборка

git clone https://github.com/anotherUser2/yamdb_final.git
cd yamdb_final\infra

Сделать файл .env по шаблону
    SECRET_KEY=                             # ключ из settings.py
    DB_ENGINE=django.db.backends.postgresql # указываем, что работаем с postgresql
    DB_NAME=postgres                        # имя базы данных
    POSTGRES_USER=postgres                  # логин для подключения к базе данных
    POSTGRES_PASSWORD=postgres              # пароль для подключения к БД (установите свой)
    DB_HOST=db                              # название сервиса (контейнера)
    DB_PORT=5432                            # порт для подключения к БД

docker-compose up -d --build
docker-compose exec web python manage.py loaddata dump.json
docker-compose exec web python manage.py createsuperuser

# Работа с API

Все ендпоинты описаны в /redoc/:
    Регистрация нового пользователя
    Управление сущностями (категории, произведения, комментарии, ...)

# Автор проекта

Дмитрий Яковлев

![final_16 workflow](https://github.com/anotherUser2/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg)