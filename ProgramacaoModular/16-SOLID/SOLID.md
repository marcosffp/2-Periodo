Aqui está a hierarquia reorganizada do tópico **SOLID**:

# SOLID

Os princípios SOLID ajudam a desenvolver software modular e de fácil manutenção, tornando o código mais organizado e flexível. Os cinco princípios são:

1. **S** - Single Responsibility Principle (SRP)
2. **O** - Open/Closed Principle (OCP)
3. **L** - Liskov Substitution Principle (LSP)
4. **I** - Interface Segregation Principle (ISP)
5. **D** - Dependency Inversion Principle (DIP)

## 1. S - Princípio da Responsabilidade Única (Single Responsibility Principle)

O **SRP** sugere que uma classe deve ser responsável por apenas um motivo para mudança.

### Exemplo Incorreto:
```java
public class GerenciadorTarefas {
    public String conectarAPI() { /*...*/ }
    public void criarTarefa() { /*...*/ }
    public void atualizarTarefa() { /*...*/ }
    public void enviarNotificacao() { /*...*/ }
    public void produzirRelatorio() { /*...*/ }
}
```
A classe `GerenciadorTarefas` possui muitas responsabilidades, como conectar APIs, gerenciar tarefas e gerar relatórios, violando o SRP.

### Exemplo Correto:
```java
public class GerenciadorTarefas {
    public void criarTarefa() { /*...*/ }
    public void atualizarTarefa() { /*...*/ }
}
public class ConectorAPI {
    public String conectarAPI() { /*...*/ }
}
public class GeradorRelatorio {
    public void produzirRelatorio() { /*...*/ }
}
```
Agora, cada classe tem apenas uma responsabilidade, facilitando a manutenção.

## 2. O - Princípio Aberto-Fechado (Open Closed Principle)

O **OCP** defende que uma classe deve ser aberta para extensão, mas fechada para modificação. Isso significa que novas funcionalidades devem ser adicionadas sem modificar o código original.

### Exemplo Incorreto:
```java
public class AprovaExame {
    public void aprovarSolicitacaoExame(Exame exame) {
        if (exame.tipo == SANGUE) { /*...*/ }
        else if (exame.tipo == RAIOX) { /*...*/ }
    }
}
```
Adicionar novos tipos de exame exigirá mais modificações na classe, tornando o código complexo.

### Exemplo Correto:
```java
public interface AprovaExame {
    void aprovarSolicitacaoExame(Exame exame);
}
public class AprovaExameSangue implements AprovaExame {
    public void aprovarSolicitacaoExame(Exame exame) { /*...*/ }
}
public class AprovaRaioX implements AprovaExame {
    public void aprovarSolicitacaoExame(Exame exame) { /*...*/ }
}
```
Aqui, o código pode ser estendido com novos tipos de exames sem alterar as classes já existentes.

## 3. L - Princípio da Substituição de Liskov (Liskov Substitution Principle)

O **LSP** afirma que objetos de uma classe derivada devem poder substituir objetos da classe base sem alterar a funcionalidade esperada.

### Exemplo Incorreto:
```java
public class Estudante {
    public void entregarTCC() { /*...*/ }
}
public class EstudantePosGraduacao extends Estudante {
    @Override
    public void entregarTCC() { throw new UnsupportedOperationException(); }
}
```
`EstudantePosGraduacao` não deveria ser obrigado a implementar `entregarTCC()`, pois isso viola o LSP.

### Exemplo Correto:
```java
public class EstudanteDeGraduacao extends Estudante {
    public void entregarTCC() { /*...*/ }
}
public class EstudanteDePosGraduacao extends Estudante {
    public void estudar() { /*...*/ }
}
```
Agora, as subclasses representam melhor suas responsabilidades e podem substituir `Estudante` sem problemas.

## 4. I - Princípio da Segregação de Interface (Interface Segregation Principle)

O **ISP** afirma que uma classe não deve ser forçada a implementar interfaces e métodos que não serão utilizados.

### Exemplo Incorreto:
```java
public interface Funcionario {
    BigDecimal salario();
    BigDecimal gerarComissao();
}
```
Neste caso, `Recepcionista` não deveria implementar `gerarComissao()`, pois isso viola o ISP.

### Exemplo Correto:
```java
public interface Funcionario {
    BigDecimal salario();
}
public interface Comissionavel {
    BigDecimal gerarComissao();
}
```
Agora, `Recepcionista` implementa apenas o que é necessário, e `Vendedor` pode implementar tanto `Funcionario` quanto `Comissionavel`.

## 5. D - Princípio da Inversão de Dependência (Dependency Inversion Principle)

O **DIP** defende que dependências devem ser invertidas: dependa de abstrações, não de implementações concretas.

### Exemplo Incorreto:
```java
public class PedidoService {
    private PedidoRepository repository = new PedidoRepository();
    public void processarPedido(Pedido pedido) {
        repository.salvarPedido(pedido);
    }
}
```
Aqui, `PedidoService` está acoplado a uma implementação específica de `PedidoRepository`.

### Exemplo Correto:
```java
public interface PedidoRepository {
    void salvarPedido(Pedido pedido);
}
public class PedidoService {
    private PedidoRepository repository;
    public PedidoService(PedidoRepository repository) {
        this.repository = repository;
    }
    public void processarPedido(Pedido pedido) {
        repository.salvarPedido(pedido);
    }
}
```
Agora, `PedidoService` depende de uma abstração, o que aumenta a flexibilidade e facilita a manutenção.