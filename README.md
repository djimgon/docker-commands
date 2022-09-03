# docker-commands

# Запуск композера внутри контейнера
docker-compose run -rm api-php-cli composer

# Деплой сайта
HOST=deploy@195.161.68.104 PORT=49347 REGISTRY=goohunter IMAGE_TAG=master-1 BUILD_NUMBER=1 make deploy

# Деплой реестра
HOST=deploy@ovz3.j49321827.0n03n.vps.myjino.ru PORT=49496 HTPASSWD_FILE=htpasswd make deploy

# Создание образа сайта и сервера
REGISTRY=goohunter IMAGE_TAG=master-1 BUILD_NUMBER=1 make build

# Загрузка в удаленный реест
REGISTRY=goohunter IMAGE_TAG=master-1 BUILD_NUMBER=1 make push

# Как внести изменения в composer
docker-compose run api-php-cli composer dump-autoload

# Как проверить работу nginx
docker-compose exec api curl --fail http://127.0.0.1/health
#
location /health {#
    add_header Content-Type text/plain;#
    return 200 'alive';#
}#
