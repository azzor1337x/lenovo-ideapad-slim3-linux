# Pós-instalação Linux (Debian / LMDE)

Este guia descreve os passos recomendados de **pós-instalação** para sistemas Linux baseados em Debian
(com foco em **Debian 13** e **LMDE 7**), especialmente em notebooks **Lenovo IdeaPad Slim 3 15ARP10**
e hardware AMD semelhante.

O objetivo é garantir **estabilidade**, **compatibilidade de hardware**, **suporte gráfico completo**
e um ambiente pronto para uso diário e desenvolvimento.

---

## 1️⃣ Atualizar o sistema

Antes de instalar novos pacotes, certifique-se de que o sistema está atualizado:

```bash
sudo apt update
sudo apt full-upgrade -y
```

---

## 2️⃣ Microcode e firmwares essenciais

Instalação dos pacotes recomendados:

```bash
sudo apt install -y \
  amd64-microcode \
  firmware-linux \
  firmware-linux-nonfree \
  firmware-misc-nonfree
```

### O que cada pacote faz

* **amd64-microcode**: atualizações de microcódigo para CPUs AMD, corrigindo bugs e melhorando estabilidade
* **firmware-linux**: firmwares essenciais para diversos dispositivos
* **firmware-linux-nonfree**: firmwares proprietários (Wi‑Fi, GPU, etc.)
* **firmware-misc-nonfree**: firmwares adicionais para hardware específico

> ⚠️ É necessário que o repositório **non-free-firmware** esteja habilitado.

---

## 3️⃣ Suporte gráfico (Mesa, OpenGL e Vulkan)

Instale os drivers gráficos e ferramentas de verificação:

```bash
sudo apt install -y \
  mesa-vulkan-drivers \
  mesa-utils \
  vulkan-tools
```

### Componentes instalados

* **Mesa**: implementação open source de OpenGL e Vulkan
* **mesa-vulkan-drivers**: suporte Vulkan para GPUs AMD
* **mesa-utils**: utilitários como `glxinfo`
* **vulkan-tools**: ferramentas como `vulkaninfo`

---

## 4️⃣ Verificações pós-instalação

### Verificar microcode carregado

```bash
dmesg | grep microcode
```

### Verificar OpenGL

```bash
glxinfo | grep "OpenGL renderer"
```

### Verificar Vulkan

```bash
vulkaninfo | less
```

Se os comandos retornarem informações válidas, o suporte gráfico está funcionando corretamente.

---

## 5️⃣ Reinicialização

Após a instalação dos pacotes e microcode, recomenda-se reiniciar o sistema:

```bash
sudo reboot
```

---

## ⚠️ Observações importantes

* Para CPUs **Intel**, substitua `amd64-microcode` por `intel-microcode`
* Mensagens ACPI no boot podem ocorrer e nem sempre indicam erro crítico
* Manter o kernel e a BIOS atualizados ajuda na estabilidade

---

## 📎 Notas finais

Este guia serve como base inicial de pós-instalação.
Outros ajustes (Docker, VS Code, ambiente de desenvolvimento) são documentados
em diretórios específicos deste repositório.

Contribuições e melhorias são bem-vindas 🙂
