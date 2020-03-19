# Docker, Apache, MySQL, PHP and phpMyAdmin ( DAMPP )
A complete docker ecosystem to run php application with mysql database connectivity on apache server

# Ecosystem Includes
- Docker
- Apache
- Mysql 5.7
- PHP 7.2.7
- phpMyAdmin

# Docker Service Setup
- Pull the repo outside of project directory from here https://github.com/ziyed/dampp
- copy `.env.example` to `.env`
- Update `.env` variable with desired values
- Create a file name `error.log` inside `/docker-resource/apache-php/logs/` directory
- Confirmed you have project folder available before running below command
- open the terminal and run `docker-compose up -d` command to run all services

# Project Setup (Laravel 7)
- Go to project root folder and copy `.env.example` folder to `.env`
- Open the terminal and run the command `docker exec -it -u ziyed app bash`. You can replace `ziyed` with you define value at env file.
- now run `composer install` to install the dependencies.
- run `php artisan optimize:clear` when ever your have change in env file and wants to clear cache at any time.
- run `php artisan migrate` to migrate all database table.
- run `npm install` to install node modules.
- run `npm run dev` or `npm run watch` for building assets.
- browser url `http://localhost`

# phpMyAdmin 
- browser url `http://localhost:81`
- username/password :  root/root


# Features
- phpMyAdmin to manage MySQL database easily
- MySQL configuration file
- MySQL data backup thus it never lose any data if container down
- MySQL log output
- Apache server error log output
- Ability to update php.ini file
- Super flexible to change variable on env file
