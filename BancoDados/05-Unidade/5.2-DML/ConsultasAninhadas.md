### Resumo de Consultas Aninhadas (Subselects) - SQL DML

#### 1. **Definição**
   - Consultas aninhadas ou subselects são queries dentro de um `SELECT` principal. A subconsulta é executada primeiro, e seu resultado é utilizado no select externo.
   - Utilizado para comparar valores derivados de consultas no banco de dados.

#### 2. **Exemplo de Subselect Simples**
   - **Consulta**: Funcionários com salário maior que a média da empresa.
   ```sql
   SELECT nome, cargo, salario
   FROM Funcionario
   WHERE salario > (SELECT AVG(salario) FROM Funcionario);
   ```

#### 3. **Subselect sem Correlação**
   - O select interno não tem relação direta com o externo.
   - **Exemplo**: Selecionar o nome e salário do funcionário com o maior salário.
   ```sql
   SELECT nome, salario
   FROM Funcionario
   WHERE salario = (SELECT MAX(salario) FROM Funcionario);
   ```

#### 4. **Subselect com Comparação de Coluna**
   - **Exemplo**: Selecionar funcionários que trabalham no departamento de Contabilidade.
   ```sql
   SELECT nome
   FROM Funcionario
   WHERE cod_depto = (SELECT cod_depto FROM Depto WHERE nome_depto = 'Contabilidade');
   ```

#### 5. **Consultas Substituíveis por Junção**
   - **Exemplo**: Departamentos com funcionários no estado de MG.
   ```sql
   -- Usando subselect
   SELECT nome_depto
   FROM Depto
   WHERE cod_depto IN (SELECT cod_depto FROM Funcionario WHERE estado = 'MG');

   -- Usando join
   SELECT nome_depto
   FROM Funcionario A
   JOIN Depto B ON A.cod_depto = B.cod_depto
   WHERE estado = 'MG';
   ```

#### 6. **Subconsultas de Múltiplas Linhas**
   - Retornam várias linhas, usadas com operadores como `IN`, `ANY`, `ALL`.
   - **Exemplo**: Funcionários que ganham salários iguais ao de João ou Joice.
   ```sql
   SELECT Pnome, Unome
   FROM Funcionario
   WHERE salario IN (SELECT salario FROM Funcionario WHERE Pnome IN ('João', 'Joice'));
   ```

#### 7. **Operadores em Subselects**
   - **IN**: Verifica se o valor está em uma lista retornada.
   - **ALL**: Compara se um valor é maior que todos os valores retornados.
   - **ANY**: Verifica se o valor é maior que pelo menos um valor retornado.
   - **Exemplo**: Funcionárias com salário maior que qualquer funcionário do sexo masculino.
   ```sql
   SELECT Pnome, Unome
   FROM Funcionario
   WHERE sexo = 'F' AND salario > ANY (SELECT salario FROM Funcionario WHERE sexo = 'M');
   ```