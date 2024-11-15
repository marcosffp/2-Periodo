### **Padrões Estruturais**
**Características Gerais:**
- Focam em como organizar e estruturar classes e objetos.
- Usam herança e composição para criar relações entre classes e objetos.
- Principais usos:
  - Simplificar a interação entre objetos complexos.
  - Permitir extensibilidade e flexibilidade.
- **Exemplos mais comuns:** Adapter, Bridge, Decorator, Facade.
- **Exemplos menos comuns:** Flyweight, Proxy.

---

### **Adapter**
**Propósito:**
- Converte a interface de uma classe para outra interface esperada pelos clientes.
- **Quando usar:**
  - Quando classes incompatíveis precisam trabalhar juntas.
  - Para reutilizar uma classe existente sem modificá-la.

**Tipos:**
1. **Não polimórfico:** Adapta diretamente métodos sem extensibilidade.
2. **Polimórfico (padrão):** Usa herança ou interfaces para criar adaptadores flexíveis.

**Exemplo:**
- Conectar uma API antiga com um novo sistema, adaptando as chamadas entre eles.

**Vantagens:**
- Promove a reutilização de código existente.
- Facilita a integração de sistemas legados.

---

### **Decorator**
**Propósito:**
- Adiciona dinamicamente responsabilidades ou funcionalidades a um objeto, sem alterar sua estrutura.
- **Quando usar:**
  - Substituir herança em cenários onde várias combinações de funcionalidades são necessárias.
  - Extender o comportamento de objetos em tempo de execução.

**Componentes:**
1. **Componente:** Interface ou classe base que define o comportamento padrão.
2. **ComponenteConcreto:** Implementação básica do componente.
3. **Decorator:** Classe abstrata que implementa o componente e contém uma referência a outro componente.
4. **DecoratorConcreto:** Adiciona responsabilidades específicas ao componente decorado.

**Exemplo: Pizzaria**
- **Componente:** Pizza básica.
- **Decoradores:** Adicionam ingredientes como queijo, tomate, ou pepperoni.

**Vantagens:**
- Alta flexibilidade para adicionar ou combinar funcionalidades.
- Mantém classes simples e focadas.

---

**Resumo dos Benefícios dos Padrões Estruturais:**
- **Adapter:** Conecta sistemas incompatíveis, promovendo reutilização.
- **Decorator:** Extende funcionalidades de objetos de forma modular e flexível.