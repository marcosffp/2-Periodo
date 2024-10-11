# Unidade 1.4: Propriedades do SGBD

1. **Propriedades Gerais do SGBD**:
    - **Integridade**: Garante que os dados no banco de dados refletem fielmente as informações do mundo real.
    - **Segurança**: Assegura que apenas usuários autorizados possam acessar ou manipular os dados.
    - **Backup e Recuperação**: Proporciona mecanismos para detectar falhas (elétricas, defeitos, erros) e restaurar o banco de dados ao estado anterior.
2. **Concorrência e Monitoramento**:
    - **Concorrência**: Permite o acesso simultâneo por vários usuários sem causar inconsistências nos dados. Controla o acesso para operações de leitura e escrita.
    - **Monitoramento**: Oferece ferramentas para acompanhar o comportamento do sistema, usadas pelo DBA para otimização (tunning) do banco de dados.
3. **Natureza Autodescritiva e Independência de Dados**:
    - **Natureza Autodescritiva**: Além dos dados, o sistema inclui uma descrição completa da estrutura e restrições do banco de dados (metadados).
    - **Independência de Dados**: Modificações na estrutura física ou lógica dos dados não exigem alterações nos programas que acessam esses dados, graças ao isolamento entre programas e dados.
4. **Suporte a Múltiplas Visões e Compartilhamento de Dados**:
    - **Múltiplas Visões**: Cada usuário pode ter diferentes perspectivas ou visões do banco de dados, conforme suas necessidades.
    - **Processamento Multiusuário**: Inclui um controle de concorrência para garantir que múltiplos usuários possam atualizar o mesmo dado de forma controlada, mantendo a integridade das transações.
5. **Controle de Acesso, Redundância e Persistência de Dados**:
    - **Controle de Acesso e Autorização**: Garante que apenas usuários com privilégios apropriados possam acessar ou modificar dados, com subsistemas específicos para gerenciar essas permissões.
    - **Controle de Redundância**: Integra diferentes visões de usuários durante o projeto do banco, evitando duplicação de dados.
    - **Persistência de Dados**: Garante o armazenamento contínuo de dados, estruturas e regras de negócios.
6. **Outras Propriedades Importantes**:
    - **Múltiplas Interfaces**: Oferece diferentes interfaces para diversos tipos de usuários, como consultas para usuários casuais e interfaces de programação para desenvolvedores.
    - **Eficiência no Processamento de Consultas**: O SGBD otimiza o processamento de consultas usando as estruturas de armazenamento disponíveis (índices).
    - **Representação de Múltiplos Relacionamentos**: Permite a inter-relação de dados de diversas maneiras, facilitando a representação de informações complexas.
    - **Padronização e Implementação de Restrições**: Implementa padrões e restrições de integridade, como tipos de dados e regras de negócios, para garantir consistência e conformidade.
7. **Conclusão**:
    - O SGBD é fundamental para facilitar o desenvolvimento de novas aplicações e proporcionar um ambiente eficiente para o armazenamento e recuperação de informações.