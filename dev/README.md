
# Guia: Instalação VS Code

> Este guia descreve como instalar o Visual Studio Code em sistemas Linux baseados em Debian/Ubuntu
> (ex: Ubuntu, Linux Mint, LMDE).

---

## 1. Preparação do ambiente e VS Code

### 1.1 Atualizar o sistema

```bash
sudo apt update
sudo apt upgrade -y
```

---

### 1.2 Instalar dependências básicas

```bash
sudo apt install wget gpg apt-transport-https -y
```

---

### 1.3 Instalar o Visual Studio Code

Adicionar a chave da Microsoft:

```bash
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
sudo install -D -o root -g root -m 644 microsoft.gpg /usr/share/keyrings/microsoft.gpg
rm -f microsoft.gpg
```

> A chave GPG é usada para garantir que os pacotes instalados sejam assinados e confiáveis.

Adicionar o repositório:

```bash
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/microsoft.gpg] https://packages.microsoft.com/repos/code stable main" | sudo tee /etc/apt/sources.list.d/vscode.list
```

> O parâmetro `signed-by` garante que apenas pacotes assinados pela Microsoft sejam aceitos.

Atualizar e instalar:

```bash
sudo apt update
sudo apt install code -y
```

Verificar instalação:

```bash
code --version
```

---

## 2. Criar a estrutura do projeto

Criar a pasta do projeto via terminal:

```bash
mkdir -p ~/primeiro-projeto
cd ~/primeiro-projeto
```

Abrir o VS Code na pasta do projeto:

```bash
code .
```

---
