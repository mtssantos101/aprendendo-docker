# O que é docker compose
O Docker Compose é uma ferramenta que permite definir e gerenciar multi-contêineres Docker para aplicações complexas. Em vez de rodar contêineres manualmente com múltiplos comandos docker run, você pode definir tudo em um único arquivo docker-compose.yml.

Exemplo de docker-compose.yml:
```
version: '3'
services:
  web:
    build: .
    ports:
      - "5000:5000"
    volumes:
      - .:/app
  db:
    image: postgres
    environment:
      POSTGRES_PASSWORD: mysecretpassword
```
## Esse comando combina dois processos: construir as imagens Docker e iniciar os serviços definidos no arquivo de configuração

```
docker compose up --build
```
