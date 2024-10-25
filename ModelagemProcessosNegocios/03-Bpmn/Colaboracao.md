# Colaboração

Aqui está um resumo em tópicos objetivos sobre BPMN: Colaboração, com base nas informações fornecidas:

- **Conceito de Colaboração em BPMN:**
    - Envolve a interação entre dois ou mais participantes, representados por piscinas (pools).
    - A troca de mensagens entre as piscinas é representada pelo "Fluxo de Mensagem" (Message Flow).
- **Piscinas e Raias:**
    - Piscinas podem ser do tipo "caixa preta" (sem detalhes internos) ou "caixa branca" (com elementos internos detalhados).
    - Fluxos de mensagem em piscinas "caixa preta" conectam-se à borda da piscina, enquanto em piscinas "caixa branca" conectam-se a eventos ou atividades.
- **Exemplos de Colaboração:**
    - **Interação Simples:** Um fabricante envia uma solicitação de crédito a uma instituição financeira, que responde com a decisão sobre o crédito.
    - **Interação Detalhada:** Um fornecedor, representado por duas raias (vendas e distribuição), envia uma autorização de pagamento a uma instituição financeira, que processa a solicitação e retorna a resposta.
    - **Piscina Mista:** Um processo de entrega de pedido envia uma requisição de autorização de crédito para uma instituição financeira, com uma piscina "caixa preta" e outra "caixa branca".
- **Recomendações:**
    - É recomendável especificar as mensagens trocadas nos fluxos de mensagem, embora não seja obrigatório.
- **Considerações Importantes:**
    - A borda da piscina "caixa preta" é onde o fluxo de mensagem se conecta.
    - No caso de uma piscina "caixa branca," o fluxo de mensagem conecta-se a um evento ou atividade específica dentro da piscina.