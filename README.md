# docker-apache-php-mysql-service
A complete docker ecosystem to run php application with mysql database connectivity on apache server

# Steps to run Laravel Project With Docker

## Docker Service Setup
- Pull the repo outside of project directory. https://github.com/ziyed/docker-apache-php-mysql-service
- copy `.env.example` to `.env`
- Update `.env` variable with desired values
- Update the `docker-compose.yml > line 42` with your specific project folder of laravel
- Create a file name like `error.log` at `/docker-resource/apache-php/logs/` directory
- open the terminal and run `docker-compose up -d` command to run all services

## Laravel Project Setup
- Go to laravel project folder root and copy `.env.example` folder to `.env`
- Open the terminal and run the command `docker exec -it -u ziyed app bash`
- now run `composer install` to install the dependencies
- run `php artisan optimize:clear` when ever your have change in env file and wants to clear cache at any time
- run `php artisan migrate` to migrate all database table
- run `npm install` to install node modules
- run `npm run dev` or `npm run watch` for building assets

## phpMyAdmin 
- browser url `http://localhost:81`
- username/password :  root/root
