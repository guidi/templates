FROM debian:bullseye-slim

LABEL maintainer="Vanderson Guidi"
LABEL description="Imagem Debian slim com ferramentas de rede e cliente MySQL para testes em containers e clusters"
LABEL version="1.0"

ENV DEBIAN_FRONTEND=noninteractive

# Atualiza pacotes e instala ferramentas de rede e o mysql-client
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
      curl \
      iputils-ping \
      iproute2 \
      traceroute \
      dnsutils \
      default-mysql-client && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Mantém o container vivo para testes interativos
CMD ["sleep", "infinity"]
