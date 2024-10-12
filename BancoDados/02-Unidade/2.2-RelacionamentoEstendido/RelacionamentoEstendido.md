# Unidade 2.2: Modelo ER: Relacionamento Estendido

Aqui está um resumo dos principais tópicos da Unidade 2.2 sobre Modelo Entidade-Relacionamento Estendido:

### Conceitos Avançados do M.E.R.

1. **Entidade Forte e Entidade Fraca**
    - **Entidade Forte:** Tem chave própria.
    - **Entidade Fraca:** Não tem chave própria; identificada por meio de relacionamentos com entidades fortes e atributos parciais. Representada por retângulo duplo.
2. **Atributos de Relacionamento**
    - Atributos associados a relacionamentos entre entidades, não diretamente às entidades.
3. **Relacionamentos Binários e Ternários**
    - **Binários (Grau 2):** Relacionamentos entre dois tipos de entidades.
    - **Ternários (Grau 3):** Relacionamentos envolvendo três tipos de entidades. Pode ser complexo decidir entre manter um relacionamento ternário ou desmembrar em binários.
4. **M.E.R. Estendido: Generalização e Especialização**
    - **Generalização:** Criação de um tipo de entidade genérica a partir de subtipos. Ex: Pessoa como supertipo de Pessoa Física e Pessoa Jurídica.
    - **Especialização:** Definição de subtipos a partir de um tipo de entidade genérica. Ex: Cliente Especial como uma especialização de Cliente.
    - **Hierarquia de Generalização/Especialização:**
        - **Disjunção:** Entidades do supertipo pertencem a no máximo um subtipo.
        - **Sobreposição:** Entidades do supertipo podem pertencer a múltiplos subtipos.
        - **Completude:** Total ou Parcial, referente à obrigatoriedade das entidades pertencerem a pelo menos um subtipo.
5. **Relacionamento Recursivo**
    - Relacionamento onde uma entidade se relaciona com outra ocorrência da mesma entidade. Ex: Uma disciplina que tem pré-requisitos também é uma disciplina.

### Observações Adicionais

- **Cardinalidade e Obrigatoriedade:** Representam quantas instâncias de uma entidade podem estar associadas a instâncias de outra entidade e a obrigatoriedade dessa associação.
- **Notação:** Importância de escolher nomes de relacionamentos que sejam legíveis e representem corretamente a semântica dos dados.

Essa unidade explora como representar relações mais complexas e hierarquias entre entidades para refletir melhor a realidade dos sistemas e processos.