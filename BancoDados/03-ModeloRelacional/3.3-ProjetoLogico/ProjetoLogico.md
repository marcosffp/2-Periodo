# Unidade 3.3: Modelo Relacional: Projeto Lógico

Aqui está o resumo em tópicos objetivos sobre o conteúdo de mapeamento do modelo ER para o modelo relacional:

### 1. **Projeto Conceitual de Banco de Dados**

- Baseado no modelo de entidade-relacionamento (ER).
- Independente do tipo de SGBD.

### 2. **Projeto Lógico de Banco de Dados**

- Específico para um tipo de banco de dados (ex: relacional).
- Converte entidades e relacionamentos em tabelas e chaves.

### 3. **Projeto Físico de Banco de Dados**

- Define a implementação em um SGBD específico (ex: Oracle, MySQL).
- Criação das estruturas físicas (tabelas, índices).

### 4. **Mapeamento de Entidade Regular**

- Cada entidade forte vira uma tabela.
- Escolha de uma chave primária (que pode ser composta).

### 5. **Mapeamento de Atributos Multivalorados**

- Criar tabela separada para cada atributo multivalorado.
- A tabela inclui uma chave estrangeira para a entidade original.

### 6. **Mapeamento de Entidade Fraca**

- A entidade fraca depende de uma entidade forte.
- A chave primária da entidade fraca é composta pela chave da entidade forte mais uma chave parcial.

### 7. **Mapeamento de Relacionamento 1:1**

- Inserir a chave estrangeira de uma entidade na tabela da outra, geralmente a que tem participação total.

### 8. **Mapeamento de Relacionamento 1:N**

- A chave primária da entidade no lado "1" é incluída como chave estrangeira na tabela do lado "N".

### 9. **Mapeamento de Relacionamento N:N**

- Criar uma tabela associativa contendo as chaves estrangeiras das duas entidades participantes.

### 10. **Mapeamento de Relacionamento N-ário**

- Criar uma tabela associativa que inclui as chaves primárias de todas as entidades envolvidas no relacionamento.

### 11. **Mapeamento de Generalização-Especialização**

- Pode ser implementado de três formas:
    1. Tabela única para o supertipo que contém todos os atributos.
    2. Tabelas separadas para cada subtipo.
    3. Uma tabela para o supertipo e tabelas separadas para cada especialização.