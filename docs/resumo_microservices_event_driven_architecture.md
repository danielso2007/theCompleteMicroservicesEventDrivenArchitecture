
# Resumo Detalhado — The Complete Microservices & Event‑Driven Architecture

## 1. Introdução
A arquitetura de microsserviços é um estilo arquitetural onde um sistema é dividido em múltiplos serviços independentes. Cada serviço possui:
- responsabilidade específica
- ciclo de vida independente
- equipe responsável
- banco de dados próprio

Esse modelo surgiu para resolver problemas de escalabilidade organizacional e técnica encontrados em arquiteturas monolíticas.

---

# 2. Arquitetura Web Tradicional (Monolítica)

Arquitetura clássica de aplicações web é composta por três camadas:

## Camadas

### 1. Presentation Layer
Interface com o usuário.

Exemplos:
- Web browsers
- Mobile apps
- Frontend SPA

### 2. Application / Business Layer
Executa regras de negócio.

Exemplos:
- APIs REST
- processamento de pedidos
- autenticação

### 3. Data Layer
Responsável pela persistência.

Exemplos:
- bancos relacionais
- armazenamento de arquivos

## Vantagens

- simplicidade de implementação
- deploy simples
- boa produtividade para equipes pequenas

## Problemas com crescimento

Quando o sistema cresce:

- base de código grande
- builds lentos
- deploy arriscado
- dependência tecnológica forte
- conflitos entre desenvolvedores

---

# 3. Arquitetura de Microsserviços

Microsserviços dividem o sistema em serviços independentes.

Cada serviço:

- possui domínio específico
- pode escalar independentemente
- pode usar tecnologias diferentes
- é implantado separadamente

## Benefícios

### Escalabilidade organizacional
Times trabalham em serviços isolados.

### Escalabilidade técnica
Serviços podem escalar individualmente.

### Resiliência
Falha em um serviço não derruba todo sistema.

### Evolução tecnológica
Cada serviço pode usar linguagem ou framework diferente.

---

# 4. Desafios dos Microsserviços

Apesar dos benefícios, microsserviços trazem complexidade.

## Principais desafios

### Comunicação distribuída
Chamadas locais viram chamadas de rede.

### Latência
Requests passam por múltiplos serviços.

### Falhas de rede
Serviços podem ficar indisponíveis.

### Observabilidade complexa
Debug exige rastreamento distribuído.

### Testes
Integração entre serviços é mais difícil.

---

# 5. Princípios para Definir Limites de Microsserviços

## 5.1 Coesão

Componentes que mudam juntos devem permanecer no mesmo serviço.

Exemplo:

Serviço de produtos contém:
- cadastro
- atualização
- busca

Não deve estar espalhado entre múltiplos serviços.

---

## 5.2 Princípio da Responsabilidade Única

Cada microsserviço deve possuir apenas uma responsabilidade.

Isso evita ambiguidade e facilita manutenção.

---

## 5.3 Baixo Acoplamento

Serviços devem depender o mínimo possível de outros.

Objetivos:
- evitar cascata de chamadas
- reduzir dependências
- facilitar substituição de serviços

---

# 6. Decomposição de Sistemas

Existem duas abordagens principais.

## 6.1 Decomposição por Capacidade de Negócio

Sistema dividido por funcionalidades do negócio.

Exemplo e‑commerce:

- Product Service
- Order Service
- Review Service
- Cart Service
- Shipping Service

Vantagens:
- alta coesão
- alinhamento com negócio

---

## 6.2 Decomposição por Subdomínio (DDD)

Baseado em Domain Driven Design.

### Tipos de subdomínio

#### Core Domain
Diferencial da empresa.

Exemplo:
- catálogo de produtos

#### Supporting Domain
Suporte ao negócio.

Exemplo:
- pedidos
- estoque

#### Generic Domain
Funcionalidades comuns.

Exemplo:
- autenticação
- logs
- analytics

---

# 7. Migração de Monólito para Microsserviços

A migração não deve ser feita usando abordagem Big Bang.

## Problemas do Big Bang

- alto risco
- interrupção de desenvolvimento
- estimativa difícil

---

## Migração Incremental

Migrar partes do sistema gradualmente.

### Critérios para escolher componentes

