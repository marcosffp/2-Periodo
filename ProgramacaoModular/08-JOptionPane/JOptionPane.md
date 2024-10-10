# JOptionPane

### 1. **`optionType`**
   - **Tipo**: `int`
   - **Descrição**: Define quais botões são exibidos na caixa de diálogo. Utiliza constantes da classe `JOptionPane` para configurar os botões disponíveis:
       - `JOptionPane.DEFAULT_OPTION`: Sem botões específicos, permite personalizar as opções.
       - `JOptionPane.YES_NO_OPTION`: Exibe os botões "Sim" e "Não".
       - `JOptionPane.OK_CANCEL_OPTION`: Exibe os botões "OK" e "Cancelar".
   - **Exemplo no código**:
   ```java
   JOptionPane.showConfirmDialog(null, "Deseja continuar?", "Confirmação", JOptionPane.YES_NO_OPTION);
   ```

### 2. **`messageType`**
   - **Tipo**: `int`
   - **Descrição**: Define o tipo de mensagem exibida, influenciando o ícone mostrado. Utiliza constantes da classe `JOptionPane`:
       - `JOptionPane.ERROR_MESSAGE`: Mensagem de erro.
       - `JOptionPane.INFORMATION_MESSAGE`: Mensagem informativa.
       - `JOptionPane.QUESTION_MESSAGE`: Mensagem de pergunta.
       - `JOptionPane.WARNING_MESSAGE`: Mensagem de aviso.
   - **Exemplo no código**:
   ```java
   JOptionPane.showMessageDialog(null, "Operação realizada com sucesso.", "Informação", JOptionPane.INFORMATION_MESSAGE);
   ```