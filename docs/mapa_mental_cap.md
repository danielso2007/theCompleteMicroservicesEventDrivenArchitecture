# Mapa Mental Completo --- Teorema CAP

## CAP Theorem

Sistema distribuído **não pode garantir simultaneamente**: -
Consistency - Availability - Partition Tolerance

Sempre que ocorrer **partição de rede**, deve-se escolher entre
**Consistência ou Disponibilidade**.

------------------------------------------------------------------------

# 1. Consistency (C)

Todos os nós veem **o mesmo dado ao mesmo tempo**.

## Características

-   leitura retorna último valor escrito
-   replicação sincronizada
-   dados idênticos em todos os nós
-   forte controle transacional

## Tecnologias associadas

-   ACID
-   Two‑Phase Commit
-   Protocolos de consenso

## Bancos comuns

-   PostgreSQL
-   Oracle
-   SQL Server
-   HBase
-   MongoDB

## Vantagens

-   integridade de dados
-   previsibilidade
-   forte consistência

## Desvantagens

-   maior latência
-   menor disponibilidade durante falhas

------------------------------------------------------------------------

# 2. Availability (A)

Todo request recebe resposta.

## Características

-   sistema sempre responde
-   qualquer nó pode atender requisições
-   tolerância a falhas de servidores

## Observação

Resposta pode conter **dados desatualizados**.

## Vantagens

-   alta disponibilidade
-   melhor experiência do usuário
-   baixa latência

## Desvantagens

-   inconsistência temporária

------------------------------------------------------------------------

# 3. Partition Tolerance (P)

Sistema continua funcionando mesmo com falhas de comunicação entre nós.

## Causas de partição

-   falha de rede
-   perda de pacotes
-   latência extrema
-   isolamento de datacenter
-   timeout de comunicação

## Consequências

-   cluster dividido
-   inconsistência potencial
-   necessidade de escolher entre C ou A

## Observação importante

Em sistemas distribuídos reais **P é inevitável**.

------------------------------------------------------------------------

# 4. Trade-off CAP

Quando ocorre uma partição:

Escolha obrigatória:

-   CP → Consistência + Partition Tolerance
-   AP → Disponibilidade + Partition Tolerance

CA não é viável em sistemas distribuídos reais.

------------------------------------------------------------------------

# 5. Modelos CAP

## CP (Consistency + Partition Tolerance)

Prioriza: - consistência - integridade de dados

Sacrifica: - disponibilidade

### Comportamento

-   operações podem ser bloqueadas
-   alguns nós ficam indisponíveis

### Exemplos

-   MongoDB
-   HBase
-   Oracle RAC
-   bancos relacionais clusterizados

------------------------------------------------------------------------

## AP (Availability + Partition Tolerance)

Prioriza: - disponibilidade - baixa latência

Sacrifica: - consistência imediata

### Comportamento

-   sistema sempre responde
-   dados podem divergir temporariamente

### Exemplos

-   Cassandra
-   DynamoDB
-   Riak

------------------------------------------------------------------------

## CA (Consistency + Availability)

Teoricamente possível apenas se **não existir partição de rede**.

Na prática: - não aplicável a sistemas distribuídos reais.

------------------------------------------------------------------------

# 6. Modelos de Consistência

## Strong Consistency

Garantia: - leitura sempre retorna o valor mais recente.

### Implementações

-   transações ACID
-   replicação síncrona
-   locks distribuídos

### Uso típico

-   sistemas financeiros
-   sistemas bancários
-   sistemas de votação

------------------------------------------------------------------------

## Eventual Consistency

Garantia: - dados convergem ao longo do tempo.

### Características

-   replicação assíncrona
-   alta disponibilidade
-   maior escalabilidade

### Uso típico

-   redes sociais
-   chat
-   sistemas distribuídos massivos

------------------------------------------------------------------------

# 7. Bancos NoSQL e CAP

NoSQL foi projetado para:

-   escalabilidade horizontal
-   replicação distribuída
-   alto throughput

Classificação comum:

-   CP
-   AP

------------------------------------------------------------------------

# 8. MongoDB no CAP

Classificação: **CP**

## Arquitetura

Replica Set

-   Primary
-   Secondary
-   Secondary

## Funcionamento

1.  escrita vai para primary
2.  secondaries replicam dados
3.  eleição ocorre se primary falhar

## Consequência

Durante eleição: - escritas ficam indisponíveis

Benefício: - consistência garantida

------------------------------------------------------------------------

# 9. Cassandra no CAP

Classificação: **AP**

## Arquitetura

Cluster sem mestre.

Todos os nós são iguais.

## Funcionamento

1.  cliente escreve em qualquer nó
2.  dados replicados assincronamente
3.  leitura ocorre no nó mais próximo

## Mecanismos internos

-   Gossip protocol
-   Anti‑entropy repair
-   Hinted handoff

## Benefícios

-   altíssima disponibilidade
-   baixa latência
-   escalabilidade massiva

------------------------------------------------------------------------

# 10. CAP em Microsserviços

Microsserviços são sistemas distribuídos.

Cada serviço pode escolher banco diferente.

## Exemplo

Pagamento - PostgreSQL - modelo CP

Catálogo - Cassandra - modelo AP

Pedidos - MongoDB - modelo CP

Notificações - DynamoDB - modelo AP

------------------------------------------------------------------------

# 11. Exemplos de Aplicação

## Sistema de votação (CP)

Requisitos: - integridade absoluta - consistência forte

Arquitetura: - Oracle RAC - replicação síncrona - protocolo 2PC

Resultado: - dados idênticos em todos os nós

------------------------------------------------------------------------

## Sistema de chat (AP)

Requisitos: - baixa latência - disponibilidade constante

Arquitetura: - Cassandra

Fluxo: 1. mensagem escrita 2. replicação assíncrona 3. usuários leem do
nó mais próximo

Possível efeito: - mensagens fora de ordem temporariamente

------------------------------------------------------------------------

# 12. Workload em Sistemas Distribuídos

Workload = carga de trabalho do sistema.

## Tipos

-   requisições de usuários
-   jobs agendados
-   processamento em background

## Características

### Volume

Quantidade de operações.

### Complexidade

Recursos necessários.

### Variabilidade

Mudança de carga ao longo do tempo.

### Dependências

Relacionamento entre tarefas.

------------------------------------------------------------------------

# Estrutura Mental Simplificada

CAP ├ Consistency │ ├ strong consistency │ ├ ACID │ └ bancos relacionais
│ ├ Availability │ ├ resposta sempre │ ├ baixa latência │ └ dados podem
divergir │ └ Partition Tolerance ├ falhas de rede ├ isolamento de nós └
necessidade de trade‑off

Trade‑off ├ CP │ ├ MongoDB │ └ bancos relacionais cluster │ └ AP ├
Cassandra └ DynamoDB
