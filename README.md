## NetBlog_REST_API
### Описание

Данный проект представляет собой API для проекта NetBlog — платформа для
публикации личных микроблогов. API позволяет клиентам обращаться к базе данных
проекта NetBlog с различными запросами через формат JSON.
Аутентифицированным пользователям разрешено добавление постов и комментариев,
а также изменение и удаление своего контента; в остальных случаях
доступ предоставляется только для чтения.
Эндпоинт /follow/  - доступ только для аутентифицированных пользователей.

### Технологический стек
[![Python](https://img.shields.io/badge/-Python-464646?style=flat&logo=Python&logoColor=56C0C0&color=008080)](https://www.python.org/)
[![Django REST Framework](https://img.shields.io/badge/-Django%20REST%20Framework-464646?style=flat&logo=Django%20REST%20Framework&logoColor=56C0C0&color=008080)](https://www.django-rest-framework.org/)

### Установка
1)Клонировать репозиторий и перейти в него в командной строке:
```
git clone https://github.com/AnnaMihailovna/NetBlog_REST_API
```
```
cd netblog_rest_api
```
2)Cоздать и активировать виртуальное окружение:
```
python3.9 -m venv env
```
```
source venv/bin/activate
```
3)Установить зависимости из файла requirements.txt:
```
pip install -r requirements.txt
```
4)Подготовить и выполнить миграции:
```
python manage.py makemigrations
python manage.py migrate
```
5)Запустить проект:
```
python manage.py runserver
```
### Примеры
Для доступа к API необходимо получить токен: 
Необходимо выполнить POST-запрос на адрес http://127.0.0.1:8000/api/v1/jwt/create/
передав в теле запроса поля username и password. API вернет JWT-токен.
Передав токен в заголовке Authorization: Bearer <токен>
можно обращаться к методам **GET, POST, PUT, PATCH, DELETE**.

Например:
http://127.0.0.1:8000/api/v1/posts/

http://127.0.0.1:8000/api/v1/posts/{post_id}/comments/{id}/

http://127.0.0.1:8000/api/v1/groups/{id}/

### Автор
[AnnaMihailovna](https://github.com/AnnaMihailovna/)
