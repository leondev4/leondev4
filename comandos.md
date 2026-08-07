Lista de comandos utilizados para generar la app
ejecutar en docker
Primero crear la red
docker network create laravel-network
Si se desea cambiar la base de datos, eliminar el volumen
docker volume create --name mariadb_data
``` docker run -d --name mariadb \ --env ALLOW_EMPTY_PASSWORD=yes \ --env
MARIADB_ROOT_PASSWORD=0bodega0 \ --env MARIADB_USER=laravel_quiz \ --env
MARIADB_DATABASE=laravel_quiz \ --network laravel-network \ --volume mariadb_data:/bitnami/mariadb \
-p 3306:3306 \ bitnami/mariadb:11.8.2
Ejecutar el comando en la carpeta padre del proyecto
docker run -d \ --name ecom-app \ #cambiar el nombre -p 8000:8000 \ --env DB_HOST=mariadb \ --env
DB_PORT=3306 \ --env DB_USERNAME=root \ #cambiar si se tiene otro usuario --env
DB_DATABASE=ecom_app \ #cambiar esto --network laravel-network \ --volume ${PWD}/ecom-app:/app \
#cambiar la ruta bitnami/laravel:12.0.10 ````
ejecutar bash desde container
docker exec -it a64 bash
realizar log del container
docker container logs 740
Crear una base de datos para el proyecto
Ir a phpmyadmin y agregar una base de datos con el nombre de quiza_app, ademas configurar la conexion en
.env, ejecutar migraciones.
cuando marque un error al guardar algun archivo, ejecutar desde el
host.
sudo chown -R $USER:$USER .
## Instalar dependencias con solo docker sin tener nada instalado docker run --rm -v /home/liz/training/ecomapp/laravel-quiz-system:/opt -w /opt laravelsail/php81-composer:latest composer install
https://medium.com/@enlabe/installing-laravel-dependencies-with-docker-without-installing-php-and-orcomposer-c7baa308f319 docker run --rm -v C:\Users\enlabe\develop\your-project:/opt -w /opt laravelsail/php83-
composer:latest composer install
### sh: 1: vite: Permission denied

sudo chmod +x node_modules/.bin/vite
ejecutar el comando desde el directorio padre de laravel-quiz-system
docker run -d \ --name laravel-quiz-system \ -p 80:8000 \ --env DB_HOST=mariadb \ --env DB_PORT=3306 \ --
env DB_USERNAME=laravel_quiz \ --env DB_DATABASE=laravel_quiz \ --network laravel-network \ --
volume ${PWD}/laravel-quiz-system:/app \ bitnami/laravel:12.0.10
DB_CONNECTION=mysql DB_HOST=127.0.0.1 DB_PORT=3306 DB_DATABASE=laravel_quiz
DB_USERNAME=laravel_quiz DB_PASSWORD=
ejecutar docker exponer el servicio fuera del
contenedor
docker run -it --rm --name n8n --network host -p 5678:5678 -v n8n_data:/home/node/.n8n
docker.n8n.io/n8nio/n8n
ngrok http 567