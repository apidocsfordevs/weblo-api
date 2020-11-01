# weblo-api

Forked from https://github.com/ammezie/blog-api to demonstrate the Weblo case study for [API Documentation for Developers](http://apidocsfordevs.com).


## Requirements
- PHP 7.2+
- MySQL installed locally or Docker

## Setup
- Install dependencies: `composer install`

- Copy `.env.example` to a `.env` file and run `php artisan key:generate` to generate an application key.

- Start a MySQL server on your local machine on port 3306 with root password `secret`, and create a database `weblo`. An easy way is to use Docker: `docker run -it -p 3306:3306 --name weblo-db -e MYSQL_DATABASE=weblo -e MYSQL_ROOT_PASSWORD=secret -d mysql`.

- Run database migrations: `php artisan migrate`

- Run `php artisan serve` to start the application on http://localhost:8000