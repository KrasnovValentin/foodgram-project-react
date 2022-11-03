[![CI](https://github.com/KrasnovValentin/foodgram-project-react/actions/workflows/main.yml/badge.svg)](https://github.com/KrasnovValentin/foodgram-project-react/actions/workflows/main.yml)


## Проект Foodgram

**Foodgram** - приложение в котором пользователи могут публиковать рецепты, добавлять чужие рецепты в избранное и подписываться на публикации других авторов. Сервис «Foodgram» позволяет пользователям создавать список продуктов, которые нужно купить для приготовления выбранных блюд.

## Как развернуть проект на локальной машине:
- В директории infra файл example.env переименовать в .env и заполнить своими данными:
```
DB_ENGINE=django.db.backends.postgresql
DB_NAME=postgres
POSTGRES_USER=postgres
POSTGRES_PASSWORD=postgres
DB_HOST=db
DB_PORT=5432
SECRET_KEY=1234567890
```
- Установить на Docker, Docker-Compose
- Создать и запустить контейнеры Docker, выполнить команду:
```
sudo docker-compose up -d
```
- После успешной сборки выполнить миграции:
```
sudo docker-compose exec backend python manage.py makemigrations
sudo docker-compose exec backend python manage.py migrate
```
- Создать суперпользователя:
```
sudo docker-compose exec backend python manage.py createsuperuser
```
- Собрать статику:
```
sudo docker-compose exec backend python manage.py collectstatic --noinput
```
- В админ-панели добавить тэги для типов приемов пищи(завтрак, обед, ужин)
- Наполнить базу данных содержимым из файла ingredients.json:
```
sudo docker-compose exec backend python manage.py loaddata ingredients.json
```
- Для остановки контейнеров Docker:
```
sudo docker-compose down -v      # с их удалением
sudo docker-compose stop         # без удаления
```
- После запуска проект будет доступен по адресу: [http://localhost/](http://localhost/)
- Документация будет доступна по адресу: [http://localhost/api/docs/](http://localhost/api/docs/)


## Как развернуть проект на сервере:

- Установить на сервере Docker, Docker-Compose
- Скопировать на сервер файлы docker-compose.yml, nginx.conf из папки infra
- Создать и запустить контейнеры Docker, выполнить команду на сервере:
```
sudo docker-compose up -d
```
- После успешной сборки выполнить миграции:
```
sudo docker-compose exec backend python manage.py makemigrations
sudo docker-compose exec backend python manage.py migrate
```
- Создать суперпользователя:
```
sudo docker-compose exec backend python manage.py createsuperuser
```
- Собрать статику:
```
sudo docker-compose exec backend python manage.py collectstatic --noinput
```
- В админ-панели добавить тэги для типов приемов пищи(завтрак, обед, ужин)
- Наполнить базу данных содержимым из файла ingredients.json:
```
sudo docker-compose exec backend python manage.py loaddata ingredients.json
```
- Для остановки контейнеров Docker:
```
sudo docker-compose down -v      # с их удалением
sudo docker-compose stop         # без удаления
```
- Для работы с GitHub Actions необходимо в репозитории в разделе Secrets > Actions создать переменные окружения:
```
SECRET_KEY              # секретный ключ Django проекта
DOCKER_PASSWORD         # пароль от Docker Hub
DOCKER_USERNAME         # логин Docker Hub
HOST                    # публичный IP сервера
USER                    # имя пользователя на сервере
PASSPHRASE              # *если ssh-ключ защищен паролем
SSH_KEY                 # приватный ssh-ключ
TELEGRAM_TO             # ID телеграм-аккаунта для посылки сообщения
TELEGRAM_TOKEN          # токен бота, посылающего сообщение
DB_ENGINE               # django.db.backends.postgresql
DB_NAME                 # postgres
POSTGRES_USER           # postgres
POSTGRES_PASSWORD       # postgres
DB_HOST                 # db
DB_PORT                 # 5432 (порт по умолчанию)
```


### Стэк технологий.
▪ **Python**<br>
▪ **Django**<br>
▪ **Django Rest Framework**<br>
▪ **Docker**<br>
▪ **Gunicorn**<br>
▪ **NGINX**<br>
▪ **PostgreSQL**<br>
▪ **Yandex Cloud**<br>
▪ **CI/CD**<br>
  
![](https://img.shields.io/badge/Python-3.7.0-blue?style=flat&logo=python&logoColor=white)
![](https://img.shields.io/badge/Django-3.2.15-orange?style=flat&logo=django&logoColor=white)
![](https://img.shields.io/badge/PostgreSQL-13.0-blue?style=flat&logo=postgresql&logoColor=white)


#### Автор проекта:

###### Краснов Валентин 34-когорта(Яндекс-Практикум)
```
e-mail: valentin.red@yandex.ru
```
