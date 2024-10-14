# 5.1-Linguagem SQL

### **Principais tópicos sobre SQL e restrições em bancos de dados:**

1. **SQL (Structured Query Language)**:
    - Linguagem padrão para gerenciar bancos de dados relacionais (SGBDs).
    - Engloba comandos para definição, manipulação e controle de dados.
2. **Tipos de Linguagem SQL**:
    - **DDL (Data Definition Language)**: Criação e manutenção de estruturas (ex: CREATE, ALTER, DROP).
    - **DML (Data Manipulation Language)**: Manipulação de dados (ex: SELECT, INSERT, UPDATE, DELETE).
3. **Comandos DDL - Criação e Alteração de Tabelas**:
    - **CREATE TABLE**: Define a estrutura de uma nova tabela com colunas e tipos de dados.
        - Exemplo:
        
        ```sql
        CREATE TABLE Funcionario (
           Matricula INT NOT NULL,
           Nome CHAR(30) NOT NULL,
           Salario MONEY NOT NULL
        );
        
        ```
        
    - **ALTER TABLE**: Altera a estrutura de uma tabela existente (adiciona/remover colunas, modificar restrições).
        - Exemplo:
        
        ```sql
        ALTER TABLE Funcionario ADD email VARCHAR(50);
        
        ```
        
    - **DROP TABLE**: Remove uma tabela e seus registros permanentemente.
        - Exemplo:
        
        ```sql
        DROP TABLE Funcionario;
        
        ```
        
4. **Tipos de Dados**:
    - **Numéricos**: INT, FLOAT, NUMBER(p,s).
    - **Texto**: CHAR(size), VARCHAR(size), TEXT.
    - **Data e Hora**: DATE, TIME, TIMESTAMP.
    - **Booleano**: BIT (0 ou 1).
5. **Restrições de Integridade**:
    - **PRIMARY KEY**: Garante unicidade dos registros e impede valores nulos.
        - Exemplo:
        
        ```sql
        CONSTRAINT PK_Funcionario PRIMARY KEY (Matricula);
        
        ```
        
    - **UNIQUE**: Garante valores únicos em uma coluna.
        - Exemplo:
        
        ```sql
        CONSTRAINT UQ_Nome UNIQUE (Nome);
        
        ```
        
    - **NOT NULL**: Impede valores nulos.
        - Exemplo:
        
        ```sql
        Nome CHAR(30) NOT NULL;
        
        ```
        
    - **FOREIGN KEY**: Garante integridade referencial entre tabelas.
        - Exemplo:
        
        ```sql
        CONSTRAINT FK_Func_Depto FOREIGN KEY (Cod_Depto) REFERENCES Departamento (Cod_Depto);
        
        ```
        
6. **Chave Estrangeira (Foreign Key)**:
    - Assegura que os valores em uma coluna correspondam aos valores da chave primária de outra tabela.
    - Opções para exclusão e atualização: **CASCADE**, **RESTRICT**, **SET NULL**, **NO ACTION**.
    - Exemplo:
        
        ```sql
        CONSTRAINT FK_Produto_Categoria FOREIGN KEY (id_categoria) REFERENCES Categoria(id);
        
        ```
        
7. **Restrições de Default**:
    - Define um valor padrão para colunas que não recebem valor explícito.
    - Exemplo:
        
        ```sql
        Cargo CHAR(15) DEFAULT 'Analista';
        
        ```
        
8. **Restrição de Verificação (CHECK)**:
    - Define condições que os valores da coluna devem cumprir.
    - Exemplo:
        
        ```sql
        CONSTRAINT checkestado CHECK (Estado IN ('MG', 'RJ', 'SP'));
        
        ```
        
9. **Diferença entre DELETE e DROP**:
    - **DELETE**: Remove dados, mantendo a estrutura da tabela.
    - **DROP**: Remove tanto os dados quanto a estrutura da tabela.
10. **Cuidados com Performance**:
    - A escolha de tipos de dados (VARCHAR vs. CHAR) impacta o armazenamento e a velocidade de consultas.
11. **Modelagem de Dados e Normalização**:
    - Importante antes da criação física das tabelas para garantir eficiência e evitar redundâncias.

Com esses tópicos e exemplos, você tem uma visão clara sobre a estrutura e restrições aplicadas no SQL para a criação e gerenciamento de tabelas.

Aqui está uma explicação bem objetiva com exemplos em SQL:

1. **CASCADE**: Se o registro na tabela pai for excluído, os registros na tabela filha também são excluídos.
    
    ```sql
    -- Excluir um departamento também exclui todos os funcionários associados
    FOREIGN KEY (Cod_Depto) REFERENCES Departamento(Cod_Depto) ON DELETE CASCADE
    
    ```
    
2. **RESTRICT**: Impede a exclusão ou atualização de um registro na tabela pai se houver registros associados na tabela filha.
    
    ```sql
    -- Não permite excluir um departamento se houver funcionários associados
    FOREIGN KEY (Cod_Depto) REFERENCES Departamento(Cod_Depto) ON DELETE RESTRICT
    
    ```
    
3. **SET NULL**: Se o registro na tabela pai for excluído, o campo da chave estrangeira na tabela filha é definido como `NULL`.
    
    ```sql
    -- Excluir um departamento define Cod_Depto como NULL nos funcionários associados
    FOREIGN KEY (Cod_Depto) REFERENCES Departamento(Cod_Depto) ON DELETE SET NULL
    
    ```
    
4. **NO ACTION**: Nenhuma ação é tomada (equivalente a RESTRICT na prática).
    
    ```sql
    -- Não permite exclusão se houver referências, comportamento padrão
    FOREIGN KEY (Cod_Depto) REFERENCES Departamento(Cod_Depto) ON DELETE NO ACTION
    
    ```
    

**SET DEFAULT**: Se um registro na tabela pai for excluído ou atualizado, o campo da chave estrangeira na tabela filha é definido com um valor padrão.

**Exemplo em SQL:**

```sql
-- Excluir um departamento define Cod_Depto como um valor padrão (ex: 1)
FOREIGN KEY (Cod_Depto) REFERENCES Departamento(Cod_Depto) ON DELETE SET DEFAULT

```

Neste exemplo, se o departamento referenciado for excluído, o `Cod_Depto` nos funcionários associados será alterado para um valor padrão, como `1`, que deve ser previamente definido na tabela.