### Resumo: Herança e Herança Simples

1. **Definição de Herança:**
    - Mecanismo que permite a criação de novas classes baseadas em uma classe existente.
    - Relação de "é um tipo de", permitindo reuso de comportamentos e características.
    - Baseada em dois princípios: **especificação** (top-down) e **generalização/abstração** (bottom-up).
2. **Herança Simples:**
    - Uma classe derivada (subclasse) é criada a partir de apenas uma classe base (superclasse).
    - Exemplos:
        - Um professor é uma pessoa.
        - Um automóvel é um veículo.
    - Em Java, utiliza-se a palavra-chave `extends` para definir herança.
3. **Exemplo de Herança Simples:**
    - Classe `Pessoa` com atributos como `dataNascimento`, `nome` e método `calculaIdade()`.
    - Subclasses:
        - `Professor`: adiciona atributos `salario` e `cargaHoraria`, e método `calcular13o()`.
        - `Aluno`: adiciona `idCurso`, `cargaMatriculada` e método `calculaMensalidade()`.
4. **Construtores em Classes Estendidas:**
    - O construtor de uma subclasse pode chamar o construtor da superclasse usando `super()`.
    - Se nenhum construtor for especificado, o construtor padrão da superclasse é invocado.
5. **Exemplo de Herança de Produto:**
    - Classe `Produto` com atributos como `descricao`, `quant`, `preco`, e métodos relacionados ao estoque.
    - Subclasses:
        - `BemDeConsumo`: adiciona atributo `dataValidade` e métodos para manipular a validade.
        - `BemDuravel`: adiciona `mesesGarantia` e métodos para gerenciar a garantia.

Esses tópicos abordam de forma objetiva o conceito de herança em Java, exemplificando com cenários práticos de uso em classes de produtos e construção de objetos em herança simples.