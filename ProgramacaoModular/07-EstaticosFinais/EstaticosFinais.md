# Membros estáticos e finais

Aqui está um resumo objetivo sobre membros estáticos e finais, com os tópicos organizados e exemplos incluídos:

---

### 1. Membros Estáticos

- **Definição**: Membros estáticos são atributos ou métodos que pertencem à classe, não a instâncias individuais.
- **Escopo e Tempo de Vida**: Um membro estático tem escopo local, mas tempo de vida global. Ele é inicializado quando a classe é carregada.
- **Utilização**: Útil para implementar contadores, identificadores de auto-incremento e definir constantes compartilhadas por todas as instâncias da classe.
- **Modificador de Acesso**: `static`.

#### Exemplo: Identificador de Produtos

```java
class Produto {
    private int id;
    private static int cont = 0;

    public static int getCont() {
        return cont;
    }

    public int getId() {
        return id;
    }

    public Produto(String d, float p, int q) {
        // Inicialização do produto
        id = ++cont;
    }

    public Produto() {
        descricao = "Novo Produto";
        preco = 0.01F;
        quant = 0;
        id = ++cont;
    }
}

class Aplicacao {
    public static void main(String args[]) {
        Produto p1 = new Produto();
        Produto p2 = new Produto("Shulambs", 1.99F, 200);

        System.out.println("Cont. produtos: " + Produto.getCont());
        System.out.println("Produto ID: " + p1.getId());
    }
}
```

### 2. Membros Finais

- **Definição**: Membros finais (`final`) são aqueles que podem ser definidos ou inicializados apenas uma vez. Uma vez atribuído, seu valor não pode ser modificado.
- **Modificador de Acesso**: `final`.
- **Tipos de Membros Finais**:
    - **Atributos Finais**: Usados para definir constantes. Se um atributo é `static final`, ele é uma constante global.
    - **Métodos Finais**: Métodos que não podem ser sobrescritos em subclasses.
    - **Classes Finais**: Classes que não podem ser estendidas.

#### Exemplo: Membros Finais

```java
class Produto {
    public static final String DESCRICAO_PADRAO = "Shulambs";
    public static final int MAX_ESTOQUE = 1000;

    private String descricao;
    private int quant;

    public void setQuant(int q) {
        if (q >= 0 && q <= MAX_ESTOQUE) {
            quant = q;
        }
    }

    public Produto() {
        descricao = DESCRICAO_PADRAO;
        preco = 0.01F;
        quant = 0;
    }
}

class Aplicacao {
    public static void main(String args[]) {
        Produto p1 = new Produto();
        int novosProdutos = 100; // Exemplo simplificado

        if ((p1.getQuant() + novosProdutos) > Produto.MAX_ESTOQUE) {
            System.out.println("Estouro do limite máximo do estoque.");
        } else {
            p1.setQuant(p1.getQuant() + novosProdutos);
        }
    }
}
```

### 3. Membros Estáticos e Finais

- **Combinação**: Membros `static final` são constantes globais que pertencem à classe e não podem ser modificados.
- **Exemplo**: Um atributo `static final` em uma classe pode ser utilizado para armazenar constantes como `MAX_ESTOQUE` ou `DESCRICAO_PADRAO`.

#### Exemplo: Atributo `static final`

```java
static final int NUMERO = 42;
static final ImmutableList<String> MESES = ImmutableList.of("janeiro", "fevereiro", "março");
```

---

Esse resumo cobre os principais conceitos de membros estáticos e finais, com exemplos de código para ilustrar cada tópico.