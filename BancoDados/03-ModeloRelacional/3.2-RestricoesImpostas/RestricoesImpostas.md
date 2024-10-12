# Unidade 3.2: Modelo Relacional: Restrições impostas pelo Modelo Relacional (Integridade Referencial)

Aqui está um resumo objetivo sobre chave estrangeira e integridade referencial no modelo relacional:

1. **Chave Estrangeira (Foreign Key)**
    - Implementa relacionamentos entre tabelas.
    - Refere-se à chave primária de outra tabela.
    - Exemplo: Tabela "Empregado" tem uma chave estrangeira que aponta para a chave primária da tabela "Departamento".
2. **Requisitos da Chave Estrangeira**
    - Deve ter o mesmo tipo e domínio da chave primária referenciada.
    - Deve referenciar um valor válido da chave primária ou ser nula.
3. **Restrições de Integridade**
    - **Integridade de Domínio**: Valor deve obedecer ao domínio definido.
    - **Integridade de Entidade**: Nenhum componente da chave primária pode ser nulo.
    - **Integridade de Chave**: Chave primária não pode ter valores duplicados.
    - **Integridade Referencial**: Chave estrangeira deve referenciar um valor válido da chave primária ou ser nula.
4. **Operações com Integridade Referencial**
    - **Inclusão**: Deve respeitar integridade de domínio, chave e referencial. Exemplo: Não permitir inclusão de um empregado em um departamento inexistente.
    - **Exclusão**: Deve garantir que não existam referências pendentes. Exemplo: Não excluir um departamento se ainda houver empregados associados.
    - **Alteração**: Mudanças devem manter a consistência. Exemplo: Não alterar a referência de um empregado para um departamento inexistente.
5. **Reações do Banco de Dados**
    - **Inclusão**: Bloqueia inserções que violam integridade.
    - **Exclusão**: Pode restringir ou definir como nulo se houver referências.
    - **Alteração**: Restringe mudanças para manter referências válidas.
6. **Configuração de Integridade Referencial**
    - Pode definir ações específicas para exclusão ou atualização, como definir valores como nulos.

Esses pontos cobrem o conceito essencial de chave estrangeira e integridade referencial em bancos de dados relacionais.