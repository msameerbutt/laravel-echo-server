# Laravel Brodcasting event via web socket

## Prerequisites
1. Docker
1. Git

## Dependencies
1. PHP FPM 7.4
1. Nginx 1.17
1. Node 13.7
1. Redis
1. Laravel 8.0
1. Laravel Echo Server

## Steps to Test

1. Create .env file from .env.example file
1. Run the entire stack from site root `docker-compose up -d`
1. Install Composer dependencies from site root with `docker-compose run --rm composer install --ignore-platform-reqs`
1. Instsll NPM dependencies from site root with `docker-compose run --rm npm install`
1. Compile JS/CSS files from site root with `docker-compose run --rm npm run dev`
1. Prepare the .env file 
1. Browse the site `http://localhost:80`, you should see a Laravel welcome page, and open console tab to see broadcasted event data
1. Jump into the app container from site root with `docker-compose exec app bash` and run the following command to listen queue `php artisan queue:listen --tries=1`
1. Browse this route to broadcase a public event `http://localhost/test-broadcast`
1. You should see the event data 