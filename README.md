Comandos a serem executados para dockerização e construção do servidor do eureka:

## Procedimentos de Build

### Para executar sem o docker:

```
./gradlew clean build && java -jar build/libs/discovery-eureka-server-0.0.1-SNAPSHOT.jar
```

### Para realizar a geração do docker container (build):

```
./gradlew build docker
```

### Executar o container na porta específica:

```
docker run -it -d --name discovery-eureka-server -p 8761:8761 discovery-eureka-server
docker container exec -it discovery-eureka-server /bin/sh
```


### Push Images para o docker hub (devemos configurar para usar o da ufma):

```
docker login -u marcosnasp
docker tag marcosnasp/discovery-eureka-server:1.0.0 discovery-eureka-server:1.0.0
docker push discovery-eureka-server:1.0.0
```

