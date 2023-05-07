# Symfony Docker Images

Services:
- Nginx
- PHP-FPM
- MySQL
- (Symfony CLI)[https://symfony.com/download]

## Usage

Just copy `docker-compose.yml` to root of your project and run:

```
docker-compose up -d
```

### Symfony CLI

```
docker-compose run symfony check:requirements
```

### Composer

```
docker-compose run symfony composer require annotations
docker-compose run symfony composer require symfony/orm-pack
docker-compose run symfony composer require --dev symfony/maker-bundle
```

### Console
```
docker-compose run symfony php bin/console debug:router

docker-compose run symfony php bin/console doctrine:database:create

docker-compose run symfony php bin/console make:entity
docker-compose run symfony php bin/console make:migration

docker-compose run symfony php bin/console doctrine:migrations:diff
docker-compose run symfony php bin/console doctrine:migrations:migrate
```

## Contributing

### Build Images

```
docker build -t s1doryak/symfony-cli ./cli
docker build -t s1doryak/symfony-fpm ./fpm
docker build -t s1doryak/symfony-nginx ./nginx
```

### Login to Docker Hub

```
docker login
```

### Push Images

```
docker push s1doryak/symfony-cli
docker push s1doryak/symfony-fpm
docker push s1doryak/symfony-nginx
```