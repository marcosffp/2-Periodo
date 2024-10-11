# Unidade 1.3: Arquitetura de 3 Níveis do SGBD

1. **Arquitetura de 3 Níveis**:
    - O SGBD utiliza uma arquitetura de três níveis para proporcionar uma visão abstrata dos dados aos usuários, facilitando a interação com o sistema.
2. **Níveis da Arquitetura**:
    - **Nível Interno (Físico)**:
        - Descreve como os dados são armazenados fisicamente no sistema.
        - Envolve a alocação de espaço em disco e o uso de índices para melhorar o desempenho.
        - É o principal foco do Administrador de Banco de Dados (DBA).
    - **Nível Conceitual (Lógico)**:
        - Define quais dados são armazenados no banco de dados e os relacionamentos entre eles.
        - Baseia-se na modelagem de dados e é o principal nível de atuação do Administrador de Dados (AD).
    - **Nível Externo (Visão)**:
        - Corresponde às diferentes visões que os usuários (desenvolvedores ou usuários finais) têm do banco de dados.
        - Cada usuário necessita apenas de uma parte específica do banco de dados, e diferentes visões podem ser fornecidas pelo sistema para um mesmo banco de dados.
3. **Independência de Dados**:
    - **Independência Física**:
        - Alterações no nível físico (como a criação de índices) não afetam o nível conceitual.
        - É alcançada quando a estrutura física dos dados pode ser modificada sem impactar a estrutura lógica.
    - **Independência Lógica**:
        - Alterações no nível conceitual não provocam modificações no nível de visão.
        - Mais difícil de alcançar, pois os programas dependem muito da estrutura lógica dos dados.
4. **Etapas do Projeto de um Banco de Dados**:
    - **Projeto Conceitual**:
        - Descreve a estrutura de informação sem considerar em qual SGBD o banco de dados será implementado.
        - Define os tipos de dados e seus relacionamentos, resultando em um esquema conceitual.
        - Envolve a participação do AD, usuário final e analista de sistemas/engenheiro de software.
    - **Projeto Lógico**:
        - Transforma o modelo de dados conceitual em um modelo específico para uma classe de SGBD (relacional, OO, hierárquico, rede).
        - Resulta em um esquema lógico que descreve as estruturas de representação.
        - Participam o AD, o DBA e o analista de sistemas/engenheiro de software.
    - **Projeto Físico**:
        - Define como o projeto lógico será armazenado fisicamente, incluindo espaço em disco, backups, e número de usuários.
        - Produz o script DDL para o SGBD específico, com foco em melhorar a performance.
        - Participam o DBA e o engenheiro de software.