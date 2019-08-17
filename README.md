Comandos a serem executados para dockerização e construção do servidor do eureka:

#Procedimento de Build

### Para executar sem o docker:

```
./gradlew clean build && java -jar build/libs/discovery-eureka-server-0.0.1-SNAPSHOT.jar
```

### Para realizar a geração do docker container (build):

```
./gradlew build docker
```

### Executar Container na porta específica:

```
docker run -p 8761:8761 -t discovery-eureka-server
```

### Push Images para o docker hub (devemos configurar para usar o da ufma):

```
docker login --username=yourhubusername --email=youremail@company.com
docker tag local-image:tagname new-repo:tagname
docker push new-repo:tagname
```

docker login -u marcosnasp
docker tag marcosnas/discovery-eureka-server:1.0.0 discovery-eureka-server:1.0.0
docker push discovery-eureka-server:1.0.0