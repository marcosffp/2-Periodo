# Interface

### Resumo: Interfaces - Fundamentos e Aspectos de Projeto

**1. Definição de Interface**

- Interface: parte visível de um módulo para outros módulos.
- Oferece um grupo coerente de métodos.
- Promove extensibilidade e baixo acoplamento no sistema.

**2. Interfaces em Java**

- Declaração de métodos sem implementação.
- Atributos são `public static final`.
- Usadas para definir protocolos de comportamento.
- Solução para o problema de herança múltipla.

**3. Exemplo: Timer e Wakeable**

- `Timer`: notifica objetos acordáveis após um certo tempo.
- `Wakeable`: interface com método `wakeUp()` a ser implementado pelas classes.

**4. Interfaces versus Classes Abstratas**

- Interface define métodos, mas não implementações.
- Classes abstratas podem conter implementações.
- Interfaces permitem múltipla herança, enquanto classes não.

**5. Métodos Default**

- Introduzidos no Java 8.
- Permitem implementação em interfaces sem quebrar código existente.
- Podem gerar conflitos de herança múltipla.

**6. Expressões Lambda e Interfaces Funcionais**

- Programação funcional: ênfase em funções "puras" e imutabilidade.
- Interfaces funcionais têm um único método abstrato.
- Exemplo: `Comparator<T>` pode ser implementada com lambdas.

Aqui está um resumo sobre o uso de interfaces no contexto dos exemplos fornecidos:

### Interfaces e Comparação em Java

- **Interface `Comparable`:**
  - Fornece um método padrão para comparar objetos da própria classe.
  - Deve ser implementada diretamente na classe para definir uma ordem natural.
  - Exemplo:
    ```java
    public abstract class Produto implements Comparable<Produto> {
        @Override
        public int compareTo(Produto o) {
            return this.descricao.compareToIgnoreCase(o.getDescricao());
        }
    }
    ```
  - No exemplo acima, a classe `Produto` implementa `Comparable<Produto>`, e a comparação é feita com base no campo `descricao`.

- **Interface `Comparator`:**
  - Usada para definir múltiplas formas de comparação entre objetos de uma classe.
  - Pode ser implementada como uma classe separada ou como uma classe anônima dentro de um método.
  - Permite flexibilidade ao ordenar por diferentes atributos de um objeto.
  - Exemplo de classe interna:
    ```java
    private class OrdenarPorQuantidade implements Comparator<Produto> {
        @Override
        public int compare(Produto o1, Produto o2) {
            return Integer.compare(o1.getQuantidade(), o2.getQuantidade());
        }
    }
    ```
  - Exemplo de uso de classe anônima:
    ```java
    Arrays.sort(produtos, 0, numProdutos, new Comparator<Produto>() {
        @Override
        public int compare(Produto o1, Produto o2) {
            return o1.getDataFabricacao().compareTo(o2.getDataFabricacao());
        }
    });
    ```
  - Exemplo de expressão lambda:
    ```java
    Arrays.sort(produtos, 0, numProdutos, (o1, o2) -> Float.compare(o1.getPreco(), o2.getPreco()));
    ```

### Resumo dos Conceitos:
- **`Comparable`:**
  - Definição da ordem natural.
  - Comparação é feita dentro da própria classe.

- **`Comparator`:**
  - Permite diferentes comparações.
  - Pode ser implementado por classes externas, internas, anônimas ou lambdas.
  - Usado para ordenar por diferentes atributos (quantidade, preço, data, etc.).

Este resumo explica como as interfaces `Comparable` e `Comparator` são utilizadas para ordenar objetos de diferentes maneiras.