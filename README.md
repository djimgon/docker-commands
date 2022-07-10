# docker-commands

# Запуск композера внутри контейнера
docker-compose run -rm api-php-cli composer

# Деплой сайта
HOST=deploy@195.161.68.104 PORT=49347 REGISTRY=goohunter IMAGE_TAG=master-1 BUILD_NUMBER=1 make deploy

# Создание образа сайта и сервера
REGISTRY=goohunter IMAGE_TAG=master-1 BUILD_NUMBER=1 make build

# Загрузка в удаленный реест
REGISTRY=goohunter IMAGE_TAG=master-1 BUILD_NUMBER=1 make push

# Как внести изменения в composer
docker-compose run api-php-cli composer dump-autoload
