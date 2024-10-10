# Polimorfismo

**Resumo sobre Polimorfismo:**

1. **Conceito Geral**:
    - Polimorfismo permite que um objeto seja tratado de diferentes formas, permitindo que o mesmo método apresente comportamentos distintos em classes diferentes.
2. **Tipos de Polimorfismo**:
    - **Polimorfismo Ad-hoc**: Inclui sobrecarga (overloading) e coerção de tipos.
        - **Sobrecarga**: Métodos com o mesmo nome, mas diferentes assinaturas na mesma classe.
        - **Coerção**: Conversão automática de tipos pelo compilador (por exemplo, `int` para `float`).
    - **Polimorfismo Universal**:
        - **Polimorfismo Paramétrico**: Uso de genéricos, permitindo que classes e métodos funcionem com tipos variados.
        - **Polimorfismo de Inclusão**: Herança e sobreposição de métodos, onde subclasses sobrescrevem métodos da classe base.
3. **Polimorfismo Ad-hoc**:
    - **Sobrecarga**: O mesmo método pode se comportar de forma diferente dependendo dos parâmetros.
    - **Coerção**: O compilador ajusta tipos para chamar o método mais adequado.
4. **Polimorfismo Universal de Inclusão**:
    - Classes derivadas podem sobrescrever métodos da classe base, mantendo a mesma assinatura.
    - **Amarração Tardia (Late Binding)**: A decisão de qual método será chamado ocorre em tempo de execução, baseado no tipo real do objeto.
5. **Exemplo Prático**:
    - Uma classe base pode ter um método que é sobrescrito por uma subclasse. O comportamento final é decidido pelo tipo real do objeto.
6. **Uso de `super()`**:
    - Chamado para invocar o construtor ou métodos da superclasse, garantindo a inicialização correta em subclasses.
7. **Otimização e Segurança**:
    - **Métodos e classes `final`**: Impedem a sobreposição de métodos ou extensão de classes, garantindo um comportamento fixo e, potencialmente, melhorando o desempenho ao evitar a amarração tardia.