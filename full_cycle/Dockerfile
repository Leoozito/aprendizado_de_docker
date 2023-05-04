# no FROM adicionamos uma Image, um sistema operacional ja existente para ser a base da nossa Image
FROM nginx:latest
# no WORKDIR abaixo, o dockerfile cria essa pasta "app" e nos deixa dentro desta pasta
WORKDIR /app
# RUN adicionamos o comando que queremos que rode automaticamente
RUN apt-get update && \
    apt-get install vim -y
COPY html/ /usr/share/nginx/html
