# Instalar DOCKER - LINUX

Para remover algum docker que esteja instalado na maquina
```
sudo apt-get remove docker-engine docker.io
```

Em seguida para instalar o docker

```
sudo apt install docker.io
```

Para iniciar o DOCKER

```
sudo systemctl start docker
```

Para verificar se o docker ja está rodando, o status dele

```
systemctl status docker
```

Verificar se o docker está instalado e rodando de fato

```
docker --version
```

```
sudo docker run hello-world
```

```
sudo docker images
```