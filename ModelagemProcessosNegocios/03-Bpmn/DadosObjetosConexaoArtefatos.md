# Dados ,objetos de conexão e artefatos

Aqui está um resumo objetivo dos tópicos abordados na aula sobre dados, objetos de conexão e artefatos no BPMN:

**Dados:**

- **Objeto de Dados (Data Objects):**
    - Representa informações que as atividades precisam para serem executadas ou produzem como saída.
    - Exemplo: "Preparar contrato" gera um rascunho de contrato, usado como entrada em "Revisar contrato".
    - Pode exibir estados diferentes (e.g., "rascunho de contrato" e "contrato revisado").
    - Associado principalmente a atividades, mas também pode estar ligado a eventos e gateways.
- **Depósito de Dados (Data Stores):**
    - Representa um repositório de dados, como uma tabela de banco de dados, arquivo físico ou eletrônico.
    - Conecta-se com tarefas que gravam ou consomem dados.
    - Exemplo: Tarefa de "Efetuar compra" pode buscar dados de um produto.

**Objetos de Conexão:**

- **Fluxos de Sequência:**
    - Indicam a ordem lógica das atividades em um processo.
    - Representado por uma linha contínua com uma seta preenchida.
- **Fluxos de Mensagem:**
    - Mostram a troca de mensagens entre participantes.
    - Representado por uma seta tracejada (detalhado em outro vídeo).
- **Associações:**
    - Usadas para associar objetos a fluxos.
    - Representadas por linhas pontilhadas, com ou sem seta, dependendo da conexão.

**Artefatos:**

- **Grupo (Group):**
    - Agrupa elementos gráficos dentro de uma mesma categoria.
    - Exemplo: Agrupamento de atividades como "Preparar" e "Entregar".
- **Anotação de Texto (Text Annotation):**
    - Fornece informações adicionais no diagrama.
    - Vinculado a uma associação (linha pontilhada).