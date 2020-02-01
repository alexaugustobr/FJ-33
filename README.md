# FJ-33 

Fernando Furtado

fernando.furtado@caelumn.com.br



docker-compose up -d



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




aula 2

change data capture

REST = descricao de um modelo arquitetural da web
achitectural styles and the design of network-based software architectures

Rest = estilo arquitetural web
restful = algo q tem o estilo arquitetural da web

ics.uci.edu

Retrofit 
Feign

choose your own adventure

HAL-FORMS 


IDL (interface)
protobuf

thrift

gRCP

kubernetes api gateway


graph ql eventos


api gateway proxy reverso

ingress controller kubernetes

arquitetura de migracao de micro servico

strangler application

kubernetes service smash

microservices.io

SQRS

api composition no api gateway

slideshow alexandreaquiles microservice

netflix filter zuul groovy

exs 

micro8734

aula 3 


filter

cap 6

multiplos stream arquivos, em partes, arquivos grandes multi conexoes

zsh auto suggestions

ZuulFilter

LocationRewriter
201 == header location
explicando aonde foi criado o recurso

ordem filtro servlet

rate limit login

api company jhon

load balance -> ngix harproxy  - > downtime

load balance -> ribbon 

orquestrador de cluster

config por yml por nome de serviço

stripPrefix remove path
path substitui path

separar log

gravar log separado

mvn spring-boot:run -Dspring-boot.run.arguments=--server.port=8085




cap 7

zookeper -> service discovery
eureka
disponibildiade do service discovery

multy installing, buildar app dentro do docker
//montar m2

//EnableDiscoveryClient
//

spring log tags

log similar a log do mvns

test integracao qualidade

syncrono
micro servido dependente

try catchs -> circuit breaker -> fallback

try catch Exception mt custoso jvm -> criar teste

hystrix -> resilence4j
zuul -> cloud gateway

apache bench
test request

exception run time vs throwable

via cep api

debug jvm remote,
gravar querys executadas para tirar metricas (analise log base)

spring retry

gravar quanto tempo o worker demora para processar
criar metrica, com base na metrica, enviar requests para filas prioritarias

@Backooff, a cada tentativa multiplica o delay

docker multi stage

https://martinfowler.com/bliki/CanaryRelease.html
https://martinfowler.com/bliki/BlueGreenDeployment.html
https://www.youtube.com/watch?v=5OjqD-ow8GE
https://martinfowler.com/bliki/StranglerFigApplication.html

http://dockerdocs.gclearning.cn/docker-for-windows/install/
https://gitlab.com/fj33-micro8734

http2 server sent event ssE stream

https://www.w3schools.com/html/html5_serversentevents.asp


cap 10

aula 4

rabbitmq 
garantia de entrega


JMS -> bom para se precisar trocar
-MqSeries
-ArchiveMq

SQS - > amazon -> garante ordem porem cara, mas pode ter msg duplicada

kafka -> plataforma de stream, topico, garantia de ordem com uma partição, orgem global
-> usa disco e é mais rapido q os demais
-> event sourcing 
  -> guarda exemplo transacoes de dinheiro ao invez de atualizar
  -> git é similar a event sourcing por ex
-> retem por 7 dias
  -> cria snapshot
-> kafka connect -> copiar dados de um bd para outro -> mysl cassandra
-> kafka stream -> pipes 
   -> indices e partições




rabbitmq -> fila -> ampq e stomp
tryrabbitmq.com
-> binding key 
direct ->>>
fanout ->>>
topic  ->>>


erlang -> bean
elixir -> gera erlang

data acess layer


-vovo
repository é serializavel
documentar rafa infra
fila para liberar os caches rabbit


SSE
RSocket
WebSocket

--- 

STOMP > SSE

MQTT

-- 
filas por cliente front via websocket stomp

teste de contrato

spring cloud contract

contract-verifier

prof spring docs??

air mock


--config server
consul
zookeeper
spring config server

spring cache

https://docs.spring.io/spring-boot/docs/current/reference/html/production-ready-features.html

https://www.baeldung.com/spring-boot-actuators

micrometer

https://spring.io/blog/2018/03/16/micrometer-spring-boot-2-s-new-application-metrics-collector


