
# Classes e Construtores

### 1. Módulos e Classes

- **Modularidade:**
    - Divisão do código em partes menores e independentes.
    - **Encapsulamento:**
        - Oculta a implementação interna dos módulos.
        - Exposição apenas de interfaces públicas.
- **Classes e Objetos:**
    - **Classe:**
        - Molde ou modelo que define atributos e métodos.
    - **Objeto:**
        - Instância de uma classe, representando uma entidade específica.
    - **UML:**
        - Ferramenta para modelar classes e objetos.

### 2. Exemplo: Estoque de Produtos

- **Classe Produto:**
    - **Atributos:**
        - `descricao`: String
        - `preco`: float
        - `quant`: int
    - **Métodos:**
        - `emEstoque()`: Verifica se o produto está em estoque.
        - `inicializaProduto(String, float, int)`: Inicializa um produto com valores específicos.

### 3. Construtores

- **Uso de Construtores:**
    - Inicializam objetos com valores padrão ou especificados.
    - **Características:**
        - Mesmo nome da classe.
        - Sem valor de retorno.
    - **Construtores Especializados:**
        - Permitem inicializar objetos com estados específicos.
        - Podem restringir a criação de objetos.

### Códigos de Exemplos

### Definição da Classe Produto (Java)

```java
class Produto {
    String descricao;
    float preco;
    int quant;

    boolean emEstoque() {
        return (quant > 0);
    }

    void inicializaProduto(String d, float p, int q) {
        descricao = d;
        preco = p;
        quant = q;
    }
}
```

### Uso da Classe Produto

```java
class Aplicacao {
    public static void main(String[] args) {
        Produto p = new Produto();
        p.descricao = "Shulambs";
        p.preco = 1.99F;
        p.quant = 200;

        System.out.println("Produto: " + p.descricao);
        System.out.println("Preço: " + p.preco);
        System.out.println("Estoque: " + p.quant);

        if (p.emEstoque()) {
            System.out.println("Produto em estoque.");
        }
    }
}
```

### Construtores na Classe Produto

```java
class Produto {
    String descricao;
    float preco;
    int quant;

    // Construtor padrão
    Produto() {
        descricao = "Novo Produto";
        preco = 0.01F;
        quant = 0;
    }

    // Construtor especializado
    Produto(String d, float p, int q) {
        if (d.length() >= 3)
            descricao = d;
        if (p > 0)
            preco = p;
        if (q >= 0)
            quant = q;
    }
}
```

### Uso de Construtores na Aplicação

```java
class Aplicacao {
    public static void main(String[] args) {
        Produto p1 = new Produto();  // Usando o construtor padrão
        Produto p2 = new Produto("Shulambs", 1.99F, 200);  // Usando o construtor especializado

        System.out.println("Produto: " + p1.descricao);
        System.out.println("Preço: " + p1.preco);
        System.out.println("Estoque: " + p1.quant);

        System.out.println("Produto: " + p2.descricao);
        System.out.println("Preço: " + p2.preco);
        System.out.println("Estoque: " + p2.quant);
    }
}
```

### Complemento de Conceitos Importantes

- **Semântica de Referência:**
    - Em Java, uma instância de uma classe é interpretada como uma referência a um objeto, e não o objeto em si.
    - A manipulação de objetos se dá através de referências, que são constantes e não podem ser alteradas diretamente.
- **Diferenças C++ vs Java:**
    - **C++:** Pode-se manipular diretamente apontadores (ponteiros) e referências.
    - **Java:** Referências são mais seguras, sem manipulação numérica direta, evitando erros comuns como apontar para áreas de memória inválidas.

Esses tópicos e exemplos ajudam a entender como a modularidade, encapsulamento, e o uso de construtores são essenciais para organizar e inicializar objetos em linguagens como Java.
