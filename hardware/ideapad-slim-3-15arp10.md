# Lenovo IdeaPad Slim 3 15ARP10 – Informações de Hardware

Este documento descreve as informações de hardware, firmware e sistema do **Lenovo IdeaPad Slim 3 15ARP10**,
servindo como referência para suporte, troubleshooting e comparação com outros modelos semelhantes.

---

## 📌 Identificação do equipamento

* **Fabricante:** Lenovo
* **Modelo comercial:** IdeaPad Slim 3 15ARP10
* **Machine Type (MTM):** 83MM
* **Família:** IdeaPad Slim 3
* **SKU:** LENOVO_MT_83MM_BU_idea_FM_IdeaPad Slim 3 15ARP10

---

## 🧠 Processador e arquitetura

* **Arquitetura:** x86_64
* **CPU:** AMD Ryzen (família AMD64)
* **Microcode:** amd64-microcode

> Recomenda-se manter o pacote `amd64-microcode` sempre atualizado.

---

## 🎮 Gráficos

* **GPU:** AMD (integrada)
* **Driver:** Mesa
* **APIs suportadas:** OpenGL / Vulkan
* **Pacotes relevantes:**

  * mesa-vulkan-drivers
  * mesa-utils
  * vulkan-tools

---

## 🧩 Firmware / BIOS

* **Vendor:** Lenovo
* **Versão da BIOS:** QBCN29WW
* **Revisão:** 1.29
* **Firmware Revision:** 1.26
* **Data de release:** 15/01/2026
* **Modo de boot:** UEFI
* **ACPI:** Ativo

---

## 🐧 Sistema operacional

* **Distribuição:** Debian-based (Debian 13 / LMDE 7)
* **Kernel:** Linux 6.12.x
* **Gerenciador de boot:** systemd-boot / GRUB (dependendo da instalação)

---

## 🔎 Comandos de identificação

Os comandos abaixo foram utilizados para coletar as informações acima:

```bash
uname -a

sudo dmidecode -s system-manufacturer
sudo dmidecode -s system-product-name
sudo dmidecode -s system-serial-number

sudo dmidecode -t system
sudo dmidecode -t bios
```

---

## ⚠️ Observações conhecidas

* Alguns kernels podem apresentar **mensagens ACPI** no boot (BIOS-related)
* Manter BIOS atualizada ajuda a reduzir warnings de ACPI
* Suspend / Resume pode variar conforme versão do kernel

---

## 📎 Notas finais

Este documento pode ser usado como base para:

* abertura de chamados junto ao suporte Lenovo
* comparação de comportamento entre kernels
* contribuição de outros usuários com hardware semelhante

Contribuições são bem-vindas 🙂
