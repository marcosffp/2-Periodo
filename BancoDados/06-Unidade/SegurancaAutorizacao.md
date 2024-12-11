### Segurança e Autorização em Banco de Dados

- **DCL (Data Control Language):**
  - Controla privilégios de acesso ao banco de dados, com foco em segurança.
  - Atribuições feitas por DBA em conjunto com analistas e gestores.

---

### **Privilégios**
1. **Sistema:** Para ações gerais no banco (ex.: criar tabelas, triggers, usuários).
2. **Objeto:** Para manipular objetos específicos (ex.: tabelas, views).

---

### **Comandos de Controle**
#### **GRANT**: Concede privilégios.
```sql
GRANT SELECT, INSERT ON FUNCIONARIOS TO RAQUEL;
GRANT ALL ON FUNCIONARIOS TO CARLOS, ANTONIO;
GRANT SELECT ON ORGANIZACAO TO PUBLIC;
GRANT SELECT, INSERT ON FUNCIONARIOS TO RAQUEL WITH GRANT OPTION;
```
#### **REVOKE**: Revoga privilégios concedidos.
```sql
REVOKE SELECT, INSERT ON FUNCIONARIOS FROM MARIA, CARLOS;
REVOKE ALL ON FUNCIONARIOS FROM PUBLIC;
REVOKE GRANT OPTION FOR SELECT, INSERT ON FUNCIONARIOS FROM RAQUEL;
```

---

### **Roles (Papéis)**
- **Definição:** Agrupamento de privilégios.
- **Comandos:**
```sql
CREATE ROLE GERENTE;
GRANT SELECT, INSERT, UPDATE ON FUNCIONARIOS TO GERENTE;
GRANT GERENTE TO MARIA;
DROP ROLE GERENTE;
```

---

### **Profiles (Perfis)**
- **Objetivo:** Gerenciar limites de recursos e políticas de senha.
- **Criação e Atribuição:**
```sql
CREATE PROFILE DESENVOLVEDOR LIMIT
    SESSIONS_PER_USER 2
    IDLE_TIME 5
    FAILED_LOGIN_ATTEMPTS 3;

ALTER USER JOAO PROFILE DESENVOLVEDOR;
CREATE USER JOAO IDENTIFIED BY senha123 PROFILE DESENVOLVEDOR;
DROP PROFILE DESENVOLVEDOR CASCADE;
```
- **Parâmetros de Senha:**
```sql
CREATE PROFILE SEGURANCA_SENHA LIMIT
    FAILED_LOGIN_ATTEMPTS 5
    PASSWORD_LIFE_TIME 30
    PASSWORD_REUSE_TIME 90
    PASSWORD_LOCK_TIME 7;
```

---

### **Funções para Verificação de Senha**
- **Exemplo em PL/SQL:**
```sql
CREATE OR REPLACE FUNCTION verifica_senha(username VARCHAR2, password VARCHAR2, old_password VARCHAR2)
RETURN BOOLEAN AS
BEGIN
    IF LENGTH(password) < 4 THEN RETURN FALSE;
    ELSE RETURN TRUE;
    END IF;
END verifica_senha;
```

---

### **DENY**
- **Função:** Nega explicitamente privilégios e tem prioridade sobre permissões concedidas.
- **Exemplos:**
```sql
DENY SELECT ON FUNCIONARIOS TO CARLOS;
DENY UPDATE ON FUNCIONARIOS TO GERENTE;
DENY CONTROL ON SCHEMA::VENDAS TO JOAO;
DENY EXECUTE ON OBJECT::SP_ALTERAR_DADOS TO MARIA;
DENY SELECT ON FUNCIONARIOS(SALARIO) TO JOAO;
```

---

### **REVOKE vs DENY**
- **`REVOKE`:** Remove permissões sem bloquear explicitamente.
```sql
GRANT SELECT ON FUNCIONARIOS TO JOAO;
REVOKE SELECT ON FUNCIONARIOS FROM JOAO;
```
- **`DENY`:** Bloqueia acesso, mesmo que haja permissões concedidas ou herdadas.
```sql
DENY SELECT ON FUNCIONARIOS TO JOAO;
```

---

### **Resumo das Diferenças**
| Comando   | Finalidade                            | Permissões Herdadas | Uso Típico                     |
|-----------|---------------------------------------|---------------------|---------------------------------|
| `GRANT`   | Concede privilégios                  | Permitido           | Acesso inicial                 |
| `REVOKE`  | Remove privilégios                   | Permitido           | Redefinir permissões           |
| `DENY`    | Nega privilégios explicitamente      | Bloqueado           | Restrições explícitas          |

---
