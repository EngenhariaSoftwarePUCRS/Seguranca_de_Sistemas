## Reconhecimento Ativo

- Coleta de informações
- Varredura
- Enumerção

### Varredura de portas

TCP

3- Way Handshake (3WHS)

1. O cliente envia um pacote SYN para o servidor.
2. O servidor responde com um pacote SYN-ACK.
3. O cliente responde com um pacote ACK, estabelecendo a conexão.

#### Exemplos

| Port | Service |
|------|---------|
| 21   | FTP     |
| 22   | SSH     |
| 25   | SMTP    |
| 53   | DNS     |
| 80   | HTTP    |
| 443  | HTTPS   |
| 3306 | MySQL   |
| 3389 | RDP     |

#### Nmap

```sh
# Varredura de portas TCP
nmap 192.168.0.2
nmap 127.0.0.1
```

- `nmap -sS [-p <portas>] <IP>`: Varredura TCP SYN (stealth scan)
- `nmap -sT <IP>`: Varredura TCP connect
- `nmap -sV -p 21,80,3389 <IP>`: Varredura de portas específicas e detecção de serviços
- `nmap -sV -sC -p <portas> <IP>`: Varredura de portas com scripts de detecção de vulnerabilidades

#### Técnicas de Evasão

-T1
-T5
-D

### Outras ferramentas

- NAABU
- RustScan
- [TryHackMe](https://tryhackme.com/room/portscan)
