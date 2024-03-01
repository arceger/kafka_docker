### Apos clonar o arquivo yml

### Subimos o servico para uma imagem docker

docker-compose up -d

### Valide se as imagens foram criadas corretamente 

docker images list

### Logar na imagem criada

docker exec -it kafka-kafka-3-1 bash

### Apos logar na imagem, criar o topico

kafka-topics --create --bootstrap-server localhost:29092 --replication-factor 3 --partitions 3 --topic topico1

### Listar o topico criado

kafka-topics --list --bootstrap-server localhost:29092

### Criar um producer que ira enviar mensagens para o topico criado

kafka-console-producer --broker-list localhost:29092 --topic topico1

### E em outro terminar criaremos o consumer(pra visualizar as mensagens)

kafka-console-consumer --bootstrap-server localhost:29092 --topic topico1