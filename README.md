# FJ-33 

Fernando Furtado

fernando.furtado@caelumn.com.br







# Aula 1 

Escalabilidade + infra

Micro serviço Syncronos

Load balance ou api gateway

Maior infra para prover esses serviços funcionando

Security gateway - Circuit breaker

Cannary deploy - Blue Green

service de aplicacao vs dominio

screaming architecture

log com identacao limite de char

https://martinfowler.com/bliki/CanaryRelease.html

https://martinfowler.com/bliki/BlueGreenDeployment.html

https://www.youtube.com/watch?v=5OjqD-ow8GE

https://martinfowler.com/bliki/StranglerFigApplication.html


separar banco perdeu ACID

separar bancos de acordo com a necessidade e demanda dos micros serviços

https://debezium.io/

kafka stream

change data capture

docker -> virtualizacao mais leve

container breakout

virtual nat 



----
rafa jenkins novo
ubuntu auto update desativar
conograma
---

S3FS

---

docker container run -v
docker volumes 
-- da pra usar formato S3FS
docker container logs

--link
forma ruin de conectar containers

--network
melhor forma de conectar containers

21017
3306

docker container cp [nome_docker]:[origem] [destino]

docker container cp [origem] [nome_docker]:[destino] 



docker exec -it micro8734_mongo.distancia_1 mongo

docker exec -it micro8734_mysql.monolito_1 bash

docker exec -it micro8734_mysql.monolito_1 mysqldump -u root -p --opt eats_pagamento > /tmp/bkp.sql

docker cp /tmp/bkp.sql micro8734_mysql.pagamento_1:/tmp/bkp.sql

docker cp ~/Downloads/restaurante_202001111618.csv micro8734_mongo.distancia_1:/tmp/restaurante_202001111618.csv


docker exec -it micro8734_mongo.distancia_1 bash 

mongoimport --db eats_distancia --collection restaurantes --type csv --fields=id,cep,tipoDeCozinhaId --file /tmp/restaurante_202001111618.csv 