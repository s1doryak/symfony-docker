# Build Images
docker build -t s1doryak/symfony-cli ./cli
docker build -t s1doryak/symfony-fpm ./fpm
docker build -t s1doryak/symfony-nginx ./nginx

# Login to Docker Hub
docker login

# Push Images
docker push s1doryak/symfony-cli
docker push s1doryak/symfony-fpm
docker push s1doryak/symfony-nginx

# Symfony CLI
docker-compose run symfony check:requirements
docker-compose run symfony composer require annotations
docker-compose run symfony composer require symfony/orm-pack
docker-compose run symfony composer require --dev symfony/maker-bundle
docker-compose run symfony php bin/console debug:router
docker-compose run symfony php bin/console make:entity
docker-compose run symfony php bin/console make:migration
docker-compose run symfony php bin/console doctrine:database:create
docker-compose run symfony php bin/console doctrine:migrations:migrate