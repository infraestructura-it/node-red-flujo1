# Imagen base de Ubuntu
FROM ubuntu:22.04

# Evita preguntas interactivas al instalar paquetes
ENV DEBIAN_FRONTEND=noninteractive

# Instala Node.js, npm y herramientas básicas
RUN apt-get update && \
    apt-get install -y curl gnupg iputils-ping net-tools traceroute && \
    curl -fsSL https://deb.nodesource.com/setup_18.x | bash - && \
    apt-get install -y nodejs && \
    npm install -g --unsafe-perm node-red && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Directorio de trabajo
WORKDIR /data

# Expone el puerto por defecto de Node-RED
EXPOSE 1880

# Comando por defecto
CMD ["node-red"]

