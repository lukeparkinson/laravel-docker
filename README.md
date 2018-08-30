# Laravel Docker

### A basic docker setup to get a Laravel project up and running quickly

##### Requirements

* Mac or Linux
* Docker
* Docker Compose

##### Instructions

1) Checkout this repository into your Laravel application, into a directory called `.docker` within the root

`git clone https://github.com/lukeparkinson/laravel-docker.git .docker`

2) Use these database settings in your `.env` file

```
DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=application
DB_USERNAME=application
DB_PASSWORD=password
```

3) Use these mail settings in your `.env` file

```
MAIL_DRIVER=smtp
MAIL_HOST=mailhog
MAIL_PORT=1025
MAIL_USERNAME=null
MAIL_PASSWORD=null
MAIL_ENCRYPTION=null
```

4) If you wish to use the redis container, use these settings in your `.env` file

```
CACHE_DRIVER=redis
```

```
SESSION_DRIVER=redis
```

```
REDIS_HOST=redis
REDIS_PASSWORD=null
REDIS_PORT=6379
```

5) The PHP container uses the redis extension, you need to tell Laravel to use this by editing `/config/database.php` and editing this line under `Redis Databases` section

```
'client' => 'phpredis',
```

6) In this directory run `docker-compose up` and wait for the containers to be built and running

7) To run migrations, run `sudo docker exec -it app_php bash` to connect to the PHP container, then run `cd /code && php ./artisan migrate:fresh --seed`

Remove the `--seed` if you don't wish to seed as well as run the migrations

8) Open your browser and go to `http://127.0.0.1:8080`

Notes:

* Emails will be caught and can be viewed by going to the mailhog URL below


#### Containers

Use the URLs below to access the containers:

| Container | URL |
| ------ | ------ |
| Nginx - Application | http://127.0.0.1:8080 |
| MySQL | http://127.0.0.1:3366 |
| Redis | http://127.0.0.1:6379 |
| Mailhog (web interface) | http://127.0.0.1:8025 |
| Cloud9 IDE | http://127.0.0.1:8081 |



###### Contact Me

 * [Website](https://lparkinson.com/)
 * [Email](mailto:mail@lparkinson.com)
