### 1. **Iterador e Métodos Comuns**
   - **Iterador<T>**: Interface usada para iterar elementos de uma coleção.
   - **hasNext()**: Verifica se há mais elementos.
     ```java
     Iterator<String> it = list.iterator();
     while (it.hasNext()) {
         System.out.println(it.next());
     }
     ```
   - **next()**: Retorna o próximo elemento da coleção.

### 2. **Stream API e Operações Comuns**
   - **stream()**: Cria um fluxo (stream) de uma coleção.
     ```java
     List<Integer> list = Arrays.asList(1, 2, 3, 4, 5);
     list.stream().forEach(System.out::println);
     ```
   - **filter()**: Filtra elementos com base em uma condição.
     ```java
     list.stream().filter(x -> x > 2).forEach(System.out::println);
     ```
   - **mapToDouble()**: Mapeia cada elemento para um `double`.
     ```java
     double sum = list.stream().mapToDouble(x -> x).sum();
     ```
   - **average()**: Calcula a média.
     ```java
     list.stream().mapToDouble(x -> x).average().ifPresent(System.out::println);
     ```
   - **getAsDouble()**: Obtém o valor `double` de um `OptionalDouble`.
   - **orElse()**: Retorna um valor padrão se `Optional` estiver vazio.
     ```java
     double avg = list.stream().mapToDouble(x -> x).average().orElse(0.0);
     ```
   - **findFirst()**: Retorna o primeiro elemento que atende à condição.
     ```java
     list.stream().filter(x -> x > 2).findFirst().ifPresent(System.out::println);
     ```
   - **reduce(0, (x, y) -> x + y)**: Reduz o stream a um único valor somando elementos.
     ```java
     int sum = list.stream().reduce(0, (x, y) -> x + y);
     ```

### 3. **Collectors e Métodos de Coleta**
   - **collect(Collectors.toList())**: Coleta elementos em uma lista.
     ```java
     List<Integer> filteredList = list.stream().filter(x -> x > 2).collect(Collectors.toList());
     ```
   - **collect(Collectors.toSet())**: Coleta elementos em um conjunto.
   - **distinct()**: Remove elementos duplicados.
   - **count()**: Conta elementos.
     ```java
     long count = list.stream().distinct().count();
     ```
   - **sum()**: Soma os valores em um `IntStream` ou `DoubleStream`.
   - **max()**: Encontra o valor máximo.
     ```java
     int max = list.stream().max(Integer::compareTo).orElse(0);
     ```
   - **max(Comparator.comparingDouble(Funcionario::getSalario)).orElse(null)**: Retorna o funcionário com o maior salário ou `null` se a lista estiver vazia.
   - **min()**: Encontra o valor mínimo.

### 4. **Estruturas de Coleção e Mapas**
   - **List**:
     - **ArrayList**: Implementação de lista que permite duplicatas e mantém ordem de inserção.
       ```java
       List<String> arrayList = new ArrayList<>();
       arrayList.add("A");
       ```
   - **Set**:
     - **HashSet**: Não permite duplicatas e não mantém ordem.
       ```java
       Set<String> hashSet = new HashSet<>();
       ```
     - **LinkedHashSet**: Mantém a ordem de inserção.
     - **SortedSet**: Interface de conjunto ordenado, implementada por `TreeSet`.
     - **TreeSet**: Mantém elementos ordenados.
       ```java
       Set<Integer> treeSet = new TreeSet<>(Arrays.asList(3, 1, 4));
       ```

   - **Map**:
     - **HashMap**: Mapa não ordenado.
       ```java
       Map<String, Integer> hashMap = new HashMap<>();
       ```
     - **LinkedHashMap**: Mapa que mantém a ordem de inserção.
     - **SortedMap**: Interface de mapa ordenado.
     - **TreeMap**: Mapa ordenado pelas chaves.

   - **Queue e Deque**: Estruturas de fila.
     ```java
     Queue<String> queue = new LinkedList<>();
     Deque<String> deque = new LinkedList<>();
     ```

### 5. **Wildcard e Bounds (`?`)**  
   - **List<?>**: Lista de elementos de qualquer tipo.
   - **? extends T**: Define um limite superior. Permite acessar elementos de tipo específico, mas não adicionar.
     ```java
     List<? extends Number> list = Arrays.asList(1, 2, 3);
     Number n = list.get(0); // Leitura permitida
     ```
   - **? super T**: Define um limite inferior. Permite adicionar elementos do tipo especificado.
     ```java
     List<? super Integer> list = new ArrayList<>();
     list.add(1); // Escrita permitida
     ```
