### Funções Agregadas
- **AVG()**: Calcula a média aritmética.
  ```sql
  SELECT AVG(salario) AS media_salario FROM funcionarios;
  ```

- **SUM()**: Soma de valores.
  ```sql
  SELECT SUM(salario) AS soma_salario FROM funcionarios WHERE departamento_id = 1;
  ```

- **MAX()**: Retorna o maior valor.
  ```sql
  SELECT MAX(salario) AS maior_salario FROM funcionarios WHERE departamento_id = 1;
  ```

- **MIN()**: Retorna o menor valor.
  ```sql
  SELECT MIN(salario) AS menor_salario FROM funcionarios WHERE departamento_id = 1;
  ```

- **COUNT()**: Conta o número de linhas ou valores distintos.
  ```sql
  SELECT COUNT(*) AS total_funcionarios FROM funcionarios;
  SELECT COUNT(DISTINCT cidade) AS total_cidades FROM clientes;
  ```

### 2. Uso do `GROUP BY`
- Agrupa resultados com base em uma ou mais colunas.
  ```sql
  SELECT departamento_id, AVG(salario) AS media_salario
  FROM funcionarios
  GROUP BY departamento_id;
  ```

### 3. Ordenação com `ORDER BY`
- **Crescente (ASC)**: Padrão, se não especificado.
  ```sql
  SELECT nome FROM funcionarios ORDER BY nome ASC;
  ```

- **Decrescente (DESC)**:
  ```sql
  SELECT nome, salario FROM funcionarios ORDER BY salario DESC;
  ```

- **Múltipla**: Ordenar por mais de uma coluna.
  ```sql
  SELECT codigo_departamento, nome 
  FROM funcionarios 
  ORDER BY codigo_departamento ASC, nome ASC;
  ```

### 4. Filtro por Agrupamento com `HAVING`
- Filtra grupos após a agregação.
  ```sql
  SELECT departamento_id, COUNT(*) AS quantidade_funcionarios
  FROM funcionarios
  GROUP BY departamento_id
  HAVING COUNT(*) > 3;
  ```

### 5. Diferenças entre `WHERE` e `HAVING`
- **WHERE**: Restringe as linhas antes do agrupamento.
  ```sql
  SELECT department_id, COUNT(*) FROM employees WHERE manager_id = 100 GROUP BY department_id;
  ```

- **HAVING**: Restringe grupos após o agrupamento.
  ```sql
  SELECT department_id, COUNT(*) FROM employees GROUP BY department_id HAVING COUNT(*) > 1;
  ```

### 6. Observações Importantes
- **Aliases**: Útil para renomear colunas resultantes.
  ```sql
  SELECT AVG(salario) AS media_salario FROM funcionarios;
  ```

- **Tratamento de Nulos**: Considerar como os nulos afetam os cálculos.
  ```sql
  SELECT AVG(salario) AS media_salario FROM funcionarios WHERE salario IS NOT NULL;
  ```
