### Listar todos os diretorios do container
```
docker exec nginx ls
```
### Entrar no meu container e executar um bash
```
docker exec -it nginx bash
```
> -it : metodo interativo
### Instalar o VIM
> VIM : é um editor de texto do terminal
> com ele da para acessar um arquivo por meio do terminal, e alterar coisas por meio do terminal
```
sudo apt-get update
```
``` 
sudo apt-get install vim
```

## Ver mais informações sobre o container
```
docker inspect [o NAME ou o CONTAINER ID]
```

# Iniciando com bind mounts
## Mover pasta da nossa maquina para dentro do container
```
docker run -d --name nginx -p 8080:80 --mount type=bind,source="$(pwd)",target=/usr/share/nginx/html
```
> "$(pwd)" : pega o caminho da pasta atual que estamos localizados 
> source: da onde pegará
> target: o caminho aonde queremos chegar
> type=bind : que vc quer fazer um bind ou seja mandar uma pasta do nosso diretório para outro

### Trazer todos os container inativos 
```
docker ps -a -q
```
## e apagar todos esses containers inativos
```
docker rm $(docker ps -a -q) -f
```

# NETWORK

## Criar uma network 
```
docker network create --driver brigde nomedarede
```
### Colocar dois containers para se comunicarem entre si dentro da nossa rede
```
docker run -dit --name nomedocontainer1 --network nomedarede bash
[...]
docker run -dit --name nomedocontainer2 --network nomedarede bash
```

### Conectar um container que esteja fora da nossa rede
```
docker network connect nomedarede nomedocontainer
```

### Fazer com que nosso container acesse nossa porta localhost de uma aplicação
> docker run --rm -it --name ubuntu ubuntu bash
> apt-get update
> apt-get install curl -y
> curl http://host.docker.internal:8000 (numero da porta da aplicação que está rodando)