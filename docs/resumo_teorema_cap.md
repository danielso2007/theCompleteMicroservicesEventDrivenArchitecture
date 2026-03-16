# Teorema CAP --- Resumo Técnico Detalhado

## 1. Introdução

O **Teorema CAP** é um princípio fundamental da arquitetura de sistemas
distribuídos. Ele define um limite teórico que descreve as propriedades
que um sistema distribuído pode garantir simultaneamente.

O teorema afirma que **um sistema distribuído não pode garantir ao mesmo
tempo três propriedades fundamentais**:

-   **Consistency (Consistência)**
-   **Availability (Disponibilidade)**
-   **Partition Tolerance (Tolerância a Partições)**

Portanto, um sistema distribuído real **precisa escolher apenas duas
dessas três propriedades**.

------------------------------------------------------------------------

# 2. Sistemas Distribuídos

Um **sistema distribuído** é um conjunto de computadores (nós) que
trabalham juntos para apresentar ao usuário um sistema único e
consistente.

Características:

-   múltiplos servidores ou nós
-   comunicação via rede
-   replicação de dados
-   tolerância a falhas

Exemplos:

-   sistemas em nuvem
-   bancos de dados distribuídos
-   arquiteturas de microsserviços
-   sistemas de big data

------------------------------------------------------------------------

# 3. As Três Propriedades do Teorema CAP

## 3.1 Consistência (Consistency)

Consistência significa que **todos os nós do sistema possuem exatamente
o mesmo dado ao mesmo tempo**.

Se um dado é escrito:

-   todas as leituras retornam o **último valor escrito**
-   ou retornam erro

Características:

-   replicação sincronizada
-   forte controle de transações
-   integridade de dados garantida

Exemplo:

Bancos relacionais tradicionais.

------------------------------------------------------------------------

## 3.2 Disponibilidade (Availability)

Disponibilidade significa que **todo pedido recebe resposta**, mesmo que
alguns nós estejam falhando.

Garantias:

-   o sistema responde sempre
-   não há falha total de serviço
-   os nós ativos continuam respondendo

Importante:

A resposta pode conter **dados desatualizados**.

------------------------------------------------------------------------

## 3.3 Tolerância a Partições (Partition Tolerance)

Uma **partição de rede** ocorre quando dois ou mais nós deixam de
conseguir se comunicar.

Exemplos de causas:

-   falha de rede
-   latência extrema
-   datacenters isolados
-   timeout de comunicação

Um sistema tolerante a partições continua funcionando **mesmo quando
parte do cluster está isolado**.

------------------------------------------------------------------------

# 4. O Trade-off do CAP

Quando ocorre uma **partição de rede**, o sistema deve escolher entre:

-   Consistência
-   Disponibilidade

Não é possível garantir ambos.

Portanto surgem dois modelos principais:

-   **CP**
-   **AP**

------------------------------------------------------------------------

# 5. Modelos de Consistência

## 5.1 Consistência Forte

Características:

-   leitura sempre retorna o último valor
-   nenhuma inconsistência é permitida
-   exige sincronização entre nós

Normalmente implementado com:

-   transações ACID
-   replicação síncrona
-   locks distribuídos

Exemplo:

-   PostgreSQL
-   Oracle
-   SQL Server

------------------------------------------------------------------------

## 5.2 Consistência Eventual

Nesse modelo:

-   dados podem ficar temporariamente inconsistentes
-   com o tempo as réplicas convergem

Propriedades:

-   alta disponibilidade
-   replicação assíncrona
-   maior desempenho

Usado em:

-   bancos NoSQL
-   sistemas altamente distribuídos

------------------------------------------------------------------------

# 6. Classificação CAP de Bancos de Dados

## 6.1 CP --- Consistência + Tolerância a Partições

Prioridade:

-   Consistência
-   Tolerância a partições

Sacrifício:

-   Disponibilidade

Quando ocorre partição:

-   algumas operações são bloqueadas

Exemplos:

-   MongoDB
-   HBase
-   Oracle RAC

------------------------------------------------------------------------

## 6.2 AP --- Disponibilidade + Tolerância a Partições

Prioridade:

-   Disponibilidade
-   Tolerância a partições

Sacrifício:

-   Consistência imediata

Características:

-   sistema responde sempre
-   dados podem ficar temporariamente inconsistentes

Exemplos:

-   Cassandra
-   DynamoDB
-   Riak

------------------------------------------------------------------------

## 6.3 CA --- Consistência + Disponibilidade

Esse modelo:

-   não tolera partições de rede

Portanto **não é viável em sistemas distribuídos reais**.

Pode existir apenas em:

-   sistemas centralizados
-   sistemas sem falhas de rede

------------------------------------------------------------------------

# 7. NoSQL e CAP

Bancos NoSQL foram projetados para **escalar horizontalmente**.

Características:

-   dados distribuídos em múltiplos nós
-   replicação automática
-   alto throughput

Esses bancos normalmente escolhem entre:

-   CP
-   AP

------------------------------------------------------------------------

# 8. MongoDB e CAP

MongoDB é classificado como **CP**.

Arquitetura:

Replica Set:

-   Primary
-   Secondary
-   Secondary

Funcionamento:

1.  Escritas vão para o **primary**
2.  Secondary replicam via log de operações
3.  Em caso de falha ocorre eleição de novo primary

Durante a eleição:

-   escritas ficam indisponíveis

Resultado:

-   consistência garantida

------------------------------------------------------------------------

# 9. Cassandra e CAP

Cassandra é classificado como **AP**.

Arquitetura:

Cluster **sem mestre (masterless)**.

Características:

-   qualquer nó pode receber escrita
-   replicação assíncrona
-   consistência eventual

Mecanismos internos:

-   Gossip protocol
-   Anti-entropy repair
-   Hinted handoff

Benefícios:

-   alta disponibilidade
-   baixa latência
-   alta escalabilidade

------------------------------------------------------------------------

# 10. CAP em Microsserviços

Microsserviços são naturalmente sistemas distribuídos.

Cada serviço pode escolher um banco diferente.

Exemplo:

  Serviço        Banco        Modelo
  -------------- ------------ --------
  Pagamento      PostgreSQL   CP
  Catálogo       Cassandra    AP
  Pedidos        MongoDB      CP
  Notificações   DynamoDB     AP

Isso permite otimizar cada domínio.

------------------------------------------------------------------------

# 11. Exemplo de Sistema CP --- Sistema de Votação

Requisitos:

-   consistência absoluta
-   votos registrados exatamente uma vez

Arquitetura sugerida:

Oracle RAC

Componentes:

-   cluster de bancos
-   replicação síncrona
-   quorum
-   protocolo de consenso (2PC)

Fluxo:

1.  usuário envia voto
2.  nó recebe transação
3.  replicação síncrona
4.  commit global

Resultado:

-   todos os nós possuem os mesmos dados

Desvantagens:

-   maior latência
-   maior complexidade

------------------------------------------------------------------------

# 12. Exemplo de Sistema AP --- Sistema de Chat

Requisitos:

-   alta disponibilidade
-   baixa latência

Arquitetura:

Apache Cassandra

Funcionamento:

1.  mensagem escrita em um nó
2.  replicação assíncrona
3.  usuário lê do nó mais próximo

Possível efeito:

-   mensagens podem aparecer fora de ordem temporariamente

Benefícios:

-   resposta rápida
-   escalabilidade massiva

------------------------------------------------------------------------

# 13. Conceito de Workload

Workload é o **conjunto de tarefas que um sistema executa**.

Inclui:

-   requisições de usuários
-   jobs agendados
-   processamento em background

Características principais:

### Volume

Número de operações por segundo.

### Complexidade

Quantidade de recursos necessários.

### Variabilidade

Picos ou variação de carga.

### Dependências

Interdependência entre tarefas.

------------------------------------------------------------------------

# 14. Conclusão

O Teorema CAP é essencial para arquitetos de sistemas distribuídos
porque:

-   define limites fundamentais da arquitetura
-   ajuda a escolher bancos de dados adequados
-   explica trade-offs entre consistência e disponibilidade

Em sistemas distribuídos modernos:

-   **P é obrigatório**
-   portanto escolhemos entre **CP ou AP**.

A escolha depende de:

-   requisitos de consistência
-   tolerância a inconsistências
-   latência aceitável
-   escala do sistema
