### Coleções, Interfaces, Streams e Polimorfismo em Java

1. **Coleções (Java Collections Framework)**:
   - Estruturas de dados como listas, conjuntos e mapas para armazenar e manipular objetos.
   - Exemplos: `ArrayList`, `HashSet`, `HashMap`.
   - **Exemplo**:
     ```java
     List<String> list = new ArrayList<>();
     list.add("Bernardo");
     list.add("Carolina");
     for (String s : list) {
         System.out.println(s);
     }
     ```

2. **Interfaces (Collection, Set, List, Queue, Map)**:
   - Contratos que definem métodos que as classes devem implementar.
   - **Exemplo com `Set`**:
     ```java
     Set<String> conjunto = new HashSet<>();
     conjunto.add("Ana");
     conjunto.add("Bernardo");
     System.out.println(conjunto);
     ```

3. **Streams e Pipelines**:
   - Abordagem funcional para processar coleções.
   - Permitem operações como filtro, mapeamento e redução.
   - **Exemplo com Stream**:
     ```java
     List<String> estoque = Arrays.asList("Item1", "Item2", "Item3");
     estoque.stream().forEach(System.out::println);
     ```

4. **Comparator**:
   - Interface usada para definir regras de ordenação de objetos.
   - **Exemplo de Ordenação**:
     ```java
     listaDeProdutos.sort(new Comparator<Produto>() {
         @Override
         public int compare(Produto p1, Produto p2) {
             return p1.getDescricao().compareTo(p2.getDescricao());
         }
     });
     ```

5. **Polimorfismo e Streams**:
   - Uso de polimorfismo e streams para simplificar cálculos e ordenações.
   - **Exemplo com Stream para somar quantidades**:
     ```java
     int totalEmEstoque = listaDeProdutos.stream()
         .mapToInt(Produto::getQuant)
         .sum();
     ```

6. **Métodos Parametrizáveis**:
   - Métodos que recebem condições e critérios de ordenação.
   - **Exemplo com `Predicate` e `Comparator`**:
     ```java
     public List<Produto> ordenarStream(Predicate<Produto> p, Comparator<Produto> c) {
         return listaDeProdutos.stream()
             .filter(p)
             .sorted(c)
             .collect(Collectors.toList());
     }
     ```

7. **Exemplo de Polimorfismo de Inclusão**:
   - Iteração tradicional para cálculo total.
   - **Exemplo**:
     ```java
     public int totalEmEstoque() {
         int total = 0;
         for (int i = 0; i < numProdutos; i++) {
             total += listaDeProdutos[i].getQuant();
         }
         return total;
     }
     ```