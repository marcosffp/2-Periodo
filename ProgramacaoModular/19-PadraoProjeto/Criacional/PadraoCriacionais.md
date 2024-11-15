### Padrões Criacionais
**Características Gerais:**
- Responsáveis pela criação de objetos.
- Aumentam a flexibilidade ao determinar o que criar, como criar e quando criar objetos.
- Principais exemplos: 
  - **Comuns:** Factory Method, Abstract Factory, Singleton.
  - **Menos comuns:** Builder, Prototype.

---

### **Singleton**
**Características:**
- **Propósito:** Garantir que uma classe tenha apenas **uma instância** e fornecer um acesso global a ela.
- **Quando usar:** 
  - É necessário um único objeto para coordenar ações.
  - Exemplo: Logging.
- **Implementação:**
  - Atributo estático e final para armazenar a instância.
  - Construtor privado para evitar múltiplas instâncias.
  - Método público estático para retornar a instância.

**Variações:**
1. **Com acesso global:**
   - Usa métodos públicos para acesso.
2. **Sem acesso global:**
   - Verifica no construtor se a classe já foi instanciada.

**Alternativa:** 
- **Classe utilitária estática:** Sem estado, útil para métodos comuns como `Math` e `System`.

---

### **Factory Method**
**Características:**
- **Propósito:** Permite criar objetos sem expor a lógica de criação ao cliente.
- **Quando usar:** 
  - Deseja-se encapsular a instanciação de tipos concretos.
  - Instância concreta será decidida por subclasses.

**Componentes:**
1. **Produto:** Interface para os objetos criados.
2. **ProdutoConcreto:** Implementação do Produto.
3. **Criador:** Declara o método fábrica (factory method).
4. **CriadorConcreto:** Implementa o método para criar um ProdutoConcreto.

**Exemplo: Fábrica de Formas**
- **Produtos:** `Forma` (interface), implementado por `Circulo`, `Quadrado`, `Retangulo`.
- **Fábrica:** Classe `FabricaDeFormas` decide qual forma criar com base em um tipo.

**Vantagens:**
- Encapsula a lógica de criação.
- Facilita a adição de novos tipos sem alterar código existente.

