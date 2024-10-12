# Unidade 2.1: Modelagem de Dados e/ Modelo ER: Relacionamentos

Aqui está o resumo em tópicos objetivos:

1. *Entidade vs. Relacionamento*:
    - Entidades são os objetos principais da modelagem.
    - Relacionamentos conectam entidades de acordo com as regras de negócio.
2. *Tipos de Relacionamentos*:
    - *1:1 (Um para Um)*: Uma entidade se associa a uma única ocorrência de outra entidade (Ex: Técnico e Time).
    - *1:N (Um para Muitos)*: Uma entidade se associa a várias ocorrências de outra entidade (Ex: Proprietário e Veículo).
    - *N:1 (Muitos para Um)*: Várias ocorrências de uma entidade se associam a uma única ocorrência de outra entidade (Ex: Veículo e Proprietário).
    - *N:M (Muitos para Muitos)*: Várias ocorrências de uma entidade se associam a várias ocorrências de outra entidade (Ex: Paciente e Médico).
3. *Cardinalidade*:
    - Expressa o número de ocorrências de uma entidade que participam do relacionamento com outra entidade.
    - Representada por um losango em diagramas ER (Diagrama de Entidade-Relacionamento).
4. *Totalidade (Obrigatoriedade)*:
    - Especifica se a existência de uma entidade depende de seu relacionamento com outra entidade.
    - Exemplo: Dependente e Sócio em um clube.
5. *Diagrama de Entidade-Relacionamento (DER)*:
    - Ferramenta visual para representar entidades e seus relacionamentos.
    - Utiliza losangos para indicar relacionamentos e linhas para conectar entidades.
6. *Notação e Representação*:
    - A cardinalidade é indicada na notação do DER.
    - Nome do relacionamento deve ser claro e descritivo, facilitando a leitura de cima para baixo ou da esquerda para a direita.
7. *Relacionamento Recursivo*:
    - Uma entidade se relaciona consigo mesma (Ex: Empregado e Supervisor).
8. *Importância das Regras de Negócio*:
    - Consultar as regras de negócio é fundamental para definir corretamente as cardinalidades e totalidades.
    - O DER deve refletir fielmente as regras de negócio para garantir a integridade dos dados.