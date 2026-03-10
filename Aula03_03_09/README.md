# Notas

## Tipos de Reconhecimento

### Passivo

Através de dados públicos, como notícias, redes sociais, etc.

### Ativo

Ruído, isto é, a vítima pode obter pistas de que está sendo monitorada, como por exemplo, um sinal de Wi-Fi falso.

### Exemplo

Descobri que uma determinada aplicação utiliza como tecnologia o Java 6.
Procuro na CVE (Common Vulnerabilities and Exposures) por vulnerabilidades relacionadas ao Java 6.
Descobri, por exemplo, que é vulnerável a um ataque de negação de serviço (DoS): CVE-2023-44487.

## Modelagem de Ameaças

Quais os possíeis problemas que podem ocorrer, quais as vulnerabilidades, quais os ataques, etc.

O que alguém pode fazer e a consequência/o impacto disso.

Quando falamos de risco falamos de probabilidade x impacto.

$Risco = Probabilidade \times Impacto$

Não se fala mais tanto em vulnerabilidade, mas sim em risco.

O que acontece (impacto) se um ataque for bem sucedido?

No mundo da cyber segurança, o movimento passou a ser falar em risco e não vulnerabilidade, pois trabalha na lingua comum aos negócios: o dinheiro.

### Exemplo

Pegar 20 livros da biblioteca da PUCRS (Irmão José Otão) sem que ninguém veja.

Caso pessoal de modelagem:

#### Invadir aplicativo de reserva de quadra.

- Pegar credencial de administrador.
  - Alterar limite de reservas.
  - Excluir reservas de outros usuários.
- Pegar credencial de usuário.
  - Desfazer/alterar reserva de outro usuário.
  - Gravar código de acesso do outro usuário.
- Descobrir tecnologias.
  - Descobrir quais requisições são feitas pela rede.
    - Fazer requisição não contar aluno a mais.
    - Fazer requisição contar aluno a menos.
  - Descobrir como acessar logs de administrador.
- Derrubar aplicação.
  - Reserva será na hora no papel.

### STRIDE

Spoofing (Falsificação de identidade)
Tampering (Violação de integridade)
Repudiation (Repúdio)
Information Disclosure (Divulgação de informações)
Denial of Service (Negação de serviço)
Elevation of Privilege (Elevação de privilégio)

Cada um desses itens representa um tipo de ataque a ser executado.

### DREAD

Damage (Dano)
Reproducibility (Reprodutibilidade)
Exploitability (Explorabilidade)
Affected Users (Usuários afetados)
Discoverability (Descobribilidade)
