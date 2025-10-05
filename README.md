# ping-sentinel — Ping Scanner — 2 utilitários em C

[![Status](https://img.shields.io/badge/status-experimental-orange)](https://github.com)  
[![License](https://img.shields.io/badge/license-MIT-blue)](LICENSE)

**Descrição curta:** Dois programas em C para descobrir hosts ativos numa sub‑rede `/24` usando ICMP (ping).  
- `scanner_autogen.c` — gera internamente a base (`IP_BASE`, ex.: `192.168.0`) e varre `0..254`.  
- `ping_arg.c` — recebe a base de rede como argumento (ex.: `./ping_arg 10.0.2`) e varre `.1..254`.

> ⚠️ **Só execute em redes que você administra ou tem permissão explícita.** Varredura sem autorização é ilegal/antiética.

---

## Repositório
- `scanner_autogen.c`  
- `ping_arg.c`  
- `README.md` (este arquivo)

---

## Pré-requisitos
- Linux/macOS com `gcc`.  
- `ping` com flags `-c` (contar) e `-W` (timeout).  
Se faltar `gcc`: `sudo apt update && sudo apt install build-essential -y`.

---

## Compilar
```bash
gcc -Wall -O2 -o scanner_autogen scanner_autogen.c
gcc -Wall -O2 -o ping_arg ping_arg.c
