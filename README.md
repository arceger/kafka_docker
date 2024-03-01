## subimos o servico para uma imagem docker

docker-compose up -d

## valide se as imagens foram criadas corretamente 

docker images list

## logar na imagem criada

docker exec -it kafka-kafka-3-1 bash

## apos logar na imagem -- criar o topico

kafka-topics --create --bootstrap-server localhost:29092 --replication-factor 3 --partitions 3 --topic topico1

##listar o topico criado

kafka-topics --list --bootstrap-server localhost:29092

## criar um producer que ira enviar mensagens para o topico criado

kafka-console-producer --broker-list localhost:29092 --topic topico1

## em outro terminar criaremos o consumer

kafka-console-consumer --bootstrap-server localhost:29092 --topic topico1