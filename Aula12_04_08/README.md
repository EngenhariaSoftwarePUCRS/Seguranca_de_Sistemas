Inicialmente tratava de vulnerabilidade e, hoje em dia, trata de risco.

### Vulnerabilidade x Risco

- Vulnerabilidade: fraqueza ou falha em um sistema que pode ser explorada por um atacante para comprometer a segurança do sistema. Uma ameaça sem vulnerabilidade, é inofensiva.

- Risco: a probabilidade de um ataque ocorrer e causar danos, levando em consideração a vulnerabilidade, a ameaça e o impacto potencial. Só existe quando uma vulnerabilidade é explorada por uma ameaça, resultando em um impacto negativo.

## Top 10 OWASP

1. Broken Access Control
   - IDOR (Insecure Direct Object References)
     - Ex: https://example.com/user/12345/profile
     - O atacante pode modificar o ID para acessar os dados de outro usuário
   - SSRF (Server-Side Request Forgery)
     - O atacante pode manipular o servidor para fazer solicitações a outros recursos internos ou externos, explorando a confiança do servidor em relação a essas solicitações.
2. Security Misconfiguration
   - Hardening: processo de configurar um sistema para reduzir suas vulnerabilidades, removendo ou desativando serviços desnecessários, aplicando patches de segurança, configurando corretamente as permissões e implementando medidas de segurança adicionais.
3. Software Supply Chain Failures
   - Terceirização de software: o uso de componentes de terceiros, como bibliotecas, frameworks e serviços, pode introduzir vulnerabilidades se esses componentes não forem adequadamente avaliados e mantidos. Qualquer um desses aumenta nossa superfície de ataque.
4. Cryptographic Failures
   - Uso de cifras vulneráveis.
5. Injection
   - SQL Injection: o atacante pode inserir código SQL malicioso em uma consulta, permitindo que ele acesse, modifique ou exclua dados do banco de dados.
   - Command Injection: o atacante pode inserir comandos maliciosos em um aplicativo, permitindo que ele execute comandos no sistema operacional subjacente.
6. Insecure Design
   - Modelagem de Ameaças: processo de identificar, avaliar e mitigar ameaças potenciais a um sistema, ajudando a garantir que o sistema seja projetado com segurança desde o início.
   - Capacitações: treinamentos e workshops para educar os desenvolvedores sobre as melhores práticas de segurança, ajudando a garantir que eles estejam cientes das vulnerabilidades comuns e saibam como evitá-las durante o processo de desenvolvimento.
   - OOWASP SAMM: Software Assurance Maturity Model, é um modelo de maturidade para avaliação e melhoria dos processos de segurança em desenvolvimento de software. Ele fornece um framework para avaliar a maturidade dos processos de segurança em uma organização e identificar áreas de melhoria.
7. Authentication Failures
   - Quando um sistema de autenticação é mal implementado, ele pode permitir que atacantes acessem contas de usuários sem autorização. Isso pode ocorrer devido a senhas fracas, falta de proteção contra ataques de força bruta, ou falhas na implementação de mecanismos de autenticação multifator.
8. Software or Data Integrity Failures
   - Desserialização Insegura: ocorre quando um aplicativo desserializa dados de uma fonte não confiável, permitindo que um atacante envie dados maliciosos que podem levar à execução de código arbitrário, negação de serviço ou outras vulnerabilidades.
9.  Security Logging and Alerting Failures
   - Trilha de Auditoria: um registro detalhado de eventos e atividades em um sistema, que pode ser usado para monitorar, analisar e responder a incidentes de segurança. A falta de uma trilha de auditoria adequada pode dificultar a detecção e resposta a ataques, tornando o sistema mais vulnerável a ameaças.
10. Mishandling of Exceptional Conditions
   - Tratamento de erros