- áreas com mudanças frequentes
- serviços com necessidade de escalabilidade
- módulos bem isolados

---

# 8. Strangler Fig Pattern

Padrão inspirado em planta que cresce ao redor de uma árvore antiga.

Estratégia:

1. Introduzir API Gateway
2. Criar novo microserviço
3. Redirecionar tráfego gradualmente
4. Remover funcionalidade do monólito

Isso permite migração segura.

---

# 9. Banco de Dados em Microsserviços

Princípio fundamental:

**Database per Service**

Cada microsserviço possui seu próprio banco.

Benefícios:

- autonomia das equipes
- independência de schema
- deploy independente

---

## Desafios

### Latência
Dados precisam ser acessados via API.

### Ausência de JOIN
Dados estão distribuídos.

### Transações distribuídas
Dificuldade em manter atomicidade.

---

## Soluções

- replicação de dados
- cache local
- event sourcing
- CQRS

---

# 10. DRY em Microsserviços

DRY (Don't Repeat Yourself) nem sempre se aplica a microsserviços.

Bibliotecas compartilhadas criam:

- acoplamento
- dependência entre serviços
- necessidade de rebuild geral

---

## Alternativas

### Novo microserviço
Encapsular lógica compartilhada.

### Code generation
Gerar código via schema.

### Duplicação de código
Aceitável para manter autonomia.

### Sidecar Pattern
Container auxiliar executando junto ao serviço.

---

# 11. Duplicação de Dados

Às vezes necessário para performance.

Exemplo:

Serviço de produto armazena cache de avaliações.

Mas:

- fonte da verdade permanece no serviço original
- consistência passa a ser eventual

---

# 12. Arquitetura Orientada a Eventos

Comunicação baseada em eventos assíncronos.

Fluxo:

Producer → Broker → Consumer

Exemplo:

OrderCreated
→ Payment Service
→ Inventory Service
→ Shipping Service

Benefícios:

- desacoplamento
- escalabilidade
- processamento assíncrono

---

# 13. Semântica de Entrega de Eventos

## At Most Once
Mensagem pode ser perdida.

## At Least Once
Mensagem pode ser duplicada.

## Exactly Once
Garantia total, porém complexa.

---

# 14. Padrões Avançados

## Saga Pattern

Gerencia transações distribuídas.

### Orquestração
Um serviço central controla fluxo.

### Coreografia
Serviços reagem a eventos.

---

## CQRS

Separação entre leitura e escrita.

Write model → comandos

Read model → consultas

Benefícios:

- leitura otimizada
- escalabilidade

---

## Event Sourcing

Estado armazenado como sequência de eventos.

Benefícios:

- auditoria completa
- reconstrução de estado
- histórico de alterações

---

# 15. Testes em Microsserviços

Pirâmide de testes adaptada.

Tipos:

- unit tests
- integration tests
- contract tests
- end‑to‑end tests

Contract tests garantem compatibilidade entre serviços.

---

# 16. Observabilidade

Três pilares:

## Logs
Registro de eventos.

## Metrics
Indicadores de performance.

## Tracing
Rastreamento de requisições.

Ferramentas comuns:

- OpenTelemetry
- Prometheus
- Grafana
- ELK
- Jaeger

---

# 17. Infraestrutura

## Máquinas virtuais

- isolamento
- controle total

## Serverless (FaaS)

Execução baseada em eventos.

Vantagens:
- escalabilidade automática

Desvantagens:
- cold start
- limitação de execução

---

## Containers

Benefícios:

- consistência entre ambientes
- portabilidade
- isolamento

---

# 18. Kubernetes

Plataforma de orquestração de containers.

Responsável por:

- scaling automático
- auto‑healing
- service discovery
- deploy contínuo

Arquitetura inclui:

- Control Plane
- Worker Nodes
- Pods
- Services

---

# Conclusão

Arquiteturas modernas combinam:

Microservices
+
Event‑Driven Architecture
+
Cloud Native Infrastructure

Principais princípios:

- serviços coesos
- responsabilidade única
- baixo acoplamento
- banco de dados por serviço
- comunicação assíncrona por eventos

Essas práticas permitem construir sistemas altamente escaláveis, resilientes e evolutivos.
