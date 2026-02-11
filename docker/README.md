# Docker, Docker Compose e Portainer

Este diretório documenta a instalação e configuração do **Docker Engine**, **Docker Compose (plugin v2)** e **Portainer**
em sistemas Linux baseados em Debian (Debian 13 / LMDE 7), com foco em notebooks **Lenovo IdeaPad Slim 3 15ARP10** e hardware semelhante.

O objetivo é fornecer um ambiente confiável para **containers**, **homelab**, **desenvolvimento** e **serviços locais**.

---

## 📌 Escopo

Este guia cobre:

* Instalação do Docker Engine (repositório oficial)
* Docker Compose (plugin)
* Portainer (UI web para Docker)
* Boas práticas iniciais

---

## 🖥️ Ambiente testado

* **Distribuição:** Debian 13 (Trixie) / LMDE 7
* **Arquitetura:** amd64
* **Kernel:** Linux 6.12.x
* **Init:** systemd

---

## 1️⃣ Preparação do sistema

Atualizar o sistema e instalar dependências básicas:

```bash
sudo apt update
sudo apt install -y ca-certificates curl gnupg lsb-release
```

---

## 2️⃣ Adicionar repositório oficial do Docker

Criar diretório de keyrings:

```bash
sudo install -d -m 0755 /etc/apt/keyrings
```

Adicionar chave GPG do Docker:

```bash
sudo curl -fsSL https://download.docker.com/linux/debian/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc
```

Adicionar repositório:

```bash
sudo tee /etc/apt/sources.list.d/docker.list <<EOF
deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/debian trixie stable
EOF
```

Atualizar índices:

```bash
sudo apt update
```

---

## 3️⃣ Instalar Docker Engine e plugins

```bash
sudo apt install -y \
  docker-ce \
  docker-ce-cli \
  containerd.io \
  docker-buildx-plugin \
  docker-compose-plugin
```

---

## 4️⃣ Executar Docker sem sudo

Criar grupo (se necessário):

```bash
sudo groupadd docker
```

Adicionar usuário:

```bash
sudo usermod -aG docker $USER
```

Aplicar grupo sem logout:

```bash
newgrp docker
```

---

## 5️⃣ Testar instalação

```bash
docker run hello-world
```

---

## 6️⃣ Instalar Portainer

Criar volume persistente:

```bash
docker volume create portainer_data
```

Subir container:

```bash
docker run -d \
  -p 8000:8000 \
  -p 9443:9443 \
  --name portainer \
  --restart=always \
  -v /var/run/docker.sock:/var/run/docker.sock \
  -v portainer_data:/data \
  portainer/portainer-ce:lts
```

Acessar:

```text
https://localhost:9443
```

---

## ⚠️ Observações

* Docker inicia automaticamente via systemd
* Para produção, configure firewall e TLS
* Ajuste a versão do Debian no repositório se necessário

---

## 📎 Referências

* [https://docs.docker.com/](https://docs.docker.com/)
* [https://docs.portainer.io/](https://docs.portainer.io/)
