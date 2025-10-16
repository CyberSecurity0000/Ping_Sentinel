# 🎯 Ping-Sentinel: Varredura ICMP Tática em C

[![Status](https://img.shields.io/badge/status-experimental-orange)](https://github.com/SEU_USUARIO/Ping-Sentinel)
[![License](https://img.shields.io/badge/license-MIT-blue)](LICENSE)

**Foco Tático:** Scanner ICMP (`ping`) ultra-rápido para enumeração de *hosts* ativos em sub-redes Classe C (`/24`). Essencial para a fase de **Reconhecimento Ativo**. 🕵️‍♂️

---

## 🛠️ Utilidade Hacker (Os 2 Binários)

Dois programas em C para descobrir hosts ativos numa sub-rede `/24` usando ICMP.

| Binário | Funcionalidade Essencial | Tática (Estilo Hacker) |
| :--- | :--- | :--- |
| **`scanner_autogen.c`** | Varre `0..254`. Base (`192.168.0`, ex.) **hardcoded** para uso rápido em *labs* isolados. | **Ataque Interno:** Ideal para ambientes *sandbox* ou testes onde a rede base é fixa e o *setup* é instantâneo. |
| **`ping_arg.c`** | Varre `.1..254`. Recebe a **base de rede como argumento** (Ex: `./ping_arg 10.0.2`). | **Ataque Adaptável:** Flexibilidade para diferentes sub-redes de clientes ou cenários de *pentest* dinâmicos. |

---

## ⚠️ Aviso: Labs, Ética e Metodologia

**Uso Exclusivo para *Labs* (Estudo, Pentest Ético e Revisão).**

*O uso desta ferramenta fora de um **escopo autorizado (com consentimento legal e explícito)** é **invasão** e de total responsabilidade do usuário. Seja sempre **metódico (MrRobot)** no escopo e na intenção.*

---

## 📂 Conteúdo do Repositório

- `scanner_autogen.c`
- `ping_arg.c`
- `README.md` (Este arquivo)
- `LICENSE`

---

## ⚙️ Pré-requisitos (Build Essencial)

- **Sistema:** Linux/macOS.
- **Compilador:** `gcc`. (Se faltar: `sudo apt update && sudo apt install build-essential -y`)
- **Dependência:** O binário `ping` deve suportar *flags* `-c` (contagem) e `-W` (*timeout*).

---

## 🚀 Compilação Ultra-Direta

Execute os comandos abaixo no seu terminal para gerar os binários executáveis:

```bash
# Compilação otimizada (-O2) para scanner_autogen
gcc -Wall -O2 -o scanner_autogen scanner_autogen.c

# Compilação otimizada (-O2) para ping_arg
gcc -Wall -O2 -o ping_arg ping_arg.c
