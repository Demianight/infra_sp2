# api_yamdb 

 

### Описание 

API для сервиса о произведениях искусства. 

### Технологии 

- Python 3.9 

- Django 2.2 

### Запуск 

Перед началом работы установите зависимости:  

``` 

pip install -r requirements.txt 

``` 

Из директории проекта, содержащей файл manage.py, выполните миграции:  

``` 

python3 manage.py migrate 

``` 

Теперь из этой же директории можно запустить проект: 

``` 

python3 manage.py runserver 

``` 

### Примеры запросов к API Yambd 

Регистрация на сервисе:  

``` 

http://127.0.0.1:8000/api/v1/auth/singup/ 

``` 

Получение токена:  

``` 

http://127.0.0.1:8000/api/v1/auth/token/ 

``` 

Получение данных через GET-запросы:  

 

- о категориях 

``` 

1. http://127.0.0.1:8000/api/v1/categories/ 

``` 

- о жанрах 

``` 

1. http://127.0.0.1:8000/api/v1/genres/ 

2. http://127.0.0.1:8000/api/v1/genres/{slug}/ 

``` 

- о произведениях 

``` 

1. http://127.0.0.1:8000/api/v1/titles/ 

2. http://127.0.0.1:8000/api/v1/titles/{titles_id}/ 

``` 

- об отзывах на произведениям 

``` 

1. http://127.0.0.1:8000/api/v1/titles/{title_id}/reviews/ 

2. http://127.0.0.1:8000/api/v1/titles/{title_id}/reviews/{review_id}/ 

``` 

- о комментариях к отзывам 

``` 

1. http://127.0.0.1:8000/api/v1/titles/{title_id}/reviews/{review_id}/comments/ 

2. http://127.0.0.1:8000/api/v1/titles/{title_id}/reviews/{review_id}/comments/{comment_id}/ 

``` 

Так же через POST, PUT, PATCH и DELETE-запросы к перечисленным  

эндпоинтам возможно редактирование данных. 

 

Полная документация с определением прав доступа ко всем эндпоинтам  

проекта, примерами содержания запросов и ответов доступна при запущеном  

проекте по адресу:  

``` 

http://127.0.0.1:8000/redoc/ 

``` 

### Авторы 

1. @____________ 

2. @____________ 

3. @____________


### Разворачивание проекта с помощью Docker 
Из директории infra_sp2/infra выполнить команду: ```docker-compose up --build -d```

После этого проект будет доступен по url: ```localhost/```

## Миграции и superuser 
```docker exec -it infra_web_1 bash``` - попадете в bash терминал контейнера с Django App
```python3 manage.py makemigrations; python3 manage.py migrate; python3 manage.py createsuperuser```
После этого регестрируетесь как админ. Вам станет доступна админ зона ```localhost/admin```