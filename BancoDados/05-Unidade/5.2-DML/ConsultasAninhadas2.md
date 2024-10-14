### Resumo Unificado: Subconsultas Correlacionadas e Não Correlacionadas em SQL

---

### 1. **Subconsultas Correlacionadas**
- **Definição**: Dependem de valores da consulta externa para serem executadas. A consulta interna é avaliada para cada linha processada pela consulta externa.
- **Funcionamento**: A consulta externa itera sobre seus registros e executa a subconsulta para cada um, utilizando os valores da linha atual.
  
**Exemplo**: Selecionar funcionários que ganham mais do que a média salarial de seu departamento.
```sql
SELECT nome
FROM funcionario A
WHERE salario > (
  SELECT AVG(salario)
  FROM funcionario B
  WHERE B.cod_depto = A.cod_depto
);
```
- A subconsulta calcula a média salarial do departamento do funcionário da linha externa.

**Exemplo 2**: Selecionar cargos que existem no departamento 1, mas não no departamento 2.
```sql
SELECT DISTINCT A.cargo
FROM funcionario A
WHERE A.cod_depto = 1
AND NOT EXISTS (
  SELECT 1
  FROM funcionario B
  WHERE B.cod_depto = 2
  AND B.cargo = A.cargo
);
```
- Verifica se o cargo de `A` (departamento 1) não existe no departamento 2.

### 2. **Subconsultas Não Correlacionadas**
- **Definição**: Podem ser executadas de forma independente da consulta externa. A subconsulta executa apenas uma vez, retornando um conjunto de resultados que a consulta externa utiliza.
  
**Exemplo**: Selecionar funcionários que ganham mais que a média salarial de todos os funcionários.
```sql
SELECT nome
FROM funcionario
WHERE salario > (
  SELECT AVG(salario)
  FROM funcionario
);
```
- A subconsulta retorna a média salarial geral, sem dependência da consulta externa.

**Exemplo 2**: Selecionar cargos do departamento 1 que não existem no departamento 2 usando `NOT IN`.
```sql
SELECT DISTINCT cargo
FROM funcionario
WHERE cod_depto = 1
AND cargo NOT IN (
  SELECT cargo
  FROM funcionario
  WHERE cod_depto = 2
);
```
- `NOT IN` compara diretamente os cargos entre os departamentos.

### 3. **EXISTS vs IN**
- **EXISTS**: Verifica se a subconsulta retorna ao menos uma linha.
- **IN**: Compara um valor com a lista de resultados da subconsulta.

**Exemplo com `EXISTS`**: Selecionar funcionários que têm colegas no mesmo estado no departamento 2.
```sql
SELECT nome
FROM funcionario A
WHERE EXISTS (
  SELECT 1
  FROM funcionario B
  WHERE B.cod_depto = 2
  AND B.estado = A.estado
);
```
- `EXISTS` verifica se algum funcionário no departamento 2 está no mesmo estado.

**Exemplo com `IN`**: Selecionar funcionários cujo estado corresponde a algum do departamento 2.
```sql
SELECT nome
FROM funcionario
WHERE estado IN (
  SELECT estado
  FROM funcionario
  WHERE cod_depto = 2
);
```

### 4. **ALL e ANY**
- **ALL**: Compara um valor com todos os resultados da subconsulta.
- **ANY**: Compara com qualquer valor retornado.

**Exemplo com `ALL`**: Selecionar funcionários que ganham mais que todos do departamento 1.
```sql
SELECT nome
FROM funcionario
WHERE salario > ALL (
  SELECT salario
  FROM funcionario
  WHERE cod_depto = 1
);
```

**Exemplo com `ANY`**: Selecionar funcionários que ganham mais que algum funcionário do departamento 1.
```sql
SELECT nome
FROM funcionario
WHERE salario > ANY (
  SELECT salario
  FROM funcionario
  WHERE cod_depto = 1
);
```

---

### 5. **Conclusão**
- **Subconsultas Correlacionadas**: São mais complexas e podem ser menos eficientes, mas são necessárias quando os dados da subconsulta dependem da consulta externa.
- **Subconsultas Não Correlacionadas**: Mais eficientes quando aplicáveis, pois executam de forma independente da consulta externa.

Esses exemplos ilustram como utilizar subconsultas correlacionadas e não correlacionadas para resolver diferentes tipos de problemas em SQL.