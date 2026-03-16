
- [Resumo Estruturado — The Complete Microservices \& Event‑Driven Architecture](#resumo-estruturado--the-complete-microservices--eventdriven-architecture)
  - [The Complete Microservices \& Event‑Driven Architecture](#the-complete-microservices--eventdriven-architecture)
- [A arquitetura típica web](#a-arquitetura-típica-web)
- [Arquitetura de Microsserviços — Benefícios e Desafios](#arquitetura-de-microsserviços--benefícios-e-desafios)
- [O que é arquitetura de microsserviços?](#o-que-é-arquitetura-de-microsserviços)
- [Limites dos microsserviços — Princípios básicos](#limites-dos-microsserviços--princípios-básicos)
    - [Coesão](#coesão)
    - [Responsabilidade única](#responsabilidade-única)
    - [Baixo acoplamento](#baixo-acoplamento)
- [Decomposição de uma aplicação monolítica em microsserviços](#decomposição-de-uma-aplicação-monolítica-em-microsserviços)
    - [1. Por capacidades de negócio](#1-por-capacidades-de-negócio)
    - [2. Por subdomínio (DDD)](#2-por-subdomínio-ddd)
- [Migração para Microsserviços — Passos, Dicas e Padrões](#migração-para-microsserviços--passos-dicas-e-padrões)
- [Bancos de dados em arquitetura de microsserviços](#bancos-de-dados-em-arquitetura-de-microsserviços)
- [O Princípio do Banco de Dados por Microsserviço](#o-princípio-do-banco-de-dados-por-microsserviço)
- [Exemplo: Transição de Monolítico para Microsserviços](#exemplo-transição-de-monolítico-para-microsserviços)
- [Problemas de Acoplamento](#problemas-de-acoplamento)
- [Benefícios do Banco de Dados por Microsserviço](#benefícios-do-banco-de-dados-por-microsserviço)
- [Desafios do Princípio](#desafios-do-princípio)
- [Soluções Alternativas](#soluções-alternativas)
- [Conclusão](#conclusão)
- [O Princípio DRY em Microsserviços e Bibliotecas Compartilhadas](#o-princípio-dry-em-microsserviços-e-bibliotecas-compartilhadas)
- [O que é o Princípio DRY?](#o-que-é-o-princípio-dry)
- [Desafios das Bibliotecas Compartilhadas em Microsserviços](#desafios-das-bibliotecas-compartilhadas-em-microsserviços)
- [Alternativas às Bibliotecas Compartilhadas](#alternativas-às-bibliotecas-compartilhadas)
- [Ajuste de Limites de Microsserviços](#ajuste-de-limites-de-microsserviços)
- [Microsserviço Específico para Lógica Compartilhada](#microsserviço-específico-para-lógica-compartilhada)
- [Modelos de Dados Compartilhados](#modelos-de-dados-compartilhados)
- [Duplicar Códigos Simples](#duplicar-códigos-simples)
- [Uso do Sidecar Pattern](#uso-do-sidecar-pattern)
- [Bibliotecas Altamente Estáveis](#bibliotecas-altamente-estáveis)
- [Duplicação de Dados em Microsserviços](#duplicação-de-dados-em-microsserviços)
- [Autonomia Estruturada para Equipes de Desenvolvimento](#autonomia-estruturada-para-equipes-de-desenvolvimento)
    - [Padronização total](#padronização-total)
    - [Liberdade controlada](#liberdade-controlada)
    - [Total autonomia](#total-autonomia)
- [Fatores que Influenciam os Limites](#fatores-que-influenciam-os-limites)
- [Padrão de Arquitetura de Micro‑frontends](#padrão-de-arquitetura-de-microfrontends)
- [Problemas de um Front‑End Monolítico](#problemas-de-um-frontend-monolítico)
- [Introdução ao Padrão Micro‑Frontends](#introdução-ao-padrão-microfrontends)
- [Benefícios dos Micro‑Frontends](#benefícios-dos-microfrontends)
- [Gerenciamento de API para Arquitetura de Microsserviços](#gerenciamento-de-api-para-arquitetura-de-microsserviços)
- [O Problema do Gerenciamento de APIs](#o-problema-do-gerenciamento-de-apis)
- [A Solução: Gateway de API](#a-solução-gateway-de-api)
- [Gateway de API vs Balanceador de Carga](#gateway-de-api-vs-balanceador-de-carga)
- [Introdução à Arquitetura Orientada a Eventos](#introdução-à-arquitetura-orientada-a-eventos)
- [Motivação](#motivação)
- [Modelo Request‑Response](#modelo-requestresponse)
- [Arquitetura Orientada a Eventos](#arquitetura-orientada-a-eventos)
- [Benefícios](#benefícios)
- [Casos de uso de arquitetura orientada a eventos](#casos-de-uso-de-arquitetura-orientada-a-eventos)
- [Semântica de entrega de mensagens](#semântica-de-entrega-de-mensagens)
    - [At most once](#at-most-once)
    - [At least once](#at-least-once)
    - [Exactly once](#exactly-once)
- [Saga Pattern](#saga-pattern)
    - [Orquestração](#orquestração)
    - [Coreografia](#coreografia)
- [CQRS Pattern](#cqrs-pattern)
- [Event Sourcing Pattern](#event-sourcing-pattern)
- [Testing Microservices and Event‑Driven Architecture](#testing-microservices-and-eventdriven-architecture)
- [Pirâmide de testes](#pirâmide-de-testes)
- [Contract Tests](#contract-tests)
- [Observabilidade na Arquitetura de Microsserviços](#observabilidade-na-arquitetura-de-microsserviços)
- [Registro Distribuído (Distributed Logging)](#registro-distribuído-distributed-logging)
- [Metrics](#metrics)
- [Implantação em produção](#implantação-em-produção)
- [Máquinas virtuais](#máquinas-virtuais)
- [Serverless (FaaS)](#serverless-faas)
- [Contêineres](#contêineres)
- [Kubernetes](#kubernetes)


# Resumo Estruturado — The Complete Microservices & Event‑Driven Architecture

---

## The Complete Microservices & Event‑Driven Architecture
Apresenta os fundamentos de arquiteturas modernas baseadas em **microsserviços** e **arquitetura orientada a eventos**. O objetivo é permitir sistemas escaláveis, resilientes e evolutivos, dividindo aplicações grandes em serviços independentes que se comunicam por APIs ou eventos.

---

# A arquitetura típica web
Arquitetura clássica composta por **3 camadas**:

1. **Presentation Layer**
   - UI web ou mobile

2. **Application / Business Layer**
   - lógica de negócio
   - APIs

3. **Data Layer**
   - banco de dados
   - armazenamento persistente

Essa arquitetura normalmente resulta em um **monólito**.

Vantagens:
- simples de desenvolver
- fácil de implantar
- adequada para equipes pequenas

Problemas ao crescer:
- base de código grande
- deploy arriscado
- baixa escalabilidade organizacional

---

# Arquitetura de Microsserviços — Benefícios e Desafios

Microsserviços dividem o sistema em serviços independentes.

Benefícios:
- escalabilidade organizacional
- deploy independente
- resiliência
- liberdade tecnológica

Desafios:
- latência de rede
- complexidade operacional
- observabilidade difícil
- testes distribuídos

---

# O que é arquitetura de microsserviços?
É um estilo arquitetural onde:

- cada serviço possui **responsabilidade específica**
- serviços são **implantados independentemente**
- cada serviço possui **seu próprio banco de dados**
- comunicação ocorre via **APIs ou eventos**

Objetivo:
- reduzir acoplamento
- permitir evolução independente.

---

# Limites dos microsserviços — Princípios básicos

Três princípios principais:

### Coesão
Componentes que mudam juntos devem ficar no mesmo serviço.

### Responsabilidade única
Cada microsserviço deve possuir apenas um motivo para mudança.

### Baixo acoplamento
Serviços devem depender o mínimo possível uns dos outros.

---

# Decomposição de uma aplicação monolítica em microsserviços

Duas abordagens principais.

### 1. Por capacidades de negócio
Serviços representam funcionalidades do negócio.

Exemplo e‑commerce:
- product service
- order service
- payment service

### 2. Por subdomínio (DDD)

Tipos de domínio:

**Core domain**
- diferencial da empresa

**Supporting domain**
- suporte ao negócio

**Generic domain**
- funcionalidades comuns

---

# Migração para Microsserviços — Passos, Dicas e Padrões

Evitar migração **Big Bang**.

Abordagem recomendada:
migração **incremental**.

Passos:

1. adicionar testes
2. definir APIs
3. isolar componentes
4. extrair serviço

---

# Bancos de dados em arquitetura de microsserviços

Princípio fundamental:

**Database per Service**

Cada microsserviço possui seu próprio banco.

Benefícios:
- autonomia das equipes
- deploy independente
- desacoplamento de schema

---

# O Princípio do Banco de Dados por Microsserviço

Cada serviço é **dono de seus dados**.

Outros serviços acessam dados **via API**, nunca diretamente no banco.

---

# Exemplo: Transição de Monolítico para Microsserviços

Antes:

Monólito → banco único

Depois:

User Service → user DB  
Order Service → order DB  
Payment Service → payment DB

---

# Problemas de Acoplamento

Banco compartilhado cria:

- dependência entre equipes
- deploy coordenado
- mudanças de schema arriscadas

---

# Benefícios do Banco de Dados por Microsserviço

- autonomia de equipes
- evolução independente
- isolamento de falhas

---

# Desafios do Princípio

- latência adicional
- ausência de JOIN
- ausência de transações distribuídas

---

# Soluções Alternativas

- cache local
- replicação de dados
- event sourcing
- CQRS

---

# Conclusão
Database per Service melhora autonomia mas exige arquitetura distribuída.

---

# O Princípio DRY em Microsserviços e Bibliotecas Compartilhadas

DRY significa **não repetir código**.

Em microsserviços, compartilhar bibliotecas pode gerar acoplamento.

---

# O que é o Princípio DRY?
Evitar duplicação de lógica.

Normalmente feito via:
- bibliotecas
- módulos reutilizáveis

---

# Desafios das Bibliotecas Compartilhadas em Microsserviços

- dependência entre serviços
- rebuild obrigatório
- dependency hell

---

# Alternativas às Bibliotecas Compartilhadas

- criar novo microsserviço
- geração de código
- duplicação controlada

---

# Ajuste de Limites de Microsserviços

Se muitos serviços compartilham lógica,
talvez os limites estejam errados.

---

# Microsserviço Específico para Lógica Compartilhada

Criar um serviço dedicado para lógica reutilizada.

---

# Modelos de Dados Compartilhados

Modelos podem ser compartilhados via:

- OpenAPI
- Protobuf
- Avro

---

# Duplicar Códigos Simples

Pequenos utilitários podem ser duplicados para manter autonomia.

---

# Uso do Sidecar Pattern

Processo auxiliar executando junto ao serviço.

Exemplo:
- proxy
- logging
- service mesh

---

# Bibliotecas Altamente Estáveis

Bibliotecas extremamente estáveis podem ser compartilhadas.

---

# Duplicação de Dados em Microsserviços

Aceitável para performance.

Mas:
- apenas um serviço é **source of truth**
- consistência passa a ser **eventual**

---

# Autonomia Estruturada para Equipes de Desenvolvimento

Três níveis de autonomia.

### Padronização total
Todas equipes usam mesma stack.

### Liberdade controlada
Stack definida, mas algumas escolhas livres.

### Total autonomia
Cada equipe decide tecnologia.

---

# Fatores que Influenciam os Limites

- domínio de negócio
- organização das equipes
- escalabilidade
- dependências

---

# Padrão de Arquitetura de Micro‑frontends

Divide frontend em aplicações menores independentes.

---

# Problemas de um Front‑End Monolítico

- builds grandes
- deploy arriscado
- baixa autonomia de times

---

# Introdução ao Padrão Micro‑Frontends

Frontend dividido em módulos independentes.

Exemplo:
- checkout app
- product catalog app

---

# Benefícios dos Micro‑Frontends

- deploy independente
- equipes autônomas
- escalabilidade organizacional

---

# Gerenciamento de API para Arquitetura de Microsserviços

Muitos serviços expõem APIs.

Necessário gerenciar acesso.

---

# O Problema do Gerenciamento de APIs

Clientes precisam acessar múltiplos serviços.

---

# A Solução: Gateway de API

Gateway centraliza:

- autenticação
- roteamento
- rate limiting

---

# Gateway de API vs Balanceador de Carga

Load Balancer:
- distribui tráfego

API Gateway:
- gerencia APIs
- aplica políticas

---

# Introdução à Arquitetura Orientada a Eventos

Arquitetura baseada em **eventos assíncronos**.

Producer → Broker → Consumer

---

# Motivação

Evitar acoplamento síncrono entre serviços.

---

# Modelo Request‑Response

Comunicação síncrona tradicional via HTTP.

---

# Arquitetura Orientada a Eventos

Serviços publicam eventos que outros serviços consomem.

---

# Benefícios

- desacoplamento
- escalabilidade
- processamento assíncrono

---

# Casos de uso de arquitetura orientada a eventos

- processamento assíncrono
- pipelines de dados
- sistemas altamente escaláveis

---

# Semântica de entrega de mensagens

Tipos de garantia:

### At most once
pode perder mensagens

### At least once
pode duplicar mensagens

### Exactly once
garantia total

---

# Saga Pattern

Gerencia transações distribuídas.

Duas abordagens:

### Orquestração
controlador central.

### Coreografia
serviços reagem a eventos.

---

# CQRS Pattern

Separação entre:

- comandos (write)
- consultas (read)

Benefícios:
- performance
- escalabilidade

---

# Event Sourcing Pattern

Estado armazenado como sequência de eventos.

Benefícios:
- auditoria
- reconstrução de estado

---

# Testing Microservices and Event‑Driven Architecture

Testar sistemas distribuídos é mais complexo.

---

# Pirâmide de testes

Base:
- unit tests

Meio:
- integration tests

Topo:
- end‑to‑end tests

---

# Contract Tests

Garantem compatibilidade entre serviços.

---

# Observabilidade na Arquitetura de Microsserviços

Três pilares:

1. logs
2. metrics
3. tracing

---

# Registro Distribuído (Distributed Logging)

Boas práticas:

- logs centralizados
- logs estruturados
- correlation id

---

# Metrics

Métricas principais:

1. tráfego
2. erros
3. latência
4. saturação
5. utilização

---

# Implantação em produção

Infraestruturas possíveis:

- máquinas virtuais
- serverless
- containers

---

# Máquinas virtuais

Podem ser:

- multitenant
- dedicadas

---

# Serverless (FaaS)

Executa código sob demanda.

Vantagens:
- escalabilidade automática

Desvantagens:
- cold start
- limites de execução

---

# Contêineres

Resolvem problema de **paridade de ambientes**.

Benefícios:
- portabilidade
- isolamento

---

# Kubernetes

Orquestra containers.

Responsabilidades:

- scaling
- auto healing
- service discovery
- deploy

