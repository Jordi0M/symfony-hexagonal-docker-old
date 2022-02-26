# symfony-hexagonal-docker

1. Crear docker-compose.yml con las configuraciones en los dockerfile
2. Dentro de la bash de php-fpm, crearemos el proyecto de symfony (con el composer ya instalado, el cual se habrá ejecutado desde el Dockerfile)
   
- Para crear el proyecto dentro de la bash:
> composer create-project symfony/skeleton project-test

- Más tarde, moveremos todo el "project-test" a la raíz (incluidos los ficheros ocultos)
> mv project-test/* .
> mv project-test/.env .env
> mv project-test/.gitignore .gitignore

- Es posible que al crear los ficheros dentro de la bash de php-fpm, no tengamos permisos. En la consola local ejecutar dentro del proyecto:
> sudo chown -R $USER:$USER .


- Para instalar dependencias una vez clonas el proyecto:
> touch .env
> composer install