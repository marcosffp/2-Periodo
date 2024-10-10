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