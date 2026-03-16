- [CAP vs PACELC --- Explicação Didática](#cap-vs-pacelc-----explicação-didática)
  - [1. Problema dos Sistemas Distribuídos](#1-problema-dos-sistemas-distribuídos)
- [2. Teorema CAP](#2-teorema-cap)
- [3. Definições do CAP](#3-definições-do-cap)
  - [Consistency](#consistency)
  - [Availability](#availability)
  - [Partition Tolerance](#partition-tolerance)
- [4. Trade‑off do CAP](#4-tradeoff-do-cap)
    - [CP](#cp)
    - [AP](#ap)
- [5. Limitação do CAP](#5-limitação-do-cap)
- [6. Teorema PACELC](#6-teorema-pacelc)
- [7. Interpretação](#7-interpretação)
  - [Durante partição](#durante-partição)
  - [Sem partição](#sem-partição)
- [8. Exemplo](#8-exemplo)
  - [Consistência forte](#consistência-forte)
  - [Latência baixa](#latência-baixa)
- [9. Classificação PACELC](#9-classificação-pacelc)
- [10. Exemplos](#10-exemplos)
  - [Cassandra](#cassandra)
  - [DynamoDB](#dynamodb)
  - [MongoDB](#mongodb)
  - [Google Spanner](#google-spanner)
- [11. Visualização](#11-visualização)
- [12. Conclusão](#12-conclusão)


# CAP vs PACELC --- Explicação Didática

## 1. Problema dos Sistemas Distribuídos

Sistemas distribuídos armazenam dados em **múltiplos nós conectados por
rede**.

Exemplo:

Client → Load Balancer → Node A / Node B / Node C

Como os nós se comunicam por rede, podem ocorrer:

-   perda de pacotes
-   latência alta
-   timeout
-   falha de link
-   isolamento de datacenter

Essas falhas criam o cenário que levou ao **Teorema CAP**.

------------------------------------------------------------------------

# 2. Teorema CAP

CAP afirma que um sistema distribuído **não pode garantir
simultaneamente**:

-   Consistency (C)
-   Availability (A)
-   Partition Tolerance (P)

Quando ocorre uma **partição de rede**, o sistema precisa escolher:

Consistency **ou** Availability.

Na prática, sistemas distribuídos são:

-   CP
-   AP

------------------------------------------------------------------------

# 3. Definições do CAP

## Consistency

Todos os nós retornam **o mesmo dado ao mesmo tempo**.

Exemplo:

Node A → saldo 100\
Node B → saldo 100\
Node C → saldo 100

Após atualização:

saldo = 150 em todos os nós.

------------------------------------------------------------------------

## Availability

Todo request recebe resposta.

Mesmo que alguns nós estejam indisponíveis.

O dado retornado pode estar **desatualizado**.

------------------------------------------------------------------------

## Partition Tolerance

Sistema continua funcionando mesmo com falhas de comunicação entre nós.

Exemplo:

Node A ---X--- Node B\
Node C isolado

O cluster foi dividido.

------------------------------------------------------------------------

# 4. Trade‑off do CAP

Durante uma partição:

-   CP → Consistency + Partition Tolerance
-   AP → Availability + Partition Tolerance

### CP

Prioriza consistência.

Exemplos:

-   MongoDB
-   HBase
-   bancos relacionais clusterizados

Durante partição o sistema pode **bloquear operações**.

### AP

Prioriza disponibilidade.

Exemplos:

-   Cassandra
-   DynamoDB
-   Riak

Sistema continua respondendo mesmo com inconsistência temporária.

------------------------------------------------------------------------

# 5. Limitação do CAP

CAP explica apenas **o comportamento quando ocorre uma partição**.

Mas a maior parte do tempo os sistemas **operam sem partições**.

Então surge uma nova pergunta:

Mesmo sem partição, o sistema prioriza **latência ou consistência?**

Essa pergunta é respondida pelo **PACELC**.

------------------------------------------------------------------------

# 6. Teorema PACELC

Proposto por Daniel Abadi (2010).

PACELC significa:

If Partition (P)\
→ choose Availability or Consistency

Else (E)\
→ choose Latency or Consistency

Ou seja:

P → A ou C\
E → L ou C

------------------------------------------------------------------------

# 7. Interpretação

PACELC descreve **duas decisões arquiteturais**.

## Durante partição

Escolha entre:

-   Availability
-   Consistency

Igual ao CAP.

## Sem partição

Escolha entre:

-   Latency
-   Consistency

Garantir consistência geralmente exige:

-   replicação síncrona
-   comunicação entre nós
-   confirmação global

Isso aumenta a latência.

------------------------------------------------------------------------

# 8. Exemplo

## Consistência forte

Client → Node A\
Node A → Node B\
Node A → Node C\
espera confirmação\
responde ao cliente

Latência maior.

------------------------------------------------------------------------

## Latência baixa

Client → Node A\
Node A responde imediatamente\
replicação ocorre depois

Latência menor, consistência eventual.

------------------------------------------------------------------------

# 9. Classificação PACELC

Formato:

P(x) / E(y)

x = A ou C\
y = L ou C

------------------------------------------------------------------------

# 10. Exemplos

## Cassandra

PA / EL

Durante partição: Availability

Sem partição: Latency

------------------------------------------------------------------------

## DynamoDB

PA / EL

Alta disponibilidade e baixa latência.

------------------------------------------------------------------------

## MongoDB

PC / EC

Durante partição: Consistency

Sem partição: Consistency

Maior latência.

------------------------------------------------------------------------

## Google Spanner

PC / EC

Consistência global utilizando TrueTime.

------------------------------------------------------------------------

# 11. Visualização

PACELC

Partition? YES → Availability ou Consistency

NO → Latency ou Consistency

------------------------------------------------------------------------

# 12. Conclusão

CAP explica:

comportamento durante falhas de rede.

PACELC explica:

trade‑offs de arquitetura no funcionamento normal do sistema.

Arquitetos modernos usam:

CAP + PACELC

para decidir:

-   banco de dados
-   estratégia de replicação
-   latência aceitável
-   consistência necessária
