
### Проверка проекта
[Редок](http://51.250.24.135/redoc/) <br>
[Админ](http://51.250.24.135/admin/) <br>
[API](http://51.250.24.135/api/v1/) <br>


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
