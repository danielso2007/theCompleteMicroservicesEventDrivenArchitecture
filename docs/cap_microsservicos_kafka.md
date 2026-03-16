- [CAP aplicado em Microsserviços + Kafka](#cap-aplicado-em-microsserviços--kafka)
  - [1. Introdução](#1-introdução)
- [2. Arquitetura típica de microsserviços](#2-arquitetura-típica-de-microsserviços)
- [3. Problema de consistência em microsserviços](#3-problema-de-consistência-em-microsserviços)
- [4. Uso de Kafka na arquitetura](#4-uso-de-kafka-na-arquitetura)
- [5. Fluxo de eventos com Kafka](#5-fluxo-de-eventos-com-kafka)
- [6. CAP nesse cenário](#6-cap-nesse-cenário)
- [7. Consistência eventual](#7-consistência-eventual)
- [8. Benefícios do uso de Kafka](#8-benefícios-do-uso-de-kafka)
- [9. Garantias de entrega](#9-garantias-de-entrega)
- [10. Uso do Saga Pattern](#10-uso-do-saga-pattern)
- [11. Modelo de consistência resultante](#11-modelo-de-consistência-resultante)
- [12. Arquitetura completa exemplo](#12-arquitetura-completa-exemplo)
- [13. Vantagens dessa arquitetura](#13-vantagens-dessa-arquitetura)
- [14. Desafios](#14-desafios)
- [15. Conclusão](#15-conclusão)


# CAP aplicado em Microsserviços + Kafka

## 1. Introdução

Arquiteturas modernas de **microsserviços distribuídos** utilizam
frequentemente **mensageria baseada em eventos**, como Apache Kafka.

Nesse contexto, o **Teorema CAP** influencia diretamente:

-   escolha de banco de dados
-   modelo de consistência
-   comunicação entre serviços
-   estratégia de tolerância a falhas

Kafka permite que sistemas adotem **eventual consistency** e **alta
disponibilidade**, facilitando arquiteturas **AP** ou híbridas.

------------------------------------------------------------------------

# 2. Arquitetura típica de microsserviços

Uma arquitetura simplificada pode ser:

Cliente → API Gateway → Microsserviços

Exemplo:

-   User Service
-   Catalog Service
-   Order Service
-   Payment Service
-   Inventory Service
-   Notification Service

Cada serviço possui:

-   banco de dados próprio
-   responsabilidade isolada
-   comunicação via eventos

Princípio arquitetural:

Database per service

------------------------------------------------------------------------

# 3. Problema de consistência em microsserviços

Quando cada serviço possui banco próprio, **transações ACID distribuídas
são difíceis**.

Exemplo:

Criar pedido envolve:

1.  criar pedido
2.  reservar estoque
3.  processar pagamento
4.  enviar confirmação

Essas operações ocorrem em **serviços diferentes**.

Isso cria desafios de consistência.

------------------------------------------------------------------------

# 4. Uso de Kafka na arquitetura

Kafka atua como **event broker**.

Arquitetura:

Order Service → Kafka Topic → outros serviços

Exemplo:

Order Service publica evento:

order-created

Serviços que consomem:

-   Inventory Service
-   Payment Service
-   Notification Service

------------------------------------------------------------------------

# 5. Fluxo de eventos com Kafka

Fluxo simplificado:

Cliente cria pedido

Order Service: - grava pedido no banco - publica evento order-created

Kafka Topic:

order-created

Consumidores:

Inventory Service → reserva estoque\
Payment Service → processa pagamento\
Notification Service → envia email

------------------------------------------------------------------------

# 6. CAP nesse cenário

Em arquiteturas baseadas em eventos, normalmente priorizamos:

Availability + Partition Tolerance

Ou seja:

AP

Motivo:

Kafka permite que sistemas continuem funcionando mesmo com falhas
temporárias.

Eventos são armazenados e processados posteriormente.

------------------------------------------------------------------------

# 7. Consistência eventual

Como os serviços processam eventos de forma assíncrona, ocorre:

Eventual Consistency

Exemplo:

Pedido criado

Order Service grava pedido imediatamente.

Inventory Service recebe evento alguns milissegundos depois.

Nesse intervalo o sistema pode estar **temporariamente inconsistente**.

------------------------------------------------------------------------

# 8. Benefícios do uso de Kafka

Desacoplamento:

Serviços não precisam chamar diretamente uns aos outros.

Escalabilidade:

Consumidores podem escalar horizontalmente.

Tolerância a falhas:

Eventos ficam persistidos no Kafka.

Reprocessamento:

Eventos podem ser consumidos novamente.

------------------------------------------------------------------------

# 9. Garantias de entrega

Kafka fornece:

At least once delivery

Ou seja:

Eventos podem ser processados mais de uma vez.

Portanto serviços precisam ser:

Idempotentes

Exemplo:

Se evento "payment-processed" for recebido duas vezes, o sistema não
pode duplicar pagamento.

------------------------------------------------------------------------

# 10. Uso do Saga Pattern

Para coordenar transações distribuídas usa-se o **Saga Pattern**.

Fluxo exemplo:

Order Created → Reserve Inventory → Process Payment → Confirm Order

Se pagamento falhar:

Compensação:

Cancel Order\
Release Inventory

------------------------------------------------------------------------

# 11. Modelo de consistência resultante

Arquiteturas com Kafka geralmente seguem:

AP + Eventual Consistency

Dados convergem com o tempo.

------------------------------------------------------------------------

# 12. Arquitetura completa exemplo

Cliente ↓ API Gateway

Order Service (CP local) ↓ Kafka Topic: order-created

Inventory Service (CP local) ↓ Kafka Topic: inventory-reserved

Payment Service (CP local) ↓ Kafka Topic: payment-processed

Notification Service (AP)

------------------------------------------------------------------------

# 13. Vantagens dessa arquitetura

Alta disponibilidade

Escalabilidade horizontal

Desacoplamento entre serviços

Resiliência a falhas

------------------------------------------------------------------------

# 14. Desafios

Consistência eventual

Complexidade operacional

Necessidade de idempotência

Monitoramento de eventos

------------------------------------------------------------------------

# 15. Conclusão

Kafka permite construir sistemas distribuídos que equilibram:

Disponibilidade Escalabilidade Resiliência

Com custo de:

Consistência eventual

Arquitetos geralmente adotam:

AP para comunicação CP dentro de cada serviço

Essa combinação cria arquiteturas robustas e escaláveis.
