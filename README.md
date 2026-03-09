Проект 5. Трекер привычек
/
Инструкция для запуска проекта на удалённом сервере с помощью Docker:

    Клонировать проект: https://github.com/maxim0275/coursework_drf-main
    Переименовать файл .env.sample в .env и заполнить его необходимыми переменными
    Ввести в терминале команду "docker-compose up -d --build"

Проверка работоспособности сервисов

		1. Бэкенд:
    Запустить команду curl http://localhost:8000/api/health.
    Убедиться, что ответ содержит "status": "ok".

		2. PostgreSQL:
    Использовать команду psql -h localhost -U <username> -d <database> для подключения.
    Выполнить простую команду, например, SELECT 1;, и проверить, что она выполняется успешно.

		3. Redis:
    Выполнить команду redis-cli -h localhost ping.
    Убедиться, что ответ "PONG".

		4. Celery:
    Убедиться, что Celery воркеры запущены с помощью команды docker-compose logs celery.
    Проверить, что в логах нет ошибок.

-----------------------------------------------------------
35.2 CI/CD и GitHub Actions

Технологии:

    python 3.13
    postgresql
    Redis
    os
    dotenv
    API

Используемые библиотеки:

    Django
    djangorestframework
    djangorestframework-simplejwt
    celery
    django-celery-beat
    pillow
    psycopg2-binary
    python-dotenv
    redis
    django-cors-headers
    drf-yasg

Инструкция для развертывания проекта:

    Клонировать проект: https://github.com/jekaGitHub/coursework_drf.git

    Создать виртуальное окружение: В терминале запустить команды:

    poetry config virtualenvs.in-project true

    Установить зависимости: Для установки всех зависимостей в терминале необходимо запустить команду:

    poetry install --no-interaction --no-ansi

    Cоздать базу данных: В терминале введите команду:

    CREATE DATABASE database_name

    Применить миграции: В терминале введите команды:

    python3 manage.py makemigrations python3 manage.py migrate

    Заполнить файл .env по образцу .env.sample

    Для создания суперпользователя необходимо применить команду: python3 manage.py csu

    Для запуска проекта использовать команду: python manage.py runserver

    Для подключения бота в Телеграм перейти по ссылке: t.me/user_habit_bot

    Для запуска периодических задач необходимо применить команду: "celery -A config worker --beat --scheduler django --loglevel=info "

    Документация API: Swagger http://127.0.0.1:8000/swagger/ Redoc http://127.0.0.1:8000/redoc/

