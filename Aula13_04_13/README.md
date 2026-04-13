Questionário

Resposta

Análise

[R1, R2, R3, R4, R5, R6]

Matrizes de Risco (= Probabilidade x Impacto)

EPSS (Exploit Prediction Scoring System) é um modelo de previsão de exploração de vulnerabilidades, desenvolvido pela FIRST (Forum of Incident Response and Security Teams). Ele utiliza uma combinação de fatores, como a gravidade da vulnerabilidade, a facilidade de exploração e a disponibilidade de exploits, para calcular uma pontuação que indica a probabilidade de uma vulnerabilidade ser explorada por atacantes.

CVSS (Common Vulnerability Scoring System) é um padrão aberto para avaliar a gravidade das vulnerabilidades de segurança em sistemas de software. Ele atribui uma pontuação numérica de 0 a 10, com base em vários fatores, como o impacto da vulnerabilidade, a facilidade de exploração e a complexidade do ataque. A pontuação CVSS ajuda as organizações a priorizar as vulnerabilidades e tomar decisões informadas sobre como mitigá-las.

---


## Modelagem de Ameaças - Estudo de Caso Inter Imenso

### Escala usada

- DREAD: 1 (baixo) a 10 (alto)
- Matriz de risco: Probabilidade (1 a 5) x Impacto (1 a 5)

- Classificação:
	- 1 a 5 = Baixo
	- 6 a 10 = Médio
	- 11 a 15 = Alto
	- 16 a 25 = Crítico

### Evento de ameaça 1 

Um dos 3 administradores executa restauração de backup comprometido no PostgreSQL local. Os próximos backups diários passam a replicar a base corrompida sem detecção, pois não há evidência de teste de restauração e validação de integridade.

### DREAD

- Damage: 9
- Reproducibility: 8
- Exploitability: 5
- Affected Users: 9
- Discoverability: 6
- Score médio: 7.4/10

### Matriz de Risco

| Probabilidade | Impacto | Nível |
|---|---|---|
| 4 | 5 | 20 (Crítico) |

### Janela temporal do evento 1

- 0 a 24h: risco de propagação da corrupção de dados para novos backups.
- A partir do 7º dia: aumento do esforço de recuperação e possível indisponibilidade parcial de históricos.
- A partir do 30º dia: impacto acumulado em confiabilidade de laudos e risco reputacional elevado.

### Evento de ameaça 2

Credenciais de cliente são comprometidas via phishing e o atacante burla o 2FA por engenharia social (ex.: troca de SIM/chip). Com isso, acessa e baixa laudos periciais sensíveis na plataforma de resultados.

### DREAD

- Damage: 8
- Reproducibility: 7
- Exploitability: 6
- Affected Users: 7
- Discoverability: 7
- Score médio: 7.0/10

### Matriz de Risco

| Probabilidade | Impacto | Nível |
|---|---|---|
| 4 | 4 | 16 (Crítico) |

### Janela temporal do evento 2

- 0 a 24h: possível acesso indevido a laudos sensíveis por conta comprometida.
- A partir do 7º dia: expansão do impacto para mais contas sem reforço de monitoramento e resposta.
- A partir do 30º dia: risco de questionamentos jurídicos e perda de confiança dos clientes afetados.

### Evento de ameaça 3

Um administrador interno com privilégio total altera ou apaga laudos e registros de auditoria para favorecer terceiros, comprometendo integridade e rastreabilidade dos dados.

### DREAD

- Damage: 10
- Reproducibility: 6
- Exploitability: 6
- Affected Users: 8
- Discoverability: 5
- Score médio: 7.0/10

### Matriz de Risco

| Probabilidade | Impacto | Nível |
|---|---|---|
| 3 | 5 | 15 (Alto) |

### Janela temporal do evento 3

- 0 a 24h: alterações maliciosas podem passar despercebidas sem auditoria ativa.
- A partir do 7º dia: inconsistências em registros e dificuldade de rastrear autoria das mudanças.
- A partir do 30º dia: comprometimento da credibilidade técnica dos resultados e retrabalho interno.

### Evento de ameaça 4

Colaborador terceirizado com acesso físico amplo (equipe de limpeza) conecta dispositivo malicioso em estação do laboratório ou servidor, capturando credenciais e facilitando movimento lateral na rede interna.

### DREAD

- Damage: 8
- Reproducibility: 6
- Exploitability: 5
- Affected Users: 7
- Discoverability: 4
- Score médio: 6.0/10

### Matriz de Risco

| Probabilidade | Impacto | Nível |
|---|---|---|
| 3 | 4 | 12 (Alto) |

### Janela temporal do evento 4

- 0 a 24h: possível coleta de credenciais após acesso físico indevido a estações.
- A partir do 7º dia: chance de movimento lateral na rede interna e ampliação da superfície de ataque.
- A partir do 30º dia: necessidade de saneamento mais amplo de endpoints e revisão de controles físicos.

### Evento de ameaça 5

Ataque de indisponibilidade (DoS) ao site/plataforma de consulta de resultados em período crítico, impedindo acesso de clientes e atrasando operações jurídicas e técnicas.

### DREAD

- Damage: 7
- Reproducibility: 8
- Exploitability: 7
- Affected Users: 8
- Discoverability: 8
- Score médio: 7.6/10

### Matriz de Risco

| Probabilidade | Impacto | Nível |
|---|---|---|
| 4 | 4 | 16 (Crítico) |

### Janela temporal do evento 5

- 0 a 24h: indisponibilidade imediata da plataforma de resultados para clientes.
- A partir do 7º dia: acúmulo de atendimentos, atrasos operacionais e desgaste de comunicação.
- A partir do 30º dia: impacto em SLAs, reputação e potencial perda de contratos sensíveis.

### Evento de ameaça 6

Falha pontual na atualização de conteúdo da landing page pública (texto desatualizado por algumas horas), sem exposição de dados sensíveis e sem impacto direto na operação laboratorial.

### DREAD

- Damage: 2
- Reproducibility: 3
- Exploitability: 2
- Affected Users: 2
- Discoverability: 4
- Score médio: 2.6/10

### Matriz de Risco

| Probabilidade | Impacto | Nível |
|---|---|---|
| 2 | 2 | 4 (Baixo) |

### Janela temporal do evento 6

- 0 a 24h: percepção pontual de desorganização por conteúdo desatualizado.
- A partir do 7º dia: impacto baixo, concentrado em experiência do usuário na página pública.
- A partir do 30º dia: efeito residual mínimo, desde que haja correção e revisão editorial simples.

### Matriz de Risco Consolidada

| Evento | Probabilidade | Impacto | Nível |
|---|---|---|---|
| 1 | 4 | 5 | 20 (Crítico) |
| 2 | 4 | 4 | 16 (Crítico) |
| 3 | 3 | 5 | 15 (Alto) |
| 4 | 3 | 4 | 12 (Alto) |
| 5 | 4 | 4 | 16 (Crítico) |
| 6 | 2 | 2 | 4 (Baixo) |

Risco final calculado = (20 + 16 + 15 + 12 + 16 + 4) / 150 = 0.553 (55.3% do risco máximo possível)

### Resumo Executivo Breve

- Curto prazo: os Eventos 1 (backups comprometidos), 2 (phishing) e 5 (indisponibilidade da plataforma) exigem resposta imediata por potencial de dano operacional e exposição de informação.
- Médio prazo: os Eventos 3 e 4 demandam fortalecimento de auditoria, segregação de funções e controle físico.
- Baixo impacto: o Evento 6 pode ser tratado como melhoria contínua de comunicação e qualidade.

### Priorização de tratamento (ordem sugerida)

1. Evento 1 - restauração de backup comprometido (Crítico)
2. Evento 2 - comprometimento de conta de cliente e vazamento de laudos (Crítico)
3. Evento 5 - indisponibilidade da plataforma de resultados (Crítico)
4. Evento 3 - abuso de privilégio administrativo (Alto)
5. Evento 4 - comprometimento físico por acesso amplo (Alto)
6. Evento 6 - falha pontual de conteúdo na landing page (Baixo)
