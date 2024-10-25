# Gateway

Aqui está o resumo em tópicos objetivos sobre Gateways em BPMN:

1. **Definição de Gateway**:
    - Controla pontos de divergência e convergência no fluxo.
    - Não toma decisões, apenas distribui o fluxo.
2. **Representação Visual**:
    - Representados por losangos.
3. **Tipos de Gateways**:
    - **Gateway Exclusivo**:
        - Utilizado para indicar decisão com base em uma condição.
        - A decisão deve ser tomada antes do Gateway.
        - Pode ter vários caminhos, mas apenas um é seguido.
        - Simbologia: losango vazio ou com um "X".
    - **Gateway Paralelo**:
        - Permite a execução de atividades em paralelo.
        - Exige que todos os caminhos paralelos sejam concluídos antes de prosseguir.
        - Simbologia: losango com um "+" dentro.
    - **Gateway Inclusivo**:
        - Permite ativar um ou mais caminhos dentre os disponíveis.
        - Usado para combinações de caminhos.
        - Simbologia: losango com um círculo interno.
4. **Uso de Gateways**:
    - Abertura e fechamento do fluxo devem usar o mesmo tipo de Gateway (paralelo, exclusivo, inclusivo).
5. **Recomendações**:
    - Não é obrigatório colocar perguntas nos Gateways.
    - É essencial indicar o que cada caminho representa após o Gateway.