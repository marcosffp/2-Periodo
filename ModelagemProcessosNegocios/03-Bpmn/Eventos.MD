# Eventos

Aqui está um resumo em tópicos objetivos sobre os eventos em BPMN:

1. **Eventos em BPMN**:
    - Representam algo que ocorre durante o processo.
    - Podem iniciar, atrasar, suspender ou finalizar um processo.
2. **Tipos de Eventos**:
    - **Evento de Início**: Círculo de borda fina, marca o início do processo.
    - **Evento Intermediário**: Círculo de borda dupla, ocorre entre o início e o fim do processo.
    - **Evento de Fim**: Círculo de borda espessa, indica o término do processo.
3. **Tipos Comuns de Eventos**:
    - **None**: Usado quando o início/fim do processo é indefinido.
    - **Timer**: Relacionado a tempo, como datas específicas ou frequências.
    - **Mensagem**: Dispara o processo ao receber uma mensagem.
    - **Sinal**: Comunicação que pode ser ouvida por vários, mas só alguns agem.
    - **Condicional**: Disparado por uma condição específica.
    - **Múltiplo**: Várias formas de acionar o processo (paralelo ou único).
4. **Eventos Intermediários**:
    - **None**: Usado quando o motivo do evento ainda não é especificado.
    - **Timer**: Pode causar atraso no fluxo do processo.
    - **Envio de Mensagem**: Envia mensagens curtas, geralmente automáticas.
    - **Recebimento de Mensagem**: Recebe mensagens curtas e automáticas.
5. **Eventos de Término**:
    - **None**: Usado quando o fim do processo não é específico.
    - **Terminate**: Interrompe imediatamente todas as atividades do processo.