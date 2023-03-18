# api_final
api final

### Описание:

Данный проект является бэкэндом проекта социальной сети Yatube, написанным на django. С помощью него в послесдствии могут быть разработаны фронтэнд, мобильное приложение и др. Но уже сейчас с приложением можно общаться на языке json запросов. Оно предоставляет почти все стандартные функции социальной сети: создание и просмотр постов, комментариев, сообществ и подписок.

### Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

```
git clone https://github.com/dmk0n/api_final_yatube
```

```
cd api_final_yatube
```

Cоздать и активировать виртуальное окружение:

```
python3 -m venv env
```

```
source env/bin/activate
```

Установить зависимости из файла requirements.txt:

```
python3 -m pip install --upgrade pip
```

```
pip install -r requirements.txt
```

Выполнить миграции:

```
cd yatube_api
```

```
python3 manage.py migrate
```

Запустить проект:

```
python3 manage.py runserver
```

### Примеры запросов и ответов API:
Получение публикаций:
```
GET ttp://127.0.0.1:8000/api/v1/posts/
```
Respoce:
```
{
  "count": 123,
  "next": "http://api.example.org/accounts/?offset=400&limit=100",
  "previous": "http://api.example.org/accounts/?offset=200&limit=100",
  "results": [
    {
      "id": 0,
      "author": "string",
      "text": "string",
      "pub_date": "2021-10-14T20:41:29.648Z",
      "image": "string",
      "group": 0
    }
  ]
}
```
Обновление публицации:
```
Put http://127.0.0.1:8000/api/v1/posts/{id}/
```
Payload:
```
{
  "text": "string",
  "image": "string",
  "group": 0
}
```
Response:
```
{
  "id": 0,
  "author": "string",
  "text": "string",
  "pub_date": "2019-08-24T14:15:22Z",
  "image": "string",
  "group": 0
}
```
Частичное обновление комментария:
```
PATCH http://127.0.0.1:8000/api/v1/posts/{post_id}/comments/{id}/
```
Payload:
```
{
  "text": "string"
}
```
Response:
```
{
  "id": 0,
  "author": "string",
  "text": "string",
  "created": "2019-08-24T14:15:22Z",
  "post": 0
}
```
Удаление комментария:
```
DELETE http://127.0.0.1:8000/api/v1/posts/{post_id}/comments/{id}/
```
Payload:
```
Copy
{
"detail": "Учетные данные не были предоставлены."
}
```
