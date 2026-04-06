## Recon Ativo

### Varredura de Diretórios, Arquivos e Subdomínios (Exploração)

Ex `subdominio.dominio.com`

Com base em uma wordlist como:
- `www`
- `mail`
- `dev`
- `test`
- `admin`

Ferramentas como:
- `dirbuster`
- `gobuster`
- `feroxbuster`
- `ffuf`
- `findomain`
- `amass`
- `subfinder`

## Modelagem de Ameaças

Sempre pensar em um _agente_ de ameaças que faz _algo_ com alguma _motivação_

Agente: Atacante malicioso externo

Agente: Estagiário

Agente: Insider (funcionário)

Agente: APT (Advanced Persistent Threat)

### STRIDE

#### Spoofing (Falsificação)

Relacionado o princípio da autenticidade

#### Tampering

Relacionado ao princípio da integridade

#### Repudiation

Relacionado ao princípio do não repúdio

#### Information Disclosure

Relacionado ao princípio da confidencialidade

#### Denial of Service

Relacionado ao princípio da disponibilidade

#### Elevation of Privilege

Relacionado ao princípio da privilégios

### Evento de ameaça (exemplo)

Acessar um site de bet, tentar depositar R$ 5, ficar clicando no botão de depósito (que só parece desabilitado) e o site retira apenas os R$ 5 mas o usuário recebe por cada clique.

Se um dos 3 funcionários sem querer subir um backup do banco que está comprometido, e os outros 2 não se ligarem e realizarem os backups subsequentes baseados nesse corrompido, como eles não tem testes de integridade e recuperação eles podem perder muitos dados por um grande intervalo e só perceber ao tentar recuperá-los.

### DREAD

#### Damage

Very high

#### Reproducibility

High

#### Exploitability

Very Low

#### Affected Users

Very high (All)

#### Discoverability

Low (Which is bad)
