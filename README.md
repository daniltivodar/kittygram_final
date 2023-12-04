Workflow
(https://github.com/daniltivodar/kittygram_final/actions/workflows/main.yml/badge.svg)

### Описание проекта
Проект kittygram создан для того, чтобы вы могли рассказать о своих котиках всем и каждому,
показать его фото, рассказать о его достижениях!

В проекте вы можете постисть своих котиков, смотреть чужих котиков.
Подробно рассказать о своем котике, выложить его фото, выбрать его цвет и год рождения.
Также вы можете рассказать о его достижениях. Написать свое, или выбрать уже существующее.


### Стек
```Django```
```Python```
```Gunicorn```
```Nginx```
```Docker```


### Как запустить проект
```
Клонируйте репозиторий
Создайте и заполните .env файл
Скачайте Docker
sudo apt update
sudo apt install curl
curl -fSL https://get.docker.com -o get-docker.sh
sudo sh ./get-docker.sh
sudo apt-get install docker-compose-plugin;
Перейдите в корень проекта
sudo docker compose pull
sudo docker compose down
sudo docker compose up -d
sudo docker compose exec backend python manage.py migrate
sudo docker compose exec backend python manage.py collectstatic
sudo docker compose exec backend cp -r /app/collect_static/. /static_backend/static/
Скачайте Nginx
sudo apt install nginx -y
sudo systemctl start nginx
sudo ufw allow 'Nginx Full'
sudo ufw allow OpenSSH
sudo ufw enable
sudo nano /etc/nginx/sites-enabled/default
Заменяем содержимое файла на это

server {
    listen 80;
    server_name example.com;
    
    location / {
        proxy_set_header HOST $host;
        proxy_pass http://127.0.0.1:9000;

    }
}

Сохраняем и закрываем файл
sudo nginx -tsudo systemctl start nginx
```

### Как заполнить env
nano .env
SECRET_KEY = 'django-insecure-cg6*%6d51ef8f#4!r3*$vmxm4)abgjw8mo!4y-q*uq1!4$-89$'
POSTGRES_USER=username
POSTGRES_PASSWORD=password
DB_HOST=db
DB_PORT=5432
ALLOWED_HOST=[]

###Автор
Данил Тиводар github: ```https://github.com/daniltivodar```