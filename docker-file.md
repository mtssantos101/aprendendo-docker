# exemplo de dockerfile

# Usando a imagem base do Ubuntu
FROM ubuntu

# Instalar pacotes necessários
RUN apt-get update && apt-get install -y python3

# Definir o diretório de trabalho
WORKDIR /app

# Copiar os arquivos da aplicação para o contêiner
COPY . /app

# Comando a ser executado ao iniciar o contêiner
CMD ["python3", "app.py"]
