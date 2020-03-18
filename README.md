# docker-apache-php-mysql-service
A complete docker ecosystem to run php application with mysql database connectivity on apache server



# Steps to run Laravel Project With Docker

## Docker Service Setup
- Pull the repo outside of project directory. https://github.com/ziyed/docker-apache-php-mysql-service
- Update .env variable when download completed
- Update the `docker-compose.yml > line 42` with your specific project folder of laravel project
- open the terminal and run `docker-compose up -d` command

## Laravel Project Setup
- Go to laravel project folder and copy .env.example folder to .env
- Open the terminal and run the command `docker exec -it -u ziyed app bash`
- now run `composer install` to install the dependencies
- 
