# Laravel Docker

### A basic docker setup to get a Laravel project up and running quickly

##### Requirements

* Mac or Linux
* Docker
* Docker Compose

##### Instructions

1) Checkout this repository into your Laravel application, into a directory called `.docker` within the root

2) Use these database settings in your `.env` file

```DB_CONNECTION=mysql
   DB_HOST=db
   DB_PORT=3366
   DB_DATABASE=application
   DB_USERNAME=application
   DB_PASSWORD=password
```

3) In this directory run `docker-compose up` and wait for the containers to be built and running

4) To run migrations, run `sudo docker exec -i -t PHP_CONTAINER_ID /bin/bash` to connect to the PHP container, then run `cd /code && php ./artisan migrate`

5) Edit your hosts file and add `127.0.0.1 application.local`

6) Open your browser and go to `http://application.local:8080`


###### Contact Me

 * [Website](https://lparkinson.com/)
 * [Email](mailto:mail@lparkinson.com)
