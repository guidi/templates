# 🐳 guidi/debian-tools

Imagem Docker leve baseada no `debian:bullseye-slim` com ferramentas essenciais de rede, ideal para testes de conectividade entre containers, depuração de DNS e acesso a bancos de dados MySQL em ambientes como Docker Swarm ou Kubernetes.

---

## 🔧 Ferramentas incluídas

- `curl` – Requisições HTTP
- `ping` – Teste de conectividade ICMP
- `iproute2` – Comando `ip`, `ss` e outros para rede
- `traceroute` – Rastreamento de rotas até destino
- `dnsutils` – Ferramentas como `dig`, `nslookup`
- `default-mysql-client` – Cliente MySQL CLI

---

## 📦 Como usar

### Local (Docker)

```bash
docker run -it --rm guidi/debian-tools bash
```

### Docker Swarm

```bash
docker service create \
  --name net-test \
  --network sua-rede-overlay \
  -it guidi/debian-tools bash
```

---

## 🧪 Exemplos de comandos

```bash
curl http://servico-interno
ping 8.8.8.8
dig google.com
mysql -h host-do-mysql -u root -p
```

---

## 📄 Dockerfile

Veja o conteúdo completo do Dockerfile neste repositório: [Dockerfile](./Dockerfile)

---

## 📥 Pull da imagem

A imagem está disponível no Docker Hub:

```bash
docker pull guidi/debian-tools:latest
```

---

## 🧑‍💻 Autor

Vanderson Guidi  
[https://github.com/guidi](https://github.com/guidi)
