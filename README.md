![yamdb_workflow](https://github.com/WayBro-54/yamdb_final/workflows/yamdb_workflow/badge.svg)

### Описание проекта  

API для проекта Yamdb на Django Rest Framework, документация Redoc, JWT-токены.
Доступ к работе с категориями, жанрами, произведениями, отзывами и комментариями.  

### Создатели

[Диана Корсак](https://github.com/onemi) <br>
[Артем Ултанов](https://github.com/WayBro-54) <br>
[Кирилл Резник](https://github.com/Invictus-7) <br>

### Список технологий
- Python
- Django
- Django Rest Framework
- JWT


### Документация проекта

Документация проекта доступна [вот здесь.](http://127.0.0.1:8000/redoc/) <br>
(для получения доступа к ней запустите<br>
отладочный сервер с адресом 127.0.0.1:8000)


### Как запустить проект  

Для запуска проект необходимо:<br>
- определиться, в какой директории на компьютере будет храниться проект<br>
- открыть командную строку и перейти в данную директорию<br>
- клонировать репозиторий командной git clone 'адрес репозитория на GitHub'<br>
- перейти в рабочую директорию или открыть проект в IDLE<br>

Создать и активировать виртуальное окружение:

```bash
python3 -m venv venv
source venv/bin/activate (для IDLE - venv/Scripts/activate)
```
  
Установить зависимости из файла requirements.txt:

```bash
python3 -m pip install --upgrade pip
pip install -r requirements.txt
```
  
Выполнить миграции:

```bash
python3 manage.py migrate
```
  
Запустить сервер:

```bash
python3 manage.py runserver
```

### Наполнение базы данных

Вместе с проектом поставляется демонстрационная база данных, состоящая<br> 
из 7-ми документов формата csv. Для того, чтобы перенести ее содержимое<br>
в базу данных Django, необходимо активировать скрипт:<br>
```bash
python3 manage.py data_transfer
```

  
### Пример запросов к API  

- Получение списка всех категорий

```python
/api/v1/categories/
```

```json
[
  {
    "count": 0,
    "next": "string",
    "previous": "string",
    "results": [
      {
        "name": "string",
        "slug": "string"
      }
    ]
  }
]
```

- Добавление комментария к отзыву 

```python
api/v1/titles/{title_id}/reviews/{review_id}/comments/
```

```json
{
  "text": "string"
}
```

- Регистрация нового пользователя

```python
api/v1/auth/signup/
```

```json
{
  "email": "string",
  "username": "string"
}
```
=======
# Api_final_yatube
![yamdb_workflow](https://github.com/WayBro-54/yamdb_final/workflows/yamdb_workflow/badge.svg)
## О проекте
REST API для социальной сети yatube.
Позволяет производить действия с постами, комментариями, сообществами и подписками.

## Требования
- Python 3.7 
- Django 2.2.19
- Djangorestframework 3.16

### Как запустить проект:
Клонировать репозиторий и перейти в него в командной строке:
```
git clone https://github.com/waybro-54/api_final_yatube.git
```
```
cd api_final_yatube
```
Cоздать и активировать виртуальное окружение:
```
python3 -m venv venv
```
```
source venv/bin/activate
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
python3 manage.py migrate
```
Запустить проект:
```
python3 manage.py runserver
```
### Примеры использования
**Получение списка постов**
```
curl --location --request GET 'http://127.0.0.1:8000/api/v1/posts/' --header 'Authorization: Bearer <your-token>'
[
    {
        "id": 1,
        "author": "user",
        "text": "New post",
        "pub_date": "2022-03-10T20:40:55.107802Z",
        "image": null,
        "group": 1
    },
    {
        "id": 7,
        "author": "dude",
        "text": "This is Dude",
        "pub_date": "2022-03-12T18:49:49.436966Z",
        "image": null,
        "group": 2
    }
]
```
**Создание поста**
```
$ curl --location --request POST 'http://127.0.0.1:8000/api/v1/posts/' \
--header 'Authorization: Bearer <your-token>' --header 'Content-Type: application/json' --data-raw '{"text": "This is Dude", "group": 2}'
{
    "id": 7,
    "author": "dude",
    "text": "This is Dude",
    "pub_date": "2022-03-12T18:49:49.436966Z",
    "image": null,
    "group": 2
}
```
>>>>>>> 40b8b57018d3781636a6d2e555925772652c6353
