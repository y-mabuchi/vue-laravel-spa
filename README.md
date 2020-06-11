# What is this?
This is Vue Laravel SPA tutorial.

Reference this page.

[Vue.js + LaravelでシンプルなSPA構築チュートリアル：概要編](https://qiita.com/minato-naka/items/2d2def4d66ec88dc3ca2)

# Requirements
- Docker
- Nginx
- PHP
- MySQL
- phpmyadmin

# How to start
## Clone
```terminal
$ git clone https://github.com/y-mabuchi/vue-laravel-spa.git
```

## Start Docker
```terminal
$ cd vue-laravel-spa
$ docker-compose up -d --build
```

## Laravel set up
Set up in host terminal.
```terminal
$ cp .env.example .env
```

Change database setting.
```.env
DB_HOST=mysql
DB_DATABASE=sample
DB_USERNAME=user
DB_PASSWORD=password
```

## Generate app key
Run following command in docker container.
```terminal
$ docker-compose exec app bash
$ cd vue-laravel-spa
$ php artisan key:generate
```

## Run migrate
Run migarate in docker container.
```terminal
$ docker-compose exec app bash
$ cd vue-laravel-spa
$ php artisan 
```

## Install Dependancies
Run this command in docker container.
```terminal
$ docker-compose exec app bash
$ cd vue-laravel-spa
$ composer install
$ npm install
```

## Build vue
Build vue files in docker container.
```terminal
$ docker-compose exec app bash
$ npm run dev
```

## Open in your browser
```browser
http://localhost:8000/
```
