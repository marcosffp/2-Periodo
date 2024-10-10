# JFreeChart

Este exemplo mostra como usar a biblioteca JFreeChart para criar gráficos de barras e exibir dados como histograma. O exemplo inclui a criação de um gráfico de barras, a manipulação de um conjunto de dados e a exibição dos dados de escolaridade.

### 1. **Criação do Gráfico de Barras Simples**

Este primeiro código cria um gráfico de barras simples e exibe-o dentro de um painel Swing.

```java
import org.jfree.chart.ChartFactory;
import org.jfree.chart.ChartPanel;
import org.jfree.chart.JFreeChart;
import org.jfree.data.category.DefaultCategoryDataset;

import javax.swing.*;

public class ExemploGrafico {
    public static void main(String[] args) {
        // Criar o conjunto de dados
        DefaultCategoryDataset dataset = new DefaultCategoryDataset();

        // Adicionar dados
        dataset.addValue(1.0, "Série 1", "Categoria 1");
        dataset.addValue(4.0, "Série 1", "Categoria 2");
        dataset.addValue(3.0, "Série 1", "Categoria 3");
        dataset.addValue(5.0, "Série 1", "Categoria 4");

        // Criar o gráfico
        JFreeChart chart = ChartFactory.createBarChart(
                "Título do Gráfico",  // Título
                "Categoria",          // Eixo X
                "Valor",              // Eixo Y
                dataset               // Conjunto de dados
        );

        // Exibir o gráfico em um painel
        ChartPanel panel = new ChartPanel(chart);
        panel.setPreferredSize(new java.awt.Dimension(800, 600));

        JFrame frame = new JFrame();
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.add(panel);
        frame.pack();
        frame.setVisible(true);
    }
}
```

### 2. **Histograma de Escolaridade**

Este exemplo cria um histograma de formação acadêmica com base nos dados cadastrados, usando um gráfico de barras. Ele verifica se há pessoas cadastradas e exibe um histograma da escolaridade.

```java
import org.jfree.chart.ChartFactory;
import org.jfree.chart.ChartPanel;
import org.jfree.chart.JFreeChart;
import org.jfree.chart.plot.PlotOrientation;
import org.jfree.chart.renderer.category.BarRenderer;
import org.jfree.data.category.DefaultCategoryDataset;

import javax.swing.*;
import java.awt.*;

public class HistogramaEscolaridade {

    public static void exibirHistogramaEscolaridade(Pessoa[] listaPessoas, int totalCadastrado) {
        if (totalCadastrado == 0) {
            JOptionPane.showMessageDialog(
                null,
                "Não há pessoas cadastradas no sistema. Por favor, cadastre algumas pessoas para visualizar o histograma.",
                "Nenhum Cadastro Encontrado",
                JOptionPane.INFORMATION_MESSAGE
            );
            return;
        }

        Escolaridade[] todasEscolaridades = Escolaridade.values();
        int[] contagemEscolaridades = new int[todasEscolaridades.length];

        // Contar a quantidade de cada tipo de escolaridade
        for (Pessoa pessoa : listaPessoas) {
            Escolaridade escolaridade = pessoa.getEscolaridade();
            for (int i = 0; i < todasEscolaridades.length; i++) {
                if (todasEscolaridades[i] == escolaridade) {
                    contagemEscolaridades[i]++;
                    break;
                }
            }
        }

        // Criar o conjunto de dados para o gráfico
        DefaultCategoryDataset datasetGrafico = new DefaultCategoryDataset();
        for (int i = 0; i < contagemEscolaridades.length; i++) {
            datasetGrafico.addValue(
                contagemEscolaridades[i], "Formação Acadêmica", todasEscolaridades[i].toString());
        }

        // Criar o gráfico
        JFreeChart grafico = ChartFactory.createBarChart(
            "Distribuição de Formação Acadêmica",      // Título
            "Formação Acadêmica",                      // Eixo X
            "Número de Pessoas",                       // Eixo Y
            datasetGrafico,                            // Conjunto de dados
            PlotOrientation.VERTICAL,                  // Orientação
            false,                                     // Exibir legenda
            true,                                      // Mostrar dicas de ferramentas
            false                                      // URLs
        );

        // Configurar a cor das barras
        BarRenderer renderizador = (BarRenderer) grafico.getCategoryPlot().getRenderer();
        for (int i = 0; i < todasEscolaridades.length; i++) {
            renderizador.setSeriesPaint(i, Color.BLUE); // Definir cor para as barras
        }

        // Configurar o painel do gráfico
        ChartPanel painelGrafico = new ChartPanel(grafico);
        painelGrafico.setPreferredSize(new java.awt.Dimension(400, 300));

        // Criar e configurar o frame
        JFrame frameGrafico = new JFrame();
        frameGrafico.setDefaultCloseOperation(JFrame.DISPOSE_ON_CLOSE);
        frameGrafico.add(painelGrafico);
        frameGrafico.pack();
        frameGrafico.setLocationRelativeTo(null);

        // Exibir o gráfico
        JOptionPane.showMessageDialog(
            null, frameGrafico.getContentPane(), "Histograma de Formação Acadêmica", JOptionPane.PLAIN_MESSAGE);
    }
}
```

### Descrição do Código:
1. **Criação do Dataset**: Os dados são adicionados ao `DefaultCategoryDataset`, que armazena os valores a serem exibidos no gráfico.
2. **Criação do Gráfico**: O método `ChartFactory.createBarChart` é usado para gerar um gráfico de barras vertical, com rótulos e dados.
3. **Renderização do Gráfico**: O gráfico é renderizado em um `ChartPanel`, que é então adicionado a um `JFrame` para ser exibido.
4. **Histograma de Escolaridade**: O método `exibirHistogramaEscolaridade` exibe um histograma da escolaridade das pessoas cadastradas no sistema, contando o número de pessoas por tipo de escolaridade e exibindo-o como um gráfico de barras.

Esse exemplo usa o JFreeChart para visualização e o `JOptionPane` para exibir o gráfico dentro de um `JFrame`.