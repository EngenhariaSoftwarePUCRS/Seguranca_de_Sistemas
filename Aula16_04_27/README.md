# Resumo e Questões - Segurança de Sistemas

## Resumo Geral da Disciplina

### Conceitos Fundamentais

Segurança de Sistemas é uma disciplina que aborda os desafios de proteger aplicações e infraestruturas contra ameaças cibernéticas. A disciplina cobre tanto aspectos defensivos quanto ofensivos, com foco em identificar, analisar e mitigar riscos de segurança.

#### Definição de Risco

A métrica fundamental para avaliar segurança é:

$$Risco = Probabilidade \times Impacto$$

Em vez de focar apenas em vulnerabilidades, a indústria moderna trabalha com risco, pois permite comunicação comum com negócios através de impacto financeiro.

### Fases de um Ataque

1. **Reconhecimento**
   - Passivo: coleta de informações públicas (notícias, redes sociais)
   - Ativo: envio de sinais que podem alertar a vítima (Wi-Fi falsos, etc.)

2. **Mapeamento de Superfície de Ataque**
   - Identificação de tecnologias utilizadas
   - Busca de vulnerabilidades conhecidas (CVE)

3. **Exploração**
   - Execução do ataque com conhecimento razoável do alvo

4. **Pós-Exploração**
   - Consolidação do acesso

### Metodologias e Frameworks

#### OWASP Top 10 (OSSTMM)

Matriz de conhecimento entre atacante e alvo:

- **Ataque Cego**: Atacante e alvo com pouco conhecimento um do outro
- **Ataque de Reconhecimento**: Atacante com algum conhecimento
- **Ataque de Exploração**: Atacante com conhecimento razoável
- **Ataque de Pós-Exploração**: Atacante com conhecimento profundo

**Princípio importante**: Tu garantes que não há vulnerabilidade naquilo que testaste, baseado nas técnicas que empregaste.

#### Avaliação de Vulnerabilidades

**CVSS (Common Vulnerability Scoring System)**
- Escala de 0 a 10
- Considera: impacto, facilidade de exploração, complexidade do ataque
- Ajuda priorização de mitigações

**EPSS (Exploit Prediction Scoring System)**
- Modelo de previsão de exploração
- Combina: gravidade, facilidade de exploração, disponibilidade de exploits
- Calcula probabilidade de uma vulnerabilidade ser explorada

**DREAD**
- Damage (Dano)
- Reproducibility (Reprodutibilidade)
- Exploitability (Explorabilidade)
- Affected Users (Usuários Afetados)
- Discoverability (Descoberta)

### Modelagem de Ameaças

Processo que define:
- Quais problemas podem ocorrer
- Quais as vulnerabilidades
- Quais os ataques possíveis
- Qual o impacto de cada ameaça

#### Matriz de Risco

| Intervalo | Classificação |
|---|---|
| 1 a 5 | Baixo |
| 6 a 10 | Médio |
| 11 a 15 | Alto |
| 16 a 25 | Crítico |

### Segurança Ofensiva vs Defensiva

#### Atividades Defensivas
- Testes de Segurança (Pentest)
- Auditoria
- Análise de Vulnerabilidades
- Forense

#### Atividades Ofensivas
- CTF (Capture the Flag): Hack The Box, TryHackMe
- Bug Bounty: HackerOne, Intigriti
- Pesquisa de Segurança

### Reconhecimento Detalhado (portas, domínios, diretórios)

- **Portas e serviços**: identificar portas TCP/UDP abertas; priorizar serviços expostos (ex.: SSH, RDP, HTTP/HTTPS, SMB). Técnicas e flags comuns do `nmap`:
   - `-sS` (SYN scan), `-sT` (connect), `-sU` (UDP), `-sV` (versão), `-p-` (todas as portas), `-T4` (velocidade)
   - Ex.: `nmap -sS -p- -T4 --open -oA scan <alvo>`; `nmap -sV --script=vuln <alvo>` para checagens básicas.

- **Domínios e subdomínios**: enumeração DNS, descoberta de subdomínios (amass, subfinder), análise de certificados (crt.sh), tentativas de `zone transfer` (AXFR) quando aplicável.

- **Diretórios e arquivos web**: enumeração de diretórios e endpoints com `gobuster`, `dirb`, `wfuzz`; buscar arquivos sensíveis (`.env`, backups, endpoints de admin).

- **Boas práticas de reconhecimento**:
   - Começar com técnicas passivas antes de varreduras ativas.
   - Usar varreduras leves e depois aprofundar nas áreas relevantes.
   - Registrar evidências (outputs, capturas) para análise e rastreabilidade.

### Ferramentas de Exploração (resumo)

- **Metasploit Framework**: exploração, módulos auxiliares, pós-exploração.
- **Burp Suite**: proxy, scanner, intruder, repeater — principal ferramenta para testes web.
- **sqlmap**: automação para SQLi.
- **Hydra/Medusa**: força bruta em serviços de autenticação.
- **John / Hashcat**: ataque a hashes.
- **CrackMapExec, BloodHound**: exploração e mapeamento em redes Active Directory.

### Pós-Exploração

- **Objetivos comuns**: manter persistência, escalar privilégios, movimentação lateral, coleta e exfiltração de dados, manutenção de acesso.
- **Técnicas e ferramentas**:
   - Persistência: criação de serviços, scheduled tasks, entradas em startup, backdoors.
   - Credenciais: captura e extração (ex.: Mimikatz), reutilização e pivot.
   - Movimentação lateral: uso de SMB, WMI, RDP, SSH, pass-the-hash, remote execution.
   - Ferramentas: Meterpreter (post modules), Mimikatz, CrackMapExec, PowerShell Empire (uso responsável).
- **Contenção e limpeza**: coordenação para evitar destruição de evidências; registrar ações para relatório.

### Perspectiva Blue Team (detecção e resposta)

- **Detecção**: logs de autenticação, EDR/AV alerts, IDS/IPS, SIEM correlation, anomalias de rede e processos.
- **Controles**: habilitar MFA, segmentação de rede, least privilege, hardening de serviços, monitoramento de integridade.
- **Resposta a incidentes**: coleta de evidências, isolamento, erradicação, recuperação, lições aprendidas.


### Avaliação de Risco ligada a Testes

- Ao reportar resultados de testes, mapear descobertas para **probabilidade x impacto** (matriz de risco) e usar métricas como CVSS/EPSS para priorizar correções.
- Definir controles compensatórios e estimar o risco residual após mitigação.
- Gerar relatórios que traduzam achados técnicos em impacto de negócio para stakeholders.

---

## Questões para Autoavaliação

### Conceitos Básicos

1. **O que diferencia um ataque passivo de um ataque ativo durante a fase de reconhecimento?**
   - Cite exemplos práticos de cada um.

2. **Por que a indústria de cybersegurança migrou do conceito de "vulnerabilidade" para "risco"?**
   - Como isso impacta a comunicação com stakeholders?

3. **Explique a fórmula $Risco = Probabilidade \times Impacto$ com um exemplo prático.**
   - O que acontece se o impacto é alto mas a probabilidade é muito baixa?

### Metodologias e Avaliação

4. **Qual é a diferença entre CVSS, EPSS e DREAD?**
   - Em quais cenários você usaria cada uma?

5. **Na matriz de conhecimento do atacante vs alvo:**
   - Um ataque de "Pós-Exploração" é necessariamente mais perigoso que um "Ataque Cego"? Por quê?

6. **O que significa a afirmação: "Tu garantes que não tem vulnerabilidade naquilo que tu testou"?**
   - Quais as limitações dessa garantia?

### Modelagem de Ameaças

7. **Descreva um cenário de ameaça para uma aplicação que você conhece bem.**
   - Identifique: ativos, ameaças, vulnerabilidades, impacto e probabilidade.

8. **Como você priorizaria vulnerabilidades em uma aplicação web?**
   - Que critérios você consideraria (além do CVSS)?

9. **Em uma modelagem de ameaças, qual é mais crítico:**
   - Uma ameaça com probabilidade 5 e impacto 5?
   - Uma ameaça com probabilidade 1 e impacto 25?
   - Justifique sua resposta.

### Aplicação Prática

10. **Você encontra uma aplicação web usando Java 6 (versão muito antiga).**
    - Como você procederia com o reconhecimento?
    - Onde buscaria informações sobre vulnerabilidades conhecidas?

11. **Descreva o fluxo completo de um teste de segurança (pentest) desde o reconhecimento até a pós-exploração.**

12. **Em um estudo de caso real:**
    - Como você diferenciaria entre risco de comprometimento de credenciais por phishing vs ataque de um administrador interno malicioso?
    - Qual teria prioridade? Por quê?

### Estratégia e Pensamento Crítico

13. **Qual é o papel de plataformas como Hack The Box e TryHackMe na formação de profissionais de segurança?**

14. **Um programa de Bug Bounty é sempre benéfico para uma organização? Quais os riscos e benefícios?**

15. **Como você explicaria para um executivo por que investir em segurança defensiva é importante, usando conceitos de risco?**

16. **Qual é a relação entre segurança ofensiva (pentest, CTF) e segurança defensiva?**
    - Por que um profissional de segurança precisa entender ambos os lados?

### Questões para Discussão em Aula

17. **Caso Inter Imenso:**
    - Por que o comprometimento de backup teve nível crítico (20) enquanto o acesso por phishing foi crítico (16)?
    - Como você mitigaria cada um desses cenários?

18. **Engenharia Social vs Exploração Técnica:**
    - Qual é mais difícil de defender? Por quê?

19. **Rastreabilidade e Auditoria:**
    - Como você garantiria que um administrador interno não conseguisse apagar logs de auditoria de forma undetectável?

20. **Evolução de Ataques:**
    - Como o conhecimento do atacante sobre o alvo evolui ao longo do tempo?
    - Como isso deveria influenciar sua estratégia defensiva?

---

## Tópicos para Aprofundamento

- [ ] Estudar em profundidade o OWASP Top 10
- [ ] Praticar modelagem de ameaças em projetos reais
- [ ] Realizar labs no TryHackMe ou HackTheBox
- [ ] Estudar análise forense de segurança
- [ ] Aprofundar em criptografia e autenticação
- [ ] Entender legislações (LGPD, GDPR, etc.)

---

## Referências e Recursos

- **OWASP**: https://owasp.org
- **NVD (CVE Database)**: https://nvd.nist.gov
- **CVSS Calculator**: https://www.first.org/cvss/calculator/3.1
- **Hack The Box**: https://www.hackthebox.com
- **TryHackMe**: https://tryhackme.com
- **HackerOne**: https://www.hackerone.com
- **Intigriti**: https://www.intigriti.com
