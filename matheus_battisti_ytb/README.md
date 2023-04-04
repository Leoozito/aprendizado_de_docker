# Fundamentos do docker

> O começo do docker é ter obviamente o docker instalado e se possivel no VScode ter uma extensão do Docker baixado
```
docker version
```

> Container: uma forma de executar as imagens, um software, uma linguagem, um framework
> A Image: podemos pensar como um projeto que será inicializado pelo container

### Para rodar por exemplo, um Image de linux, ou seja, ter um terminal de ubuntu no terminal do windows
```
docker run -it ubuntu
```
> docker run: Estamos mandando com que o docker rode uma interface pré programada, e no caso acima, rodou um container que tem um projeto "Image" que é o "ubuntu"

### Para saber quais container estão ativos
```
docker ps
```

### Para mostrar todos containers
```
docker ps -a
```

### Para ativar um container e não precisa lidar com o terminal
```
docker run -d nomedocontainer
```

### Para adicionar um nome à um container
```
docker run -d -p 80:80 --name nomedomeucontainer nginx
``` 
> -p : publicar porta
> -d : desatachando meu terminal do processo do container, o terminal não ficará preso

### Para parar esse container
```
docker ps
``` 
```
docker stop [o NAME ou o CONTAINER ID]
```

## Para usar uma porta de um container
```
docker run -d -p 80:80 nginx
```
> Para reiniciar nosso container, e não ter que criar outro container
```
docker start [o NAME ou o CONTAINER ID]
```

### Para remover um container
> primeiro tem que parar
```
docker stop [o NAME ou o CONTAINER ID]
```
> em seguida
```
docker rm nomedomeucontainer -f
```

Para criar uma Image personalizada se usa o : Dockerfile [...]

### Depois de criar uma Image no dockerfile, e o docker entender que há uma Image para buildar, só rodar
```
docker build .
```

### E para rodar um container com base na nossa Image
```
docker image ls
```
> copiar o Image ID
```
docker run -p 3000:3000 -d [IMAGE ID]
```

# Sendo assim nós criamos nossa própria image e rodou ela no container, fazendo também ele rodar em nossa porta localhost:3000

### para apagar uma image
> primeiro o container
```
docker rm nomedocontainer
```
> depois a image
```
docker rmi nomedaimage
```