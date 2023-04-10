# api_yamdb
api_yamdb

**Как запустить проект:**
Клонировать репозиторий и перейти в него в командной строке:

```bash
@git clone https://github.com/yandex-praktikum/api_yamdb.git
@cd api_yamdb
```

Cоздать и активировать виртуальное окружение:

```bash
@python3 -m venv env
@source env/bin/activate
```

Установить зависимости из файла requirements.txt:

```bash
@python3 -m pip install --upgrade pip
@pip install -r requirements.txt
```

Шаблон наполнения env-файла:

```bash
DB_ENGINE='указываем, что работаем с postgresql'
DB_NAME='имя базы данных'
POSTGRES_USER='логин для подключения к базе данных'
POSTGRES_PASSWORD='пароль для подключения к БД'
DB_HOST='название сервиса (контейнера)'
DB_PORT='порт для подключения к БД'
```

Выполнить миграции:

```bash
@python3 manage.py migrate
```

Импортировать данные:

или из csv файлов:
```bash
@python3 manage.py import_data
```

или из сохраненного дампа БД:
```bash
@python3 manage.py loaddata ./static/data/data.json
```

Запустить проект:

```bash
@python3 manage.py runserver
```

Описание команд для запуска приложения в контейнерах:

```bash
sudo docker-compose up #для запуска контейнера
sudo docker-compose exec web python manage.py migrate # выполнить миграции
sudo docker-compose exec web python manage.py createsuperuser # создать суперпользователя
sudo docker-compose exec web python manage.py collectstatic --no-input # собрать статику
```

Остановка и удаление контейнеров вместе с зависимостями
```bash
docker-compose down -v
```
