# docker

docker run -ti debian:9 bash


#subir serviços
docker run -d --name mysql -e MYSQL_ROOT_PASSWORD=mysql-secret -e MYSQL_DATABASE=wordpress mysql:5.7
docker run -d --name wordpress -p 80:80 wordpress

#executar o container
docker run -d --name php -p 80:80 -v $(pwd)/volume:/var/www/html php:5

#subir um arquivo docker-compose.yml
docker-compose up -d


#iniciar cluster
docker swarm init --advertise-addr 10.80.80.1

#construir uma imagem
docker build -t php:5 .

#criar um servico docker
docker service create \
  --mode global \
  --mount type=bind,source=$(pwd)/volume,destination=/usr/share/nginx/html \
  --publish mode=host,target=80,published=8080 \
  --name=nginx \
  nginx:latest


#subir um pilha de servicos
docker stack deploy --compose-file=docker-compose.yml wordpress
