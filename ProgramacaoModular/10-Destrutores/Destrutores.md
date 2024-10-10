# Destrutores

Aqui está um resumo objetivo dos tópicos mencionados:

### 1. Alias e Semântica de Referência

- **Semântica de Referência**: Variáveis representam referências a objetos em vez de conterem os próprios objetos.
- **Alias**: Ocorre quando dois ou mais nomes (referências) se referem ao mesmo objeto, podendo causar efeitos colaterais inesperados.

### 2. Lixo de Memória e Referência Dangling

- **Lixo de Memória**: Memória alocada que se torna inacessível ao programa, geralmente devido à falta de desalocação.
- **Referência Dangling**: Ponteiro ou referência que aponta para uma área de memória já liberada, podendo causar erros ou comportamentos imprevisíveis.

### 3. Coletores de Lixo

- **Coletores de Lixo**: Processos que automaticamente liberam memória que não é mais utilizada pelo programa, eliminando lixo de memória e referências dangling.
- **Java**: Utiliza coletor de lixo automático, não exigindo desalocação manual de memória.

### 4. Finalizando um Objeto

- **Finalização de Objetos**: Antes de um objeto ser removido da memória, pendências podem ser resolvidas através do método `finalize()` na classe `Object`.
- **Exemplo**: Em Java, `finalize()` pode ser usado para fechar streams de arquivos ou atualizar contadores estáticos antes que o objeto seja coletado pelo garbage collector.

### Exemplos Práticos

- **Processa Arquivo**: Demonstra o uso do método `finalize()` para fechar um arquivo antes que o objeto seja coletado.
- **Classe Produto**: Exemplo de implementação de um destrutor em Java, usando `finalize()` para decrementar um contador de instâncias.

Este resumo abrange os principais conceitos discutidos nas aulas do professor Hugo de Paula sobre programação modular.