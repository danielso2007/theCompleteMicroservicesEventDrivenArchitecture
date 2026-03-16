- [Arquitetura Real de E‑commerce Aplicando o Teorema CAP](#arquitetura-real-de-ecommerce-aplicando-o-teorema-cap)
  - [1. Visão Geral](#1-visão-geral)
- [2. Princípio Fundamental](#2-princípio-fundamental)
- [3. Classificação CAP por Serviço](#3-classificação-cap-por-serviço)
- [4. Serviço de Catálogo](#4-serviço-de-catálogo)
- [5. Serviço de Carrinho](#5-serviço-de-carrinho)
- [6. Serviço de Pedidos](#6-serviço-de-pedidos)
- [7. Serviço de Pagamento](#7-serviço-de-pagamento)
- [8. Serviço de Estoque](#8-serviço-de-estoque)
- [9. Serviço de Notificação](#9-serviço-de-notificação)
- [10. Fluxo de Compra](#10-fluxo-de-compra)
- [11. Comunicação entre Serviços](#11-comunicação-entre-serviços)
- [12. Consistência entre Serviços](#12-consistência-entre-serviços)
- [13. Exemplo de Saga](#13-exemplo-de-saga)
- [14. Arquitetura Completa](#14-arquitetura-completa)
- [15. Benefícios](#15-benefícios)
- [16. Conclusão](#16-conclusão)


# Arquitetura Real de E‑commerce Aplicando o Teorema CAP

## 1. Visão Geral

Um e‑commerce moderno normalmente utiliza **arquitetura de
microsserviços**.\
Cada serviço possui:

-   responsabilidade específica
-   banco de dados próprio
-   estratégia de consistência própria

Arquitetura simplificada:

Cliente → API Gateway → Microsserviços

Microsserviços típicos:

-   Auth Service
-   Catalog Service
-   Cart Service
-   Order Service
-   Payment Service
-   Inventory Service
-   Notification Service

Cada um desses serviços pode adotar **diferentes estratégias CAP**.

------------------------------------------------------------------------

# 2. Princípio Fundamental

Nem todos os domínios precisam do mesmo nível de consistência.

Regra comum:

Dados críticos → CP\
Dados de leitura ou experiência → AP

------------------------------------------------------------------------

# 3. Classificação CAP por Serviço

  Serviço        Responsabilidade      Modelo CAP
  -------------- --------------------- ------------
  Catalog        exibir produtos       AP
  Cart           carrinho do usuário   AP
  Order          pedidos               CP
  Payment        pagamentos            CP
  Inventory      estoque               CP
  Notification   emails e mensagens    AP

------------------------------------------------------------------------

# 4. Serviço de Catálogo

Responsável por:

-   lista de produtos
-   imagens
-   descrição
-   busca

Banco comum:

-   Cassandra
-   DynamoDB
-   Elasticsearch

Modelo CAP:

AP

Motivo:

O catálogo precisa **sempre estar disponível**.

Se houver inconsistência temporária (ex: preço atualizado com atraso), o
impacto é pequeno.

------------------------------------------------------------------------

# 5. Serviço de Carrinho

Responsável por:

-   itens escolhidos pelo usuário
-   sessão de compra

Bancos comuns:

-   Redis
-   DynamoDB
-   Cassandra

Modelo:

AP

Motivo:

Carrinho é um **estado temporário**.

Mesmo que ocorra inconsistência momentânea, ela pode ser corrigida
posteriormente.

Disponibilidade é mais importante.

------------------------------------------------------------------------

# 6. Serviço de Pedidos

Responsável por:

-   criação do pedido
-   status do pedido
-   histórico

Banco comum:

-   PostgreSQL
-   MySQL
-   MongoDB

Modelo:

CP

Motivo:

Pedidos não podem:

-   duplicar
-   desaparecer
-   mudar estado incorretamente

Por isso consistência é essencial.

------------------------------------------------------------------------

# 7. Serviço de Pagamento

Responsável por:

-   autorização de pagamento
-   transações financeiras

Banco comum:

-   PostgreSQL
-   bancos ACID

Modelo:

CP

Motivo:

Pagamentos exigem:

-   consistência
-   atomicidade
-   integridade financeira

------------------------------------------------------------------------

# 8. Serviço de Estoque

Responsável por:

-   quantidade de produtos
-   reserva de estoque

Banco comum:

-   PostgreSQL
-   MongoDB

Modelo:

CP

Motivo:

Evitar overselling.

Exemplo de problema:

estoque = 1

Cliente A compra\
Cliente B compra

Sem consistência isso poderia ocorrer.

------------------------------------------------------------------------

# 9. Serviço de Notificação

Responsável por:

-   envio de emails
-   SMS
-   push notifications

Banco comum:

-   Cassandra
-   DynamoDB

Modelo:

AP

Motivo:

Notificações podem atrasar alguns segundos sem causar problemas.

------------------------------------------------------------------------

# 10. Fluxo de Compra

Fluxo simplificado:

1.  Cliente adiciona produto ao carrinho
2.  Cart Service registra item
3.  Cliente realiza checkout
4.  Order Service cria pedido
5.  Inventory Service reserva estoque
6.  Payment Service processa pagamento
7.  Notification Service envia confirmação

------------------------------------------------------------------------

# 11. Comunicação entre Serviços

Arquiteturas modernas utilizam **event‑driven architecture**.

Exemplo:

Order Service publica evento:

order-created

Serviços que consomem:

-   Inventory Service
-   Payment Service
-   Notification Service

Tecnologias comuns:

-   Kafka
-   RabbitMQ
-   AWS SNS/SQS

------------------------------------------------------------------------

# 12. Consistência entre Serviços

Como cada serviço possui banco próprio, utiliza-se:

Eventual Consistency.

Padrões usados:

-   Saga Pattern
-   Event Sourcing
-   CQRS

------------------------------------------------------------------------

# 13. Exemplo de Saga

1.  Order created
2.  Reserve inventory
3.  Process payment
4.  Confirm order

Se pagamento falhar:

-   cancelar pedido
-   liberar estoque

------------------------------------------------------------------------

# 14. Arquitetura Completa

Cliente ↓ API Gateway ↓ Auth Service

Catalog Service (AP) → Cassandra

Cart Service (AP) → Redis

Order Service (CP) → PostgreSQL

Inventory Service (CP) → PostgreSQL

Payment Service (CP) → PostgreSQL

Notification Service (AP) → Cassandra

------------------------------------------------------------------------

# 15. Benefícios

Escalabilidade: Serviços AP escalam facilmente.

Segurança: Serviços CP garantem integridade.

Disponibilidade: Partes não críticas continuam funcionando.

------------------------------------------------------------------------

# 16. Conclusão

Arquiteturas modernas de e‑commerce aplicam CAP **por domínio de
negócio**.

Estratégia prática:

dados financeiros → CP\
dados de leitura → AP

Isso permite equilibrar:

-   consistência
-   disponibilidade
-   escalabilidade
