
# Laravel Docker Starter Kit

Laravel is a web application framework with expressive, elegant syntax. We believe development must be an enjoyable and creative experience to be truly fulfilling. Laravel takes the pain out of development by easing common tasks used in many web projects

Laravel is accessible, powerful, and provides tools required for large, robust applications.

Kit has 3 docker containers: **php, nginx** and **mysql** 


## Installation

Download the project<br>
```composer create-project sarvar-lapasov/laravel-docker-starter-kit --ignore-platform-reqs --no-scripts```

Go to the project directory<br>
```cd laravel-docker-starter-kit```

Copy .env from .env.example <br>
```cp .env.example .env```

Run docker containers <br>
```docker compose up -d```

Install composer scripts:<br>
```docker compose exec php composer install```

Generate app key:<br>
```docker compose exec php php artisan key:generate```

Running migrations:<br>
```docker compose exec php php artisan migrate```

**Done! You can open <a href="http://localhost:8000" target="_blank">http://localhost:8000</a> via browser. 
By the way, you can change this port by changing ```DOCKER_NGINX_PORT``` variable in [.env](.env) file.** 

If you receive an error message (Permission denied)<br>
```docker compose exec php bash```<br>
```chown -R www-data:www-data storage/ bootstrap/cache/```


## Docker
For enter to php container run 
```docker compose exec php bash```

For enter to mysql container run 
```docker compose exec mysql bash```

For enter to nginx container run 
```docker compose exec nginx bash```

You can change containers prefix by changing ```DOCKER_PROJECT_NAME``` variable in [.env](.env) file.  

Also, you can change public ports of nginx and mysql by changing ```DOCKER_NGINX_PORT``` and ```DOCKER_DATABASE_PORT```

## Contributing

Thank you for considering contributing to the Laravel framework! The contribution guide can be found in the [Laravel documentation](https://laravel.com/docs/contributions).

## License

The Laravel framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).
