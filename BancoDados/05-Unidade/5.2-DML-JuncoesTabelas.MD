### Resumo de SQL DML – Junções de Tabelas (JOIN)

**1. Junções (JOIN)**:  
- Usado para combinar linhas de duas ou mais tabelas com base em uma condição de junção, geralmente relacionando chaves primárias e estrangeiras.  
Exemplo:
```sql
SELECT funcionario.nome, departamento.nome  
FROM funcionario  
JOIN departamento ON funcionario.dep_id = departamento.id;
```

**2. Produto Cartesiano**:  
- Combina todas as linhas de duas tabelas sem uma condição de junção, gerando muitas combinações indesejadas.  
Exemplo:
```sql
SELECT nome_depto, nome  
FROM Depto, Funcionario;
```

**3. Tipos de JOIN**:  
- **INNER JOIN**: Retorna apenas as linhas com correspondência em ambas as tabelas.  
- **LEFT JOIN**: Retorna todas as linhas da tabela à esquerda e as correspondências da direita.  
- **RIGHT JOIN**: Retorna todas as linhas da tabela à direita e as correspondências da esquerda.  
- **FULL JOIN**: Retorna todas as linhas de ambas as tabelas, preenchendo com valores nulos onde não há correspondência.

Exemplos:
- **INNER JOIN**:
```sql
SELECT nome_depto, nome  
FROM Depto INNER JOIN Funcionario  
ON Depto.cod_depto = Funcionario.cod_depto;
```
- **LEFT JOIN**:
```sql
SELECT nome, nome_dependente  
FROM Funcionario LEFT JOIN Dependente  
ON Funcionario.matricula = Dependente.matricula;
```

**4. Alias (Apelidos)**:  
- Simplifica a consulta ao renomear as tabelas.  
Exemplo:
```sql
SELECT F.nome, D.nome_depto  
FROM Funcionario F, Departamento D  
WHERE F.cod_depto = D.cod_depto;
```

**5. UNION**:  
- Combina os resultados de dois ou mais SELECTs, removendo duplicatas (ou mantendo com UNION ALL).  
Exemplo:
```sql
SELECT nome, estado FROM Funcionario WHERE estado = 'MG'  
UNION  
SELECT nome, estado FROM Funcionario WHERE estado = 'RJ';
```

**6. Operações com agregados**:  
- Realiza cálculos como soma, média, etc.  
Exemplo:  
Média de salários no departamento de informática, excluindo gerente:
```sql
SELECT AVG(salario)  
FROM Funcionario  
JOIN Depto ON Funcionario.cod_depto = Depto.cod_depto  
WHERE nome_depto = 'Informatica' AND cargo <> 'gerente';
```

**7. Agrupamento e Ordenação**:  
- **GROUP BY** agrupa dados por colunas, enquanto **ORDER BY** define a ordem de exibição.  
Exemplo:  
Somatório de salários por departamento:
```sql
SELECT nome_depto, SUM(salario)  
FROM Funcionario  
JOIN Depto ON Funcionario.cod_depto = Depto.cod_depto  
GROUP BY nome_depto  
ORDER BY SUM(salario) DESC;
```

Esses tópicos cobrem os principais tipos de junções, agregados, alias, e operações com tabelas em SQL.