### Resumo sobre Polimorfismo Paramétrico e Generics em Java

#### 1. **Polimorfismo Paramétrico**
   - Permite que funções ou classes operem sobre diferentes tipos de dados sem conhecimento específico dos tipos.
   - Exemplo de classe parametrizada:
     ```java
     public class Caixa<T> {
         private T conteudo;
         public void colocar(T conteudo) { this.conteudo = conteudo; }
         public T pegar() { return conteudo; }
     }
     ```

#### 2. **Generics em Java**
   - Introduzidos para proporcionar **segurança de tipos** e **reutilização de código**.
   - Classes e métodos podem aceitar tipos genéricos, melhorando a flexibilidade.
   
   - **Exemplo com tipo genérico `T`**:
     ```java
     public class Par<T, U> {
         private T primeiro;
         private U segundo;
         public Par(T primeiro, U segundo) {
             this.primeiro = primeiro;
             this.segundo = segundo;
         }
         public T getPrimeiro() { return primeiro; }
         public U getSegundo() { return segundo; }
     }
     ```

#### 3. **Nomenclatura Comum em Generics**
   - **T (Tipo)**: Representa qualquer tipo genérico.
     ```java
     public class Caixa<T> { ... }
     ```
   - **E (Elemento)**: Usado em coleções como `List<E>`.
     ```java
     public interface List<E> { void add(E e); }
     ```
   - **N (Número)**: Representa um tipo numérico (`Integer`, `Double`).
     ```java
     public class Calculadora<N extends Number> { ... }
     ```
   - **K (Chave)** e **V (Valor)**: Usados em estruturas chave-valor, como `Map<K, V>`.
     ```java
     public class Mapa<K, V> { ... }
     ```

#### 4. **Restrições de Tipos**
   - **Sem restrição (`<T>`)**: Aceita qualquer tipo.
     ```java
     public class Caixa<T> { ... }
     ```
   - **Com restrição (`<T extends Number>`)**: Aceita apenas tipos numéricos.
     ```java
     public class Calculadora<T extends Number> { ... }
     ```

#### 5. **Métodos Genéricos**
   - Definidos com parâmetros de tipo para aceitar e processar diferentes tipos de dados.
   - Exemplo:
     ```java
     public static <T> void imprimirArray(T[] array) {
         for (T elemento : array) {
             System.out.println(elemento);
         }
     }
     ```

#### 6. **Vantagens dos Generics**
   - **Segurança de Tipos**: Detecta erros de tipo em tempo de compilação.
   - **Reusabilidade**: Mesma classe/método pode ser utilizado com diferentes tipos.

### Exemplos
1. **Exemplo com `T` (Tipo Genérico)**:
   ```java
   Caixa<String> caixaTexto = new Caixa<>();
   caixaTexto.colocar("Texto Exemplo");
   System.out.println(caixaTexto.pegar());
   ```

2. **Exemplo com `N extends Number` (Restrição a Números)**:
   ```java
   Calculadora<Integer> calc = new Calculadora<>();
   System.out.println(calc.somar(10, 20));  // Output: 30.0
   ```

