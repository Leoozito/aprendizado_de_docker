FROM node 
# minha image vai se basear na image do node
WORKDIR /usr/src/app
# aonde nossa aplicação será criada
COPY package.json .

RUN npm install
# instalar todos nossos pacotes
COPY . .
# copiar todos os arquivos e colar no meu diretorio do workdir
EXPOSE 3000
# expondo a porta
CMD ["node","index.js"]
# comando que será executado depois de tudo
