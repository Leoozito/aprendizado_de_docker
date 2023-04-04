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

# Iniciando com bind mounts
## Mover pasta da nossa maquina para dentro do container
```
docker run -d --name nginx -p 8080:80 --mount type=bind,source="$(pwd)",target=/usr/share/nginx/html
```
> "$(pwd)" : pega o caminho da pasta atual que estamos localizados 
> source: da onde pegará
> target: o caminho aonde queremos chegar
> type=bind : que vc quer fazer um bind ou seja mandar uma pasta do nosso diretório para outro

