# 5.1-Índices e visões

Aqui está um resumo conciso sobre índices e visões em bancos de dados, com exemplos SQL:

### Tópicos Objetivos sobre Índices e Visões

### 1. **Índices no Banco de Dados**

- **Estrutura Física**: Índices otimizam a performance de consultas.
- **Criação**: Utiliza-se `CREATE INDEX`.
    
    ```sql
    CREATE INDEX idx_nome_cliente ON clientes(nome);
    
    ```
    
- **Uso Automático**: O SGBD decide automaticamente o uso do índice.
- **Impacto em DML**: `INSERT`, `UPDATE`, e `DELETE` podem ser mais lentos devido à atualização dos índices.
- **Índices Únicos**: Garantem valores únicos.
    
    ```sql
    CREATE UNIQUE INDEX idx_unique_email ON usuarios(email);
    
    ```
    
- **Índices Compostos**: Criação de índices em múltiplas colunas.
    
    ```sql
    CREATE INDEX idx_estado_cidade ON clientes(estado, cidade);
    
    ```
    
- **Índices Clusterizados**: Ordenam registros fisicamente.
    
    ```sql
    CREATE CLUSTERED INDEX idx_matricula ON funcionarios(matricula);
    
    ```
    
- **Deleção de Índices**: Para remover um índice:
    
    ```sql
    DROP INDEX idx_nome_cliente;
    
    ```
    

### 2. **Visões no Banco de Dados**

- **Estrutura Lógica**: Visões são tabelas virtuais baseadas em consultas `SELECT`.
- **Criação de Visão**: Usando `CREATE VIEW`.
    
    ```sql
    CREATE VIEW vw_ramais_empresa AS
    SELECT f.nome, d.nome_departamento, f.ramal
    FROM funcionarios f
    JOIN departamentos d ON f.id_departamento = d.id_departamento;
    
    ```
    
- **Filtros em Visões**: Visões podem filtrar registros.
    
    ```sql
    CREATE VIEW vw_clientes_sudeste AS
    SELECT nome, cidade
    FROM clientes
    WHERE estado IN ('MG', 'SP', 'RJ', 'ES');
    
    ```
    
- **Alteração e Exclusão**: Remover visões com `DROP VIEW`.
    
    ```sql
    DROP VIEW vw_clientes_sudeste;
    
    ```
    

### 3. **Quando Criar Índices**

- Crie índices em colunas com frequente uso em `WHERE`, `ORDER BY` ou `JOIN`.
- Evite em colunas pouco seletivas.
    
    ```sql
    CREATE INDEX idx_estado ON clientes(estado); -- Exemplo não ideal.
    
    ```
    

### 4. **Impacto na Performance**

- **Consultas**: Índices aceleram seleções e ordenações.
- **Inserções e Atualizações**: Podem ser mais lentas devido à atualização dos índices.

### Considerações Finais

- O uso eficaz de índices e visões é crucial para a performance do banco de dados. O planejamento cuidadoso na criação e uso é necessário para evitar degradações de desempenho em operações DML.