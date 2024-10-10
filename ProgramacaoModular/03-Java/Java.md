# Java

Aqui está um resumo mais objetivo e detalhado dos pontos abordados sobre a linguagem Java:

### 1. **Histórico do Java**

- Desenvolvida por James Gosling em 1991 e lançada pela Sun Microsystems em 1995.
- É uma linguagem orientada a objetos e derivada do C++.
- **Portabilidade:** Projetada para ser portável em várias arquiteturas e sistemas operacionais.
- **Compilação e Interpretação:** O código Java é compilado em bytecode, que é interpretado pela Java Virtual Machine (JVM).

### 2. **Características do Java**

- **Semântica de Referência:** Java utiliza referências ao invés de ponteiros (diferente do C++).
- **Gerenciamento Automático de Memória:** Inclui um coletor de lixo (garbage collector) que gerencia a memória, eliminando a necessidade de operações manuais como `delete`.
- **Estrutura Simples:** Não possui variáveis globais, sobrecarga de operadores, herança múltipla de classes (mas permite herança múltipla de interfaces).

### 3. **Ranking do Java**

- Em fevereiro de 2020, Java estava no topo do índice Tiobe, com 17,358% de popularidade, sendo uma das linguagens mais utilizadas.

### 4. **Estrutura de uma Aplicação Java**

- **Arquivos .java:** Contêm o código-fonte e podem incluir várias classes, com uma única classe pública que deve ter o mesmo nome do arquivo.
- **Compilação:** O código é compilado para arquivos `.class` que contêm o bytecode.
- **Pacotes (Packages):** As classes são organizadas em pacotes para melhor estruturação e encapsulamento.
- **CLASSPATH:** Diretórios onde os arquivos `.class` estão localizados, permitindo que a JVM encontre as classes compiladas.

### 5. **Aplicações Java**

- **Aplicações Console:** Executadas na JVM, utilizam as interfaces padrão de entrada e saída.
- **Aplicações Gráficas:** Usam bibliotecas como AWT e Swing para criar interfaces gráficas orientadas a eventos.
- **Método main:** Ponto de entrada para as aplicações Java. Aplicações gráficas e applets utilizam outros métodos como `start`, `init`, e `paint`.

### 6. **Exemplos de Código**

- **Aplicação Console:**

    ```java
    class AloMundo {
        public static void main(String[] args) {
            System.out.println("Alô Mundo!");
        }
    }
    ```

- **Aplicação Gráfica:**

    ```java
    import javax.swing.JOptionPane;

    public class AloMundoGraphic {
        public static void main(String[] args) {
            JOptionPane.showMessageDialog(null, "Alô Mundo!");
            System.exit(0); // encerra a aplicação
        }
    }
    ```

Esses tópicos cobrem os aspectos essenciais da linguagem Java, incluindo seu histórico, características principais, estrutura de aplicações e exemplos práticos.
