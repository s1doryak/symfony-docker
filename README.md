docker build -t s1doryak/symfony-cli ./cli
docker build -t s1doryak/symfony-fpm ./fpm
docker build -t s1doryak/symfony-nginx ./nginx

docker login

docker push s1doryak/symfony-cli
docker push s1doryak/symfony-fpm
docker push s1doryak/symfony-nginx