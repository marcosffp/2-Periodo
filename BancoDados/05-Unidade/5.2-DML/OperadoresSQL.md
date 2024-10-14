# 5.2-Operadores SQL

### Resumo Objetivo e Direto:

1. **Operações Básicas de Manipulação de Dados (DML):**
    - **INSERT (Inserção)**: Adiciona registros a uma tabela.
        
        ```sql
        INSERT INTO projeto (numero, nome, localizacao, dep_responsavel)
        VALUES (22, 'Rede Wi-Fi corporativa', 'Predio P1', 10);
        
        ```
        
    - **SELECT (Seleção)**: Recupera dados de uma ou mais tabelas.
        
        ```sql
        SELECT matricula, nome FROM Funcionario WHERE comissao < 150;
        
        ```
        
    - **UPDATE (Atualização)**: Altera dados existentes.
        
        ```sql
        UPDATE Funcionario SET salario = salario * 1.10 WHERE cargo = 'contador';
        
        ```
        
    - **DELETE (Exclusão)**: Remove registros de uma tabela.
        
        ```sql
        DELETE FROM Funcionario WHERE cargo = 'contador';
        
        ```
        
2. **DML vs. DDL:**
    - **DDL (Data Definition Language)**: Usado para definir a estrutura de dados (ex.: criação de tabelas).
    - **DML (Data Manipulation Language)**: Manipula dados já existentes (ex.: INSERT, SELECT, UPDATE, DELETE).
3. **Inserção de Dados:**
    - **Inserção Unitária**: Inserção de um único registro.
        
        ```sql
        INSERT INTO Funcionario (matricula, nome, cargo, salario, cod_depto)
        VALUES (70, 'Abel', 'analista', 2000, 1);
        
        ```
        
    - **Inserção em Massa**: Inserção a partir de um SELECT.
        
        ```sql
        INSERT INTO Funcionario_TI SELECT * FROM Funcionario WHERE cod_depto = 1;
        
        ```
        
4. **Uso do SELECT e Filtros:**
    - **Select Asterisco**: Retorna todas as colunas.
        
        ```sql
        SELECT * FROM Funcionario;
        
        ```
        
    - **Filtros com WHERE**: Limita os dados retornados com condições.
        
        ```sql
        SELECT nome, salario FROM Funcionario WHERE salario BETWEEN 2000 AND 3500 AND cod_depto = 1;
        
        ```
        
5. **Principais Operadores:**
    - **Comparação**: `=`, `<>`, `>`, `<`, `>=`, `<=`.
    - **Lógicos**: `AND`, `OR`, `NOT`.
    - **BETWEEN**: Define um intervalo.
        
        ```sql
        SELECT * FROM Funcionario WHERE salario BETWEEN 1800 AND 2000;
        
        ```
        
    - **IN**: Verifica presença em uma lista de valores.
        
        ```sql
        SELECT nome FROM Funcionario WHERE cod_depto IN (1, 2);
        
        ```
        
    - **IS NULL / IS NOT NULL**: Verifica valores nulos.
        
        ```sql
        SELECT nome FROM Funcionario WHERE estado IS NULL;
        
        ```
        
    - **LIKE**: Pesquisa padrões de string.
        
        ```sql
        SELECT nome FROM Funcionario WHERE nome LIKE '_u%';
        
        ```
        
6. **Boas Práticas no SQL:**
    - Evitar o uso de `SELECT *` para otimizar performance.
    - Utilizar operadores de comparação adequados para garantir clareza e eficiência na consulta.

Esses pontos cobrem as principais operações e melhores práticas para manipulação de dados utilizando SQL DML.