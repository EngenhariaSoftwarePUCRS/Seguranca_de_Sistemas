Questionário

Resposta

Análise

[R1, R2, R3, R4]

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

### Priorização de tratamento (ordem sugerida)

1. Evento 1 - restauração de backup comprometido (Crítico)
2. Evento 2 - comprometimento de conta de cliente e vazamento de laudos (Crítico)
3. Evento 5 - indisponibilidade da plataforma de resultados (Crítico)
4. Evento 3 - abuso de privilégio administrativo (Alto)
5. Evento 4 - comprometimento físico por acesso amplo (Alto)
6. Evento 6 - falha pontual de conteúdo na landing page (Baixo)
