# Docker, Apache, MySQL, PHP7 and phpMyAdmin ( DAMPP )
A complete docker ecosystem to run php7 application with mysql database connectivity at apache server

# Ecosystem
- Apache
- PHP 7.2.7
- Mysql 5.7
- phpMyAdmin
- Docker

# Steps to run Project With Docker

## Docker Service Setup
- Pull the repo outside of project directory from here https://github.com/ziyed/docker-apache-php-mysql-service
- copy `.env.example` to `.env`
- Update `.env` variable with desired values
- Create a file name `error.log` at `/docker-resource/apache-php/logs/` directory
- open the terminal and run `docker-compose up -d` command to run all services

## Project Setup (Laravel)
- Go to project root folder and copy `.env.example` folder to `.env`
- Open the terminal and run the command `docker exec -it -u ziyed app bash`. You can replace `ziyed` with you define value at env file.
- now run `composer install` to install the dependencies.
- run `php artisan optimize:clear` when ever your have change in env file and wants to clear cache at any time.
- run `php artisan migrate` to migrate all database table.
- run `npm install` to install node modules.
- run `npm run dev` or `npm run watch` for building assets.

## phpMyAdmin 
- browser url `http://localhost:81`
- username/password :  root/root
