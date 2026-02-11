# Lenovo IdeaPad Slim 3 (15ARP10) – Guia Linux

Este repositório documenta o processo de **pós-instalação**, ajustes de **firmware**, **drivers gráficos**, ambiente de **desenvolvimento** e **containers** para notebooks **Lenovo IdeaPad Slim 3 15ARP10** (MTM 83MM) e modelos com hardware semelhante.

O objetivo é fornecer um **guia reprodutível**, organizado e baseado em boas práticas para usuários Linux que desejam estabilidade, desempenho e um ambiente pronto para uso diário, desenvolvimento e homelab.

---

## 📑 Índice

* [🎯 Objetivo do projeto](#-objetivo-do-projeto)
* [💻 Hardware testado](#-hardware-testado)
* [🐧 Sistemas testados](#-sistemas-testados)
* [📁 Estrutura do repositório](#-estrutura-do-repositório)

### 📘 Documentação

* [🖥️ Informações de Hardware – IdeaPad Slim 3 15ARP10](hardware/ideapad-slim-3-15arp10.md)
* [⚙️ Pós-instalação – Debian / LMDE](post-install/debian-lmde.md)

### 🧰 Ambiente e Ferramentas

* [🐳 Docker, Docker Compose e Portainer](docker/)
* [🧑‍💻 Ambiente de Desenvolvimento](dev/)

### 📄 Outros

* [📐 Template de documentação](docs/TEMPLATE.md)
* [🤝 Contribuições](#-contribuições)
* [📜 Licença](#-licença)

---

## 🎯 Objetivo do projeto

* Documentar passo a passo o pós-instalação do Linux
* Facilitar a vida de outros usuários com hardware semelhante
* Centralizar ajustes comuns (microcode, firmware, Mesa, Vulkan)
* Padronizar ambiente de desenvolvimento (VS Code, Docker, Portainer)
* Servir como base para troubleshooting e evolução comunitária

---

## 💻 Hardware testado

* **Modelo:** Lenovo IdeaPad Slim 3 15ARP10
* **Machine Type (MTM):** 83MM
* **CPU:** AMD Ryzen
* **GPU:** AMD (Mesa / Vulkan)
* **Firmware:** UEFI / ACPI
* **BIOS:** QBCN29WW (1.29 – Jan/2026)

> Outros modelos podem funcionar, mas este repositório é focado neste hardware específico.

---

## 🐧 Sistemas testados

* Debian 13 (Trixie)
* LMDE 7
* Outras distribuições Debian-based (não garantido)

---

## 📁 Estrutura do repositório

```text
lenovo-ideapad-slim3-linux
├── README.md
├── hardware/        # Informações e especificações do notebook
├── post-install/    # Guias de pós-instalação (firmware, Mesa, Vulkan)
├── docker/          # Docker, Docker Compose e Portainer
├── dev/             # Ambiente de desenvolvimento (VS Code, etc.)
├── docs/            # Templates e documentação auxiliar
└── scripts/         # Scripts auxiliares (coleta de informações, checks)
```

---

## ⚠️ Observações importantes

* Alguns pacotes exigem que o repositório **non-free-firmware** esteja habilitado
* Recomenda-se manter o sistema e a BIOS sempre atualizados
* Ajustes de ACPI e kernel podem variar conforme versão do Linux
* Sempre reinicie o sistema após atualizações críticas de firmware ou microcode

---

## 🤝 Contribuições

Contribuições são bem-vindas!

* Issues para relatar problemas ou melhorias
* Pull Requests para adicionar suporte a modelos semelhantes
* Documentação adicional ou correções

Ao contribuir, informe:

* Modelo do notebook
* Versão do kernel
* Distribuição utilizada

---

## 📜 Licença

Este repositório é distribuído para fins educacionais e colaborativos.

Use por sua conta e risco 🙂
