# Nginx Proxy 🚀
Compose com a combinação das imagens do Nginx + Docker-Gen + Acme Companion.

Nginx-Proxy é um serviço que usa o nginx como proxy reverso para os containers rodando em um host. -> [Nginx Proxy](https://hub.docker.com/r/nginxproxy/nginx-proxy)<br>
Docker Gen é um serviço responsável por gerar alguns templates de dados baseados em metadados de um container. -> [Docker Gen](https://hub.docker.com/r/nginxproxy/docker-gen)<br>
Acme Companion é um serviço responsável por gerar e gerenciar certificados SSL LetsEncrypt para os containers que estão sendo proxyados. -> [Acme Companion](https://hub.docker.com/r/nginxproxy/acme-companion)<br>

Para maiores detalhes do uso desse compose visite este post do meu blog: [Post](https://blog.vandersonguidi.com.br/tutoriais/fazendo-deploy-de-keycloak-v17-em-container-docker-com-nginx-como-proxy-reverso-ssl-com-letsencrypt/)<br>
