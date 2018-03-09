# Laravel Docker

### A basic docker setup to get a Laravel project up and running quickly

##### Requirements

* Mac or Linux
* Docker
* Docker Compose

##### Instructions

1) Checkout this repository into your Laravel application, into a directory called `.docker` within the root

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

5) In this directory run `docker-compose up` and wait for the containers to be built and running

6) To run migrations, run `sudo docker exec -i -t PHP_CONTAINER_ID /bin/bash` to connect to the PHP container, then run `cd /code && php ./artisan migrate`

7) Edit your hosts file and add `127.0.0.1 application.local`

8) Open your browser and go to `http://application.local:8080`

9) Emails will be caught and can be viewed by going to `http://application.local:8025/`


###### Contact Me

 * [Website](https://lparkinson.com/)
 * [Email](mailto:mail@lparkinson.com)
