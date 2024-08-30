# O que é dockerfile

Dockerfile é um arquivo de texto que contém uma série de instruções sobre como criar uma imagem Docker. Essas instruções definem o ambiente, as dependências, e o comportamento da aplicação que será executada dentro de um contêiner. O Docker lê o Dockerfile e executa cada instrução para criar uma imagem personalizada, que pode ser usada para instanciar contêineres.

## Por que usar um Dockerfile?
- Automatização: Automatiza o processo de criação de imagens, garantindo que todos os desenvolvedores ou ambientes de produção possam gerar a mesma imagem.
- Consistência: Garante que o ambiente de execução seja sempre o mesmo, independentemente de onde a imagem é executada.
- Portabilidade: A imagem criada a partir de um Dockerfile pode ser distribuída e executada em qualquer máquina que suporte Docker.

## Exemplo de Dockerfile
```

# Usando a imagem base do Ubuntu
FROM ubuntu

# Instalar pacotes necessários
RUN apt-get update && apt-get install -y python3

# Definir o diretório de trabalho
WORKDIR /app

# Copiar os arquivos da aplicação para o contêiner
COPY . /app

# Instalando dependências
RUN pip install --no-cache-dir -r requirements.txt

# Expondo a porta que a aplicação irá usar
EXPOSE 8000

# Comando a ser executado ao iniciar o contêiner
CMD ["python3", "app.py"]
```

### Construa a Imagem: Use o comando docker build para construir a imagem a partir do Dockerfile:
```
docker build -t minha-imagem .
```
O -t permite que você nomeie a imagem, e o . indica que o Dockerfile está no diretório atual.

### Execute um Contêiner: Use o comando docker run para criar e executar um contêiner a partir da imagem criada:
```
docker run -p 8000:8000 minha-imagem
```
O -p 8000:8000 mapeia a porta 8000 do contêiner para a porta 8000 do host.

### comando que para os conteineres:

```
docker compose down
```