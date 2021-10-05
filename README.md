# [YaMDb]

![Django workflow](https://github.com/Player-18/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg)

Проект доступен по адресу: http://62.84.117.221/admin

Описание проекта:

Проект YaMDb - это сервис собирающий отзывы пользователей на книги, фильмы, музыку. Список категорий может быть расширен администратором сервиса. У произведения есть жанр, который можно выбрать из списка предустановленных(например, «Сказка», «Детектив» и т.п). Жанры создаются администратором сервиса. Пользователи могут оставить свой отзыв на произведение, но не более одного раза.

**Подготовка.**

Необходимо установить Docker:

-   выполните команду  `docker --version` и проверьте , что Docker установлен.

Если Docker отсутствует необходимо зайти на [официальный сайт](https://www.docker.com/products/docker-desktop)  и скачать установочный файл Docker Desktop для вашей операционной системы. Далее необходимо следовать инструкциям по установке в зависимости от Вашей операционной системы.

**Запуск приложения.**

1.  Клонируйте репозиторий:

`git clone https://github.com/Player-18/infra_sp2.git`

2.  Создайте виртуальное:

`python -m venv venv`

3.  Активируйте виртуальное окружение и запустите установку пакетов из requirements.txt:

`venv\Scripts\activate`

`pip install -r requirements.txt`

4.  Выполните команду:
 
    `docker-compose up -d --build`
    
5. После успешной сборки и запуска контейнеров нужно выполнить миграции:

`docker-compose exec web python manage.py migrate --noinput`

6.  Установите статику:

`docker-compose exec web python manage.py collectstatic --no-input`

7.  Заполните базу данных:

`docker-compose exec web python3 manage.py loaddata fixtures.json`

8.  Создайте суперпользователя:

`docker-compose exec web python manage.py createsuperuser`

Проект доступен по адресу  [http://127.0.0.1/](http://127.0.0.1/). 
