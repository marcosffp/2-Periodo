# Classe Abstrata

Aqui está um resumo focado apenas em **classe abstrata**:

### Classe Abstrata

- **Definição**: Uma classe que não pode ser instanciada diretamente, servindo como base para outras classes. Ela pode conter métodos concretos e abstratos.

### Características de uma Classe Abstrata:

1. **Métodos Abstratos**: Métodos que não têm implementação na classe abstrata e devem ser implementados pelas subclasses.
2. **Métodos Concretos**: Métodos com implementação que podem ser compartilhados entre subclasses.
3. **Impossibilidade de Instanciação**: Não é possível criar objetos diretamente de uma classe abstrata.
4. **Herança**: Subclasses devem herdar de uma classe abstrata e são obrigadas a implementar seus métodos abstratos.

### Quando Usar Classes Abstratas:

- **Estrutura Comum**: Quando várias classes compartilham uma estrutura comum, mas a implementação de certos métodos varia.
- **Forçar Implementação**: Quando deseja-se garantir que as subclasses forneçam implementações específicas para métodos.

### Exemplo:

- Uma classe `Animal` abstrata pode ter o método abstrato `fazerSom()`, forçando todas as subclasses como `Cachorro` e `Gato` a implementar suas próprias versões desse método.

### Benefícios:

- **Organização do código**: Facilita a criação de uma estrutura padronizada.
- **Reuso**: Métodos concretos em uma classe abstrata podem ser reutilizados em várias subclasses.

### Diferença com Interfaces:

- As classes abstratas podem ter métodos concretos (com corpo), enquanto interfaces só possuem métodos abstratos (dependendo da versão do Java).