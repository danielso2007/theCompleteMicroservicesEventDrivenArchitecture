- [API](#api)
  - [Segurança](#segurança)
  - [Liberdade com limites:](#liberdade-com-limites)
  - [Linguagens de programação](#linguagens-de-programação)
  - [Tecnologias de banco de dados](#tecnologias-de-banco-de-dados)
  - [Autonomia completa:](#autonomia-completa)
  - [Processo de lançamento](#processo-de-lançamento)
  - [Cronograma e frequência de lançamento](#cronograma-e-frequência-de-lançamento)
  - [Scripts personalizados para desenvolvimento e teste local](#scripts-personalizados-para-desenvolvimento-e-teste-local)
  - [Documentação](#documentação)
  - [O processo de integração para novos desenvolvedores](#o-processo-de-integração-para-novos-desenvolvedores)
  - [Padrão de Arquitetura de Micro-frontends](#padrão-de-arquitetura-de-micro-frontends)
  - [Resumo deste capítulo:](#resumo-deste-capítulo-2)
  - [Neste capítulo, seguiremos os seguintes passos:](#neste-capítulo-seguiremos-os-seguintes-passos)
  - [Problemas de um Front-End Monolítico](#problemas-de-um-front-end-monolítico)
  - [No back-end, o sistema já segue as melhores práticas de microsserviços:](#no-back-end-o-sistema-já-segue-as-melhores-práticas-de-microsserviços)
  - [Problemas organizacionais:](#problemas-organizacionais)
  - [Dependência cruzada entre equipes:](#dependência-cruzada-entre-equipes)
  - [Conhecimento disperso:](#conhecimento-disperso)
  - [Problemas técnicos:](#problemas-técnicos)
  - [Crescimento da base de código:](#crescimento-da-base-de-código)
  - [Gargalos em releases:](#gargalos-em-releases)
  - [Introdução ao Padrão Micro-Frontends](#introdução-ao-padrão-micro-frontends)
  - [Características do Micro-Frontend:](#características-do-micro-frontend)
  - [Divisão por domínios de negócio:](#divisão-por-domínios-de-negócio)
  - [Autonomia:](#autonomia)
  - [Desacoplamento:](#desacoplamento)
  - [Exemplo Prático](#exemplo-prático)
  - [Quando o usuário acessa a página inicial da plataforma:](#quando-o-usuário-acessa-a-página-inicial-da-plataforma)
  - [Em seguida, invoca os pontos de entrada dos micro-frontends de:](#em-seguida-invoca-os-pontos-de-entrada-dos-micro-frontends-de)
  - [Quando o usuário navega para a página de perfil, o contêiner:](#quando-o-usuário-navega-para-a-página-de-perfil-o-contêiner)
  - [Benefícios dos Micro-Frontends](#benefícios-dos-micro-frontends)
  - [Manutenção simplificada:](#manutenção-simplificada)
  - [Autonomia das equipes:](#autonomia-das-equipes)
  - [Implantações independentes:](#implantações-independentes)
  - [Testes mais rápidos:](#testes-mais-rápidos)
  - [Práticas Recomendadas](#práticas-recomendadas)
  - [Carregamento em tempo de execução:](#carregamento-em-tempo-de-execução)
  - [Isolamento de estado:](#isolamento-de-estado)
  - [Reutilização inteligente:](#reutilização-inteligente)
  - [Conclusão](#conclusão-1)
  - [Gerenciamento de API para Arquitetura de Microsserviços](#gerenciamento-de-api-para-arquitetura-de-microsserviços)
  - [O Problema do Gerenciamento de APIs](#o-problema-do-gerenciamento-de-apis)
  - [A Solução: Gateway de API](#a-solução-gateway-de-api)
  - [Gateway de API vs. Balanceador de Carga](#gateway-de-api-vs-balanceador-de-carga)
  - [Conclusão](#conclusão-2)
  - [Introdução à Arquitetura Orientada a Eventos](#introdução-à-arquitetura-orientada-a-eventos)
  - [Resumo:](#resumo)
  - [Motivação](#motivação)
  - [Abordagem Tradicional: Modelo de Requisição-Resposta](#abordagem-tradicional-modelo-de-requisição-resposta)
  - [Uma solução seria encadear solicitações:](#uma-solução-seria-encadear-solicitações)
  - [Vantagem:](#vantagem)
  - [Desvantagens:](#desvantagens-1)
  - [Alternativa: Padrão de Orquestração](#alternativa-padrão-de-orquestração)
  - [Solução: Arquitetura Orientada a Eventos](#solução-arquitetura-orientada-a-eventos)
  - [Benefícios](#benefícios)
  - [Exemplo Prático](#exemplo-prático-1)
  - [Para o cenário de assinatura:](#para-o-cenário-de-assinatura)
  - [Conclusão](#conclusão-3)
  - [Casos de uso e padrões de arquitetura orientada a eventos](#casos-de-uso-e-padrões-de-arquitetura-orientada-a-eventos)
  - [Resumo:](#resumo-1)
  - [Casos de Uso para a Arquitetura Orientada a Eventos](#casos-de-uso-para-a-arquitetura-orientada-a-eventos)
  - [Entrega Confiável](#entrega-confiável)
  - [Casos em que o Modelo de Request-Response é Preferível](#casos-em-que-o-modelo-de-request-response-é-preferível)
  - [Combinação de Modelos](#combinação-de-modelos)
  - [Padrões de Entrega de Eventos](#padrões-de-entrega-de-eventos)
  - [Uso Ideal:](#uso-ideal)
  - [Uso Ideal:](#uso-ideal-1)
  - [Conclusão](#conclusão-4)
  - [Semântica de entrega de mensagens em arquitetura orientada a eventos](#semântica-de-entrega-de-mensagens-em-arquitetura-orientada-a-eventos)
  - [Resumo:](#resumo-2)
  - [O Problema da Comunicação entre Microsserviços](#o-problema-da-comunicação-entre-microsserviços)
  - [Entrega em Arquiteturas Orientadas a Eventos](#entrega-em-arquiteturas-orientadas-a-eventos)
  - [Semântica de Entrega "Máximo uma vez” (At most once)](#semântica-de-entrega-máximo-uma-vez-at-most-once)
  - [Vantagens:](#vantagens)
  - [Desvantagens:](#desvantagens-2)
  - [Semântica de Entrega "Pelo menos uma vez” (At least once)](#semântica-de-entrega-pelo-menos-uma-vez-at-least-once)
  - [Vantagens:](#vantagens-1)
  - [Desvantagens:](#desvantagens-3)
  - [Semântica de Entrega "Exatamente uma vez” (Exactly once)](#semântica-de-entrega-exatamente-uma-vez-exactly-once)
  - [Vantagens:](#vantagens-2)
  - [Desvantagens:](#desvantagens-4)
  - [Conclusão](#conclusão-5)
  - [Microsserviços Orientados a Eventos - Padrões de Design](#microsserviços-orientados-a-eventos---padrões-de-design)
  - [Saga Pattern](#saga-pattern)
  - [Resumo:](#resumo-3)
  - [1. O Problema a Ser Resolvido](#1-o-problema-a-ser-resolvido)
  - [2. O Conceito de Transações ACID](#2-o-conceito-de-transações-acid)
  - [3. Como o Padrão Saga Resolve o Problema](#3-como-o-padrão-saga-resolve-o-problema)
  - [4. Implementação do Padrão Saga](#4-implementação-do-padrão-saga)
  - [Existem duas maneiras principais de implementar o padrão Saga:](#existem-duas-maneiras-principais-de-implementar-o-padrão-saga)
  - [4.1 Orquestração com Serviço de Fluxo de Trabalho](#41-orquestração-com-serviço-de-fluxo-de-trabalho)
  - [Etapas do fluxo de trabalho:](#etapas-do-fluxo-de-trabalho)
  - [Operações de compensação:](#operações-de-compensação)
  - [Fluxo de execução:](#fluxo-de-execução)
  - [4.2 Arquitetura Orientada por Eventos](#42-arquitetura-orientada-por-eventos)
  - [Eventos:](#eventos)
  - [Reversão de transação:](#reversão-de-transação)
  - [5. Comparando as Abordagens](#5-comparando-as-abordagens)
  - [Orquestração com fluxo de trabalho:](#orquestração-com-fluxo-de-trabalho)
  - [Arquitetura orientada por eventos:](#arquitetura-orientada-por-eventos)
  - [6. Conclusão](#6-conclusão)
  - [CQRS Pattern](#cqrs-pattern)
  - [Resumo:](#resumo-4)
  - [1. O Que É o Padrão CQRS?](#1-o-que-é-o-padrão-cqrs)
  - [Operações de comando:](#operações-de-comando)
  - [Alteram o estado do sistema, como:](#alteram-o-estado-do-sistema-como)
  - [Operações de consulta:](#operações-de-consulta)
  - [Exemplos:](#exemplos)
  - [2. Como Funciona o CQRS?](#2-como-funciona-o-cqrs)
  - [Separação de responsabilidades:](#separação-de-responsabilidades)
  - [Serviço de comando:](#serviço-de-comando)
  - [Serviço de consulta:](#serviço-de-consulta)
  - [3. Benefícios do Padrão CQRS](#3-benefícios-do-padrão-cqrs)
  - [Separação de Preocupações:](#separação-de-preocupações)
  - [Evolução Independente:](#evolução-independente)
  - [Desempenho Otimizado:](#desempenho-otimizado)
  - [Banco de dados de comandos:](#banco-de-dados-de-comandos)
  - [Banco de dados de consultas:](#banco-de-dados-de-consultas)
  - [Escalabilidade:](#escalabilidade)
  - [4. Casos de Uso do CQRS em Microsserviços](#4-casos-de-uso-do-cqrs-em-microsserviços)
  - [Otimização de Operações de Leitura e Escrita:](#otimização-de-operações-de-leitura-e-escrita)
  - [Unificação de Dados em Sistemas Distribuídos:](#unificação-de-dados-em-sistemas-distribuídos)
  - [Resolução do problema de união de dados:](#resolução-do-problema-de-união-de-dados)
  - [Solução com CQRS:](#solução-com-cqrs)
  - [5. Considerações Importantes](#5-considerações-importantes)
  - [Consistência Eventual:](#consistência-eventual)
  - [6. Exemplo Real: Sistema de Avaliações por Crowdsourcing](#6-exemplo-real-sistema-de-avaliações-por-crowdsourcing)
  - [Contexto:](#contexto)
  - [Desafios:](#desafios)
  - [Comando:](#comando)
  - [Garantir validação e lógica comercial rigorosa:](#garantir-validação-e-lógica-comercial-rigorosa)
  - [Consulta:](#consulta)
  - [Solução com CQRS:](#solução-com-cqrs-1)
  - [Criar um serviço de busca de negócios:](#criar-um-serviço-de-busca-de-negócios)
  - [Fluxo:](#fluxo)
  - [Conclusão](#conclusão-6)
  - [O padrão CQRS oferece soluções práticas para arquiteturas de microsserviços ao:](#o-padrão-cqrs-oferece-soluções-práticas-para-arquiteturas-de-microsserviços-ao)
  - [Event Sourcing Pattern](#event-sourcing-pattern)
  - [Resumo:](#resumo-5)
  - [Armazenamento e Representação de Eventos](#armazenamento-e-representação-de-eventos)
  - [Os eventos podem ser armazenados de duas maneiras principais:](#os-eventos-podem-ser-armazenados-de-duas-maneiras-principais)
  - [Benefícios Adicionais](#benefícios-adicionais)
  - [Estratégias de Leitura e Reconstrução](#estratégias-de-leitura-e-reconstrução)
  - [Testing Microservices and Event-Driven Architecture](#testing-microservices-and-event-driven-architecture)
  - [Pirâmide de testes para microsserviços - Introdução e desafios](#pirâmide-de-testes-para-microsserviços---introdução-e-desafios)
  - [Testes de unidade](#testes-de-unidade)
  - [Testes de integração](#testes-de-integração)
  - [Testes funcionais ou de ponta a ponta](#testes-funcionais-ou-de-ponta-a-ponta)
  - [Resumo:](#resumo-6)
  - [Revisão da Pirâmide de Testes Monolítica](#revisão-da-pirâmide-de-testes-monolítica)
  - [Adaptando a Pirâmide para Microsserviços](#adaptando-a-pirâmide-para-microsserviços)
  - [Desafios no Teste de Microsserviços](#desafios-no-teste-de-microsserviços)
  - [1. Complexidade dos Testes E2E](#1-complexidade-dos-testes-e2e)
  - [2. Dificuldade em Testes de Integração](#2-dificuldade-em-testes-de-integração)
  - [3. Desafios em Arquitetura Orientada por Eventos](#3-desafios-em-arquitetura-orientada-por-eventos)
  - [contract tests e testes de produção](#contract-tests-e-testes-de-produção)
  - [Soluções de teste de contrato](#soluções-de-teste-de-contrato)
  - [Resumo:](#resumo-7)
  - [Mocking Leve como Solução para Testes de Integração](#mocking-leve-como-solução-para-testes-de-integração)
  - [Testes de Contrato (Contract Tests)](#testes-de-contrato-contract-tests)
  - [Testes de Contrato em Arquiteturas Orientadas por Eventos](#testes-de-contrato-em-arquiteturas-orientadas-por-eventos)
  - [Testes em Produção](#testes-em-produção)
  - [Conclusão](#conclusão-7)
  - [Observabilidade na Arquitetura de Microsserviços](#observabilidade-na-arquitetura-de-microsserviços)
  - [Introdução aos três pilares da observabilidade em microsserviços](#introdução-aos-três-pilares-da-observabilidade-em-microsserviços)
  - [Resumo:](#resumo-8)
  - [Observabilidade vs. Monitoramento](#observabilidade-vs-monitoramento)
  - [A Relevância da Observabilidade em Microsserviços](#a-relevância-da-observabilidade-em-microsserviços)
  - [Problemas são ainda mais desafiadores porque:](#problemas-são-ainda-mais-desafiadores-porque)
  - [Os Três Pilares da Observabilidade](#os-três-pilares-da-observabilidade)
  - [Logs](#logs)
  - [Métricas](#métricas)
  - [Rastreios (Traces)](#rastreios-traces)
  - [Como os Pilares Trabalham em Conjunto](#como-os-pilares-trabalham-em-conjunto)
  - [Conclusão](#conclusão-8)
  - [Registro Distribuído (Distributed Logging)](#registro-distribuído-distributed-logging)
  - [Resumo:](#resumo-9)
  - [O Que é Registro em Log?](#o-que-é-registro-em-log)
  - [Práticas Recomendadas para Registro Distribuído](#práticas-recomendadas-para-registro-distribuído)
  - [1. Centralização dos Logs](#1-centralização-dos-logs)
  - [2. Formato Padronizado e Estruturado](#2-formato-padronizado-e-estruturado)
  - [3. Níveis de Log](#3-níveis-de-log)
  - [Atribua níveis de severidade a cada entrada de log, como:](#atribua-níveis-de-severidade-a-cada-entrada-de-log-como)
  - [4. IDs de Correlação](#4-ids-de-correlação)
  - [5. Contexto Rico nos Logs](#5-contexto-rico-nos-logs)
  - [Cada linha de log deve incluir informações úteis para depuração, como:](#cada-linha-de-log-deve-incluir-informações-úteis-para-depuração-como)
  - [6. Minimização e Privacidade dos Dados](#6-minimização-e-privacidade-dos-dados)
  - [Benefícios do Registro Distribuído](#benefícios-do-registro-distribuído)
  - [Metrics](#metrics)
  - [The Five (Golden) Types of Signals:](#the-five-golden-types-of-signals)
  - [Traffic](#traffic)
  - [Errors](#errors)
  - [Latency](#latency)
  - [Saturation](#saturation)
  - [Utilization](#utilization)
  - [Resumo:](#resumo-10)
  - [O que são métricas?](#o-que-são-métricas)
  - [Os problemas da coleta excessiva](#os-problemas-da-coleta-excessiva)
  - [Os cinco tipos principais de sinais](#os-cinco-tipos-principais-de-sinais)
  - [1. Tráfego](#1-tráfego)
  - [2. Erros](#2-erros)
  - [3. Latência](#3-latência)
  - [4. Saturação](#4-saturação)
  - [5. Utilização](#5-utilização)
  - [Considerações finais](#considerações-finais)
  - [Distributed Tracing](#distributed-tracing)
  - [Soluções de Rastreamento Distribuído](#soluções-de-rastreamento-distribuído)
  - [Estruturas de Instrumentação de Rastreamento Distribuído](#estruturas-de-instrumentação-de-rastreamento-distribuído)
  - [Backends de rastreamento distribuído](#backends-de-rastreamento-distribuído)
  - [Resumo:](#resumo-11)
  - [Motivação para o Rastreamento Distribuído](#motivação-para-o-rastreamento-distribuído)
  - [O que é o Rastreamento Distribuído](#o-que-é-o-rastreamento-distribuído)
  - [Funcionamento do Rastreamento Distribuído](#funcionamento-do-rastreamento-distribuído)
  - [Desafios do Rastreamento Distribuído](#desafios-do-rastreamento-distribuído)
  - [Custo Operacional:](#custo-operacional)
  - [Conclusão](#conclusão-9)
  - [Implantação de microsserviços e arquitetura orientada a eventos em produção](#implantação-de-microsserviços-e-arquitetura-orientada-a-eventos-em-produção)
  - [Multitenancy em Cloud Computing:](#multitenancy-em-cloud-computing)
  - [Multitenancy em Virtual Machines:](#multitenancy-em-virtual-machines)
  - [Serviço de Nuvem de Máquina Virtual Multitenant](#serviço-de-nuvem-de-máquina-virtual-multitenant)
  - [Resumo:](#resumo-12)
  - [Máquinas Virtuais na Nuvem](#máquinas-virtuais-na-nuvem)
  - [Vantagens das VMs Multitenant na Nuvem](#vantagens-das-vms-multitenant-na-nuvem)
  - [Desvantagens das VMs Multitenant](#desvantagens-das-vms-multitenant)
  - [Instâncias ou Hosts Dedicados](#instâncias-ou-hosts-dedicados)
  - [Instâncias Dedicadas](#instâncias-dedicadas)
  - [Hosts Dedicados](#hosts-dedicados)
  - [Considerações Finais](#considerações-finais-1)
  - [Serviços Web da Amazon (AWS)](#serviços-web-da-amazon-aws)
  - [Plataforma de nuvem do Google (GCP)](#plataforma-de-nuvem-do-google-gcp)
  - [Microsoft Azure](#microsoft-azure)
  - [Resumo:](#resumo-13)
  - [Cenários Reais: Identificando os Problemas](#cenários-reais-identificando-os-problemas)
  - [O Papel do FaaS](#o-papel-do-faas)
  - [Quando o evento ocorre, o provedor:](#quando-o-evento-ocorre-o-provedor)
  - [Vantagens do FaaS](#vantagens-do-faas)
  - [Redução de Custos de Infraestrutura:](#redução-de-custos-de-infraestrutura)
  - [Escalabilidade Automática:](#escalabilidade-automática)
  - [Redução de Sobrecarga de Desenvolvimento:](#redução-de-sobrecarga-de-desenvolvimento)
  - [Desvantagens do FaaS](#desvantagens-do-faas)
  - [Custos Crescentes com Mudança no Padrão de Tráfego:](#custos-crescentes-com-mudança-no-padrão-de-tráfego)
  - [Desempenho Menos Previsível:](#desempenho-menos-previsível)
  - [Riscos de Segurança:](#riscos-de-segurança)
  - [Considerações Finais](#considerações-finais-2)
  - [Contêineres para microsserviços em desenvolvimento, testes e produção](#contêineres-para-microsserviços-em-desenvolvimento-testes-e-produção)
  - [Resumo:](#resumo-14)
  - [O Problema: Paridade de Ambientes](#o-problema-paridade-de-ambientes)
  - [A Solução: Contêineres](#a-solução-contêineres)
  - [Benefícios em Produção](#benefícios-em-produção)
  - [Em produção, os contêineres oferecem várias vantagens:](#em-produção-os-contêineres-oferecem-várias-vantagens)
  - [Desafios na Produção](#desafios-na-produção)
  - [Apesar dos benefícios, a produção traz novos desafios:](#apesar-dos-benefícios-a-produção-traz-novos-desafios)
  - [Orquestração de contêineres e Kubernetes para arquitetura de microsserviços](#orquestração-de-contêineres-e-kubernetes-para-arquitetura-de-microsserviços)
  - [Resumo:](#resumo-15)
  - [O que é Orquestração de Contêineres?](#o-que-é-orquestração-de-contêineres)
  - [Arquitetura do Kubernetes](#arquitetura-do-kubernetes)
  - [Estrutura do Cluster](#estrutura-do-cluster)
  - [Um cluster Kubernetes é composto por:](#um-cluster-kubernetes-é-composto-por)
  - [Nós de Trabalho: Executam os contêineres de microsserviços. Cada nó contém:](#nós-de-trabalho-executam-os-contêineres-de-microsserviços-cada-nó-contém)
  - [Conceitos Fundamentais](#conceitos-fundamentais)
  - [Alta Disponibilidade e Escalabilidade](#alta-disponibilidade-e-escalabilidade)
  - [Para sistemas em larga escala, clusters Kubernetes podem incluir:](#para-sistemas-em-larga-escala-clusters-kubernetes-podem-incluir)
  - [Benefícios e Complexidade](#benefícios-e-complexidade)


## The Complete Microservices & Event-Driven Architecture



A arquitetura de microsserviços é o estilo arquitetônico mais moderno e popular do setor. Nesse estilo de arquitetura, todo o nosso sistema é organizado como uma coleção de serviços independentes. Cada um tem seu escopo restrito de responsabilidade e é de propriedade total de uma equipe independente de desenvolvedores.



Atualmente, a maioria das maiores e mais bem-sucedidas empresas de tecnologia usam a arquitetura de microsserviços, o que é considerado um dos maiores contribuintes para seu sucesso. Quando feita corretamente, a arquitetura de microsserviços permite que as organizações escalem para milhares ou até dezenas de milhares de serviços divididos em pequenos grupos que operam de forma independente. Isso, por sua vez, permite que essas organizações criem sistemas altamente dimensionáveis que atingem bilhões de usuários, tudo isso mantendo seus custos operacionais baixos e permanecendo eficientes e inovadores.



Com essas informações, é difícil não ficar animado e começar a refatorar sua própria base de código em microsserviços. No entanto, embora a maior parte do burburinho em torno dos microsserviços seja muito positiva, um número considerável de organizações tiveram sérias dificuldades e até mesmo voltou atrás em sua decisão de usar microsserviços. E isso se deve ao fato de que a arquitetura de microsserviços, por si só, não é uma bala de prata que resolve todos os seus problemas quando aplicada corretamente e sob as condições certas.



A arquitetura de microsserviços pode realmente fazer maravilhas, mas, se aplicada incorretamente ou em uma empresa que não esteja pronta para essa mudança, pode introduzir muita sobrecarga desnecessária sem trazer nenhum benefício.



A arquitetura orientada por eventos não é nova e não requer microsserviços. Ele é comumente usado em conjunto com microsserviços, estabelecendo uma comunicação assíncrona baseada em eventos entre os microsserviços, o que nos permite obter um desacoplamento ainda maior e maior escalabilidade para nossa empresa. A arquitetura orientada por eventos também é muito útil para implementar alguns padrões de design muito avançados para a arquitetura de microsserviços.



## A arquitetura típica web



Se pensarmos na arquitetura de uma empresa típica baseada na Web, podemos dividi-la em três camadas.



## A primeira é a camada de apresentação:

Essa camada contém o código front-end do lado do cliente e é executada nos tablets dos dispositivos móveis do usuário.

E em navegadores da Web.



A segunda camada intermediária é chamada de camada lógica, às vezes chamada de camada de aplicativo ou camada de negócios:

Essa parte do sistema executa toda a nossa lógica comercial que lida com todas as interações entre nossos usuários e nosso sistema.



## E, por fim, temos a camada de dados:

Nessa parte do nosso sistema, armazenamos todas as informações necessárias sobre nossos clientes ou negócios em um armazenamento persistente.

Normalmente, isso inclui um banco de dados, mas, em alguns casos, também pode envolver o armazenamento direto de arquivos no sistema de arquivos.



Essa arquitetura de três camadas também é comumente chamada de arquitetura monolítica, porque toda a lógica comercial e o desenvolvimento de back-end estão concentrados em uma única base de código, que é a camada de aplicativos. Ele também é implantado em tempo de execução como um único processo monolítico.



Agora, antes de prosseguirmos, é importante reconhecer que essa arquitetura de três camadas ainda é o estilo arquitetônico mais comumente usado, pois oferece muitos benefícios excelentes prontos para uso.



O primeiro benefício é projetar um sistema. Usar essa arquitetura é muito fácil.

O motivo é que essa arquitetura monolítica se adapta a quase todos os sistemas baseados na Web, independentemente do setor ou do serviço que está sendo fornecido.

Seja uma revista de notícias on-line, um serviço de negociação de ações, um serviço de encontros ou um banco on-line.

A arquitetura dos sistemas pode ser exatamente a mesma em todos esses cenários.

O segundo benefício é que ele é muito fácil de implementar com uma pequena equipe de desenvolvedores full stack e algumas das estruturas web shell e tecnologias de banco de dados padrão.

Podemos facilmente ter um sistema totalmente funcional seguindo essa arquitetura.

Portanto, se formos uma pequena empresa iniciante que deseja colocar nossa ideia nas mãos dos usuários rapidamente, ou se formos apenas uma empresa com uma pequena equipe de desenvolvimento, essa arquitetura é a melhor opção.



Para citar Jeff Bezos, fundador da Amazon, o tamanho perfeito de uma equipe deve ser pequeno o suficiente para que ela possa ser alimentada com duas pizzas, o que é a chave para a eficiência e a escalabilidade. Portanto, se sua empresa se encaixa nesse modelo, não há motivo para usar algo mais complexo. No entanto, à medida que nossa empresa se torna mais bem-sucedida e nossa equipe de desenvolvimento continua crescendo, começamos a ter cada vez mais problemas muito mais sérios do que não ficar satisfeitos com duas pizzas.

## O primeiro problema do crescimento da equipe para um monolítico:

É a baixa escalabilidade organizacional, com muitos engenheiros trabalhando na mesma base de código.

Os conflitos de mesclagem de código se tornam um problema sério.

Essencialmente, todos estão pisando nos pés uns dos outros e a conclusão até mesmo do recurso mais trivial se torna mais lenta e difícil de lidar com esses problemas.

Precisamos de muito mais planejamento e coordenação, o que normalmente significa mais reuniões.

E quanto mais pessoas estiverem presentes nessas reuniões, mais longas e menos produtivas elas se tornam.



Mas o número de engenheiros não é o único problema. À medida que adicionamos mais recursos ao nosso aplicativo, nossa base de código se torna maior e mais complexa. Isso dificulta o raciocínio. Leva mais tempo para carregá-lo no IDE, é mais lento para criar e testar e mais arriscado para implantar. Portanto, como resultado, nosso cronograma de lançamentos se torna menos frequente, o que, na verdade, torna as coisas ainda piores, pois agora cada novo lançamento contém ainda mais recursos, aumentando as chances de bugs e interrupções.



Mas, além da baixa escalabilidade organizacional, um aplicativo monolítico grande também pode ter problemas técnicos que tornam o sistema menos escalável. Cada instância de aplicativo, que contém toda a nossa lógica comercial, requer muita CPU e memória. Portanto, em vez de usar hardware de commodity barato, precisamos executar cada instância. Em um computador mais sofisticado e caro.



Também estamos muito limitados às escolhas tecnológicas que potencialmente fizemos há muitos anos, e não podemos tirar proveito de tecnologias novas e melhores. Refatorar nossa base de código, mesmo de uma biblioteca para outra, pode ser um esforço enorme, sem falar na consideração de uma nova linguagem de programação ou de uma estrutura.



Outro problema é que nosso aplicativo também se torna menos estável. Até mesmo um pequeno problema de desempenho de vazamento de memória ou um bug pode afetar todo o nosso sistema e pode exigir que façamos uma reversão.



É importante ressaltar que, logicamente, a separação do aplicativo monolítico em camadas, módulos ou até mesmo bibliotecas pode ajudar muito pouco.



Mas, no final das contas, todos esses módulos diferentes ainda estão fortemente acoplados. Ainda estamos limitados a usar as mesmas tecnologias e linguagens de programação, e o aplicativo ainda precisa ser implantado como uma única unidade de tempo de execução. Portanto, agora que entendemos completamente o problema que estamos tentando resolver e as condições para considerar outra abordagem arquitetônica, estamos prontos para explorar a alternativa à arquitetura monolítica, que é a arquitetura de microsserviços.







## Arquitetura de Microsserviços - Benefícios e Desafios



Primeiro teremos uma introdução ao que é a arquitetura de microsserviços. Em seguida, aprenderemos sobre os benefícios que obtemos com os microsserviços e como eles resolvem os problemas de escalabilidade de uma arquitetura monolítica. E, por fim, discutiremos os desafios do uso de microsserviços, que aprenderemos a abordar ao longo do curso.



## O que é arquitetura de microsserviços?



Ao contrário da arquitetura de três camadas, em que toda a lógica de negócios está concentrada em um aplicativo, a arquitetura de microsserviços organiza nossa lógica de negócios como uma coleção de serviços fracamente acoplados e implantados de forma independente. Mais importante ainda, cada serviço é de propriedade de uma pequena equipe e tem um escopo restrito de responsabilidade.



Os benefícios dessa separação lógica e física muito mais refinada são os seguintes:

Em primeiro lugar, com essa arquitetura, obtemos uma escalabilidade organizacional muito maior, pois como cada serviço contém apenas um subconjunto da funcionalidade geral, a base de código de cada serviço é muito menor.

Isso permite que cada desenvolvedor carregue toda a sua base de código no IDE com muito mais rapidez.

A criação de cada microsserviço também se torna muito mais rápida porque o tamanho de cada binário é bastante reduzido.

O teste e o raciocínio sobre cada serviço isoladamente também se tornam muito mais fáceis porque há muito menos lógica para entender, executar e testar.

Essa simplicidade da base de código em cada microsserviço também acelera o processo de integração de novos membros da equipe para que nossa empresa possa crescer rapidamente e permanecer eficiente.



Tudo isso aumenta a velocidade de desenvolvimento de cada equipe, o que significa que podemos oferecer mais recursos e obter uma vantagem sobre nossos concorrentes na escalabilidade do sistema.



Também obtemos muitos benefícios com o aplicativo monolítico. Cada instância tinha que executar toda a base de código, o que exigia um hardware muito potente e caro para executar cada instância.



Quando dividimos nossa base de código em microsserviços, cada serviço é muito menor, de modo que cada instância de um microsserviço consome menos memória e CPU. Como resultado, ele pode ser executado em hardware de commodity barato e amplamente disponível.



Cada equipe também pode fazer o melhor julgamento sobre quais tecnologias beneficiaram seu serviço e também pode responder às mudanças tecnológicas com muito mais rapidez, refatorando sua base de código já pequena ou até mesmo reescrevendo todo o serviço, se necessário.



Por fim, também obtemos uma estabilidade muito maior para todo o sistema, pois cada microsserviço é implantado como uma unidade de tempo de execução separada. O raio de alcance de um bug de vazamento de memória ou de um problema de desempenho é muito menor. Na maioria dos casos, um bug em um microsserviço afetará apenas esse microsserviço ou apenas os que dependem dele em algum nível. Mas o restante do sistema pode continuar funcionando perfeitamente.



Portanto, essencialmente, os microsserviços rompem a barreira de escalabilidade que atingimos com uma arquitetura monolítica. Gosto de pensar nesses estilos arquitetônicos como duas marchas em uma bicicleta de montanha ou em um carro com transmissão manual.



A marcha mais baixa é a arquitetura monolítica, que permite que nossa empresa comece a se mover rapidamente do zero e cresça até um determinado limite. Mas se quisermos continuar crescendo, precisamos mudar de marcha e migrar para a arquitetura de microsserviços.



Portanto, agora que entendemos os benefícios dos microsserviços e como eles resolvem os problemas de escalabilidade da arquitetura monolítica de três camadas, há uma grande ressalva. Ele voltaria à sua base de código, dividindo-a em pequenos serviços e tudo mais. A partir daí, tudo seria fácil e tranquilo. Infelizmente, as coisas não são tão simples com todos os benefícios que vêm com os microsserviços. Esse estilo de arquitetura também traz muitos desafios e sobrecargas.



Começando com os desafios técnicos, o primeiro grande problema é que pegamos um sistema centralizado e o dividimos em um sistema altamente distribuído. Agora, as chamadas de método que costumavam ter um comportamento, uma taxa de sucesso e uma latência muito previsíveis tornaram-se chamadas de rede entre dois aplicativos diferentes que podem estar sendo executados em computadores diferentes.



Essas solicitações de rede agora estão atravessando uma rede não confiável, onde os pacotes podem ser perdidos ou atrasados, causando problemas de latência imprevisíveis e até mesmo erros. Além da própria rede, a natureza dos sistemas distribuídos é que cada componente é inerentemente não confiável.



Por exemplo, uma solicitação de uma instância de serviço pode atingir um processo que falhou devido a uma falha de hardware ou software ou que está sendo reiniciado como parte de uma manutenção de rotina de uma perspectiva de teste. Agora também temos novos desafios.



Por um lado, testar cada microsserviço isoladamente ficou mais rápido e fácil. Por outro lado, agora não há garantia de que, depois que todos os serviços forem implantados, eles funcionarão corretamente como um todo.



E quando fazemos uma alteração em um serviço, temos muito menos confiança de que, quando a nova versão do nosso serviço for implantada na produção, ela não quebrará outro serviço. Essa situação pode levar à criação de testes de integração muito complexos e lentos que podem reduzir nossa produtividade.



E como cada serviço pode pertencer a uma equipe diferente, é muito difícil decidir quem é o proprietário desses testes de integração para começar.



Por fim, com os microsserviços, é muito mais difícil solucionar problemas de desempenho e bugs. Vamos considerar uma situação em que uma solicitação do usuário passa por uma cadeia de microsserviços e,no final, o usuário não obtém as informações corretas, obtém um erro ou obtém as informações corretas, mas com um longo atraso. Como podemos saber qual microsserviço é responsável por esse bug ou problema de desempenho?



Como se isso não bastasse, também podemos enfrentar desafios de escalabilidade organizacional. Uma das maiores dúvidas é como definir o escopo de responsabilidade entre os microsserviços. Se definirmos os limites incorretamente, podemos, na verdade, ter mais despesas gerais organizacionais do que benefícios.



Por exemplo, se cada alteração no sistema exigir uma coordenação cuidadosa entre diferentes equipes, então não estaremos em melhor situação do que na arquitetura monolítica.



Da mesma forma, se cada equipe usar uma pilha de tecnologia, ferramentas e práticas recomendadas completamente diferentes, poderemos ter muitos esforços duplicados e também confusão ao analisar a base de código de uma equipe diferente. Portanto, como podemos ver, se não formos cuidadosos e não considerarmos todos esses desafios, podemos facilmente estar em uma situação muito pior após a migração para microsserviços do que se mantivermos um grande aplicativo monolítico.



Essa situação é comumente chamada de monólito distribuído ou, de maneira menos formal, uma grande bola de lama.



A boa notícia é que muitas empresas já passaram por todas essas dores de crescimento. Portanto, depois de muitos anos de arquitetos de software dessas empresas compartilhando conhecimento, histórias de sucesso e erros, agora podemos estabelecer um conjunto de princípios e práticas recomendadas para uma arquitetura de microsserviços bem-sucedida.



Se seguirmos esses princípios comprovados pelo setor, os benefícios que obtemos com os microsserviços excedem em muito sua sobrecarga e complexidade.



Esses benefícios incluem maior escalabilidade organizacional devido à base de código menor de cada microsserviço.

E também obtemos maior escalabilidade do sistema, o que nos permite escolher a melhor tecnologia para cada microsserviço e executá-lo em um hardware mais barato.



Por outro lado, também mencionamos alguns dos desafios e das despesas gerais que acompanham os microsserviços.



Isso inclui as complexidades e a imprevisibilidade da execução de um sistema altamente distribuído com componentes não confiáveis, que conversam entre si por meio de uma rede não confiável e o risco de redução da escalabilidade organizacional.

Se definirmos incorretamente os limites entre os microsserviços e suas equipes.









## Limites dos microsserviços - Princípios básicos





Nos capítulos anteriores, aprenderemos sobre o primeiro conjunto de princípios para definir os limites entre os microsserviços. Para chegar a esses princípios, analisaremos algumas abordagens para dividir um aplicativo monolítico existente. Esses estudos de caso não são apenas experimentos de pensamento, mas situações reais de empresas que passaram pela migração e encontraram problemas no processo. Portanto, cada estudo de caso nos ajudará a definir um novo princípio fundamental para uma migração bem-sucedida para a arquitetura de microsserviços.



Vamos migrar e apenas dividir uma grande base de código em um conjunto arbitrário de microsserviços e entregar cada um deles a uma equipe separada que não necessariamente nos beneficiará. Vamos imaginar que somos uma empresa de comércio eletrônico bem-sucedida que administra uma loja on-line para milhares de clientes. A arquitetura do nosso sistema é uma arquitetura típica de três camadas com um aplicativo da Web monolítico na camada intermediária. Esse aplicativo da Web recebe solicitações da Web de usuários que executam nosso código de front-end em seus navegadores da Web e aplicativos móveis na camada de apresentação. Na camada de dados, temos um banco de dados interno que armazena todas as nossas transações, produtos, avaliações e informações de inventário. E também temos um serviço de pagamento externo que pertence a um terceiro que lida com todo o faturamento do cartão de crédito do usuário.



Nossa arquitetura monolítica nos serviu muito bem por muitos anos, mas agora nossa base de código ficou muito grande e complexa. O tamanho binário do nosso aplicativo requer um hardware muito caro e a equipe de desenvolvimento já ultrapassou a regra das duas pizzas. Portanto, há muitas ineficiências.



Ouvimos dizer que a divisão desse aplicativo em diferentes serviços resolveria todos os nossos problemas, mas não temos certeza de como dividir esse aplicativo em microsserviços. Portanto, uma abordagem para dividir esse aplicativo monolítico seria seguir as camadas lógicas internas que já existem na base de código do aplicativo. Podemos pegar a camada de frente de loja da nossa base de código que lida com solicitações de usuários, segurança e validação de permissões e também serve o HTML JavaScript e CSS para o navegador da Web e dividi-la em seu próprio serviço, que é mantido por uma equipe separada e é fisicamente implantado como uma unidade de tempo de execução separada.



Da mesma forma, podemos pegar toda a funcionalidade comercial que lida com descontos no checkout, produtos de vendas sazonais e avaliações e executá-la como outro microsserviço. E, por fim, podemos pegar a camada de dados desse aplicativo e executá-la também como um serviço separado.



À primeira vista, essa abordagem parece uma boa ideia. Ele aproveita a separação lógica já existente em nosso aplicativo, portanto, é necessária muito pouca refatoração. No entanto, essa abordagem não funciona muito bem e não nos trará muitos benefícios. A razão para isso é simples: cada novo recurso que desenvolvemos nesse aplicativo provavelmente exigirá uma alteração na API, uma alteração nos negócios e uma alteração nos dados. Isso significa que cada microsserviço em nosso sistema estará envolvido em cada recurso, o que exige planejamento cuidadoso e coordenação de lançamento entre as diferentes equipes. Portanto, não obteremos nenhum benefício para nossa escalabilidade organizacional usando essa abordagem.



Na verdade, tudo o que fizemos aqui foi apenas transformar essa arquitetura de três camadas em uma arquitetura de cinco camadas, o que ainda não é considerado microsserviços. Dividir o aplicativo monolítico em mais camadas não vai funcionar. Isso nos leva ao primeiro princípio para definir os limites entre os microsserviços. Esse princípio é que cada microsserviço precisa ser coeso.







## Coesão:

Significa que os elementos que estão intimamente relacionados uns aos outros e que mudam juntos devem permanecer juntos. Se toda a lógica que muda em conjunto permanecer dentro dos limites do mesmo microsserviço, cada equipe poderá realmente operar de forma independente. Em nosso caso, a migração. Fracassou porque cada um de nossos microsserviços não era coeso o suficiente para melhorar nossa escalabilidade organizacional.



Agora vamos dar uma olhada em outra abordagem que muitas empresas adotaram ao migrar para os microsserviços, que se baseia em limites tecnológicos. Após uma análise cuidadosa, nossos desenvolvedores chegaram a algumas observações interessantes. Eles perceberam que, se dividissem a camada de front-end de nossa loja e reescrevessem uma parte específica dela em NodeJS com JavaScript, poderiam reduzir o número de linhas de código em 50%. E se eles escreverem a outra parte em Java, poderão melhorar o desempenho em 20%. Além disso, parte do nosso mecanismo de recomendação de produtos que exige cálculos pesados já estava separada em uma biblioteca escrita em C++.



Ao mesmo tempo, eles também perceberam que, se reescrevermos outra parte de nossa recomendação de produto em Python, podemos usar algumas bibliotecas poderosas de aprendizado de máquina que podem melhorar ainda mais nosso desempenho.



Por fim, se dividirmos parte de nossa camada de dados que se comunica com o serviço de pagamento externo para a Golang, também poderemos melhorar o desempenho e o número de linhas de código neste módulo. Depois de dividir esses módulos em microsserviços separados, observamos grandes melhorias no desempenho. No entanto, esses limites são puramente tecnológicos. Assim, as partes interessadas externas que não estão familiarizadas com a base de código, como gerentes de produto que solicitam novos recursos ou engenheiros de suporte que relatam bugs dos usuários, não sabem qual subequipe precisa receber as tarefas. Por exemplo, quando um gerente de produtos precisa atualizar o mecanismo de recomendações de produtos, não fica claro se ele precisa falar com esta equipe, com aquela equipe ou com ambas. O mesmo se aplica às alterações de API. As responsabilidades desses dois serviços de fachada não estão claramente definidas, portanto, não está claro. Por exemplo, para um desenvolvedor front-end, qual base de código precisa ser alterada para um determinado recurso?



Além disso, a terminologia de cada API é muito complicada porque estamos misturando contextos diferentes, como usuários, produtos, contas bancárias e assim por diante, tudo na mesma API. O último microsserviço, que ainda tem a maior parte da lógica comercial, tem muita responsabilidade e ainda é muito grande. Ele tem o potencial de se tornar mais um aplicativo monolítico.



Isso nos leva ao segundo princípio fundamental, que é o princípio da responsabilidade única.





## Princípio da responsabilidade única:

Esse princípio diz que “uma classe deve ter apenas um motivo para mudar”, ou seja, deve ter uma única responsabilidade. Basicamente, esse princípio trata especificamente a coesão. A coesão é definida como a afinidade funcional dos elementos de um módulo. Se refere ao relacionamento que os membros desse módulo possuem, se possuem uma relação mais direta e importante. Dessa forma, quanto mais bem definido o que sua classe faz, mais coesa ela é.



Com base nesse princípio, todo microsserviço deve fazer uma coisa e fazê-la excepcionalmente bem. Se cada microsserviço em nosso sistema seguir esse princípio, não haverá ambiguidade sobre onde uma nova parte da funcionalidade precisa ir e qual equipe precisa ser responsável por ela. Isso também ajuda a criar uma API muito clara e fácil de seguir para cada microsserviço, pois todas as entidades ou identificadores de terminologia estão vinculados a um contexto específico.



Por exemplo, se precisarmos falar com o serviço de usuário, é claro que o ID aqui é o ID do usuário, o nome é o nome do usuário e assim por diante. Mas se falarmos com o serviço de produtos, os mesmos termos terão um significado completamente diferente e não haverá nenhuma ambiguidade em torno deles. Ok, vamos fazer mais uma tentativa com base em um caso de uso real de uma empresa que está migrando para microsserviços. Desta vez, notamos a parte micro na arquitetura de microsserviços, o que nos deu a impressão de que dividir o aplicativo monolítico em pequenos serviços nos traria os melhores benefícios. Quanto menor, melhor. Portanto, podemos seguir uma abordagem um pouco mais grosseira e usar cada pacote ou módulo e transformá-lo em um microsserviço. Ou, como nosso aplicativo monolítico original foi escrito em uma linguagem orientada a objetos, poderíamos dividir cada classe em um microsserviço implantado e gerenciado de forma independente. Agora, na produção, começamos a ver problemas ainda maiores, pois cada solicitação de um usuário. Desencadeia uma cadeia de comunicação entre vários microsserviços e cada microsserviço precisa se comunicar com outros microsserviços para realizar seu trabalho.



O desempenho ficou muito ruim e a solução de problemas tornou-se quase impossível. E isso ocorre porque nossos microsserviços são fortemente acoplados uns aos outros, e cada operação exige muita comunicação entre os diferentes serviços. Portanto, o terceiro princípio que aprenderemos com essa tentativa é que os microsserviços devem ser fracamente acoplados.





## Fracamente acoplados:

Refere-se ao princípio de projetar componentes do sistema com dependências mínimas entre si, facilitando a manutenção, a escalabilidade e a testabilidade.

Independência: Módulos ou classes dependem de abstrações (interfaces) em vez de implementações concretas, conforme o Princípio da Inversão de Dependência (DIP).

Baixa dependência direta: Mudanças em um componente têm impacto limitado nos demais.

Flexibilidade: Componentes podem ser substituídos, modificados ou testados de forma isolada.



Os microsserviços com acoplamento frouxo têm muito pouca ou nenhuma interdependência. Isso significa que cada microsserviço pode executar sua funcionalidade com o mínimo de comunicação com outros microsserviços. Também é importante ressaltar que o tamanho de cada microsserviço não é tão importante, e é um equívoco comum pensar que os microsserviços precisam ser tão pequenos quanto possível. Na Thatrillionegard, o termo "microsserviços” é um tanto enganoso. Desde que nossos microsserviços sejam coesos, sigam o princípio da responsabilidade única e sejam fracamente acoplados uns aos outros, o tamanho não importa.



E também não devemos esperar que todos os nossos microsserviços tenham o mesmo tamanho. Naturalmente, alguns serão menores e outros maiores, e isso não tem problema algum.



Portanto, esses três princípios são os pré-requisitos para uma arquitetura de microsserviços bem-sucedida. Em outras palavras, se não as seguirmos, provavelmente teremos problemas mais cedo ou mais tarde. No entanto, eles ainda não nos dizem exatamente como realmente dividir o aplicativo monolítico em microsserviços que sigam esses princípios.



Neste capítulo, aprenderemos os princípios básicos mais importantes para definir os limites entre os serviços em uma arquitetura de microsserviços. Esses princípios determinam que cada microsserviço precisa ser coeso, o que significa que todos os elementos que mudam juntos permanecem dentro dos limites de um microsserviço. Cada microsserviço deve seguir o princípio de responsabilidade única, e cada microsserviço deve ser frouxamente acoplado a todos os outros microsserviços para minimizar a comunicação em tempo de execução.



Também aprendemos que, ao contrário de muitas crenças, a arquitetura micro e de microsserviços não significa que nossos serviços devam ser tão pequenos quanto possível, de modo que seu tamanho pode ser muito diferente dependendo de sua funcionalidade.





## Decomposição de uma aplicação monolítica em microsserviços



Neste capítulo, aprenderemos dois métodos para decompor um sistema em microsserviços que seguem os três princípios que aprendemos no capítulo anterior. Primeiro, aprenderemos cada técnica isoladamente e, depois, as compararemos e discutiremos a importância de escolher um método em vez de outro.



O primeiro método para decompor um sistema em microsserviços é por recursos comerciais. Nesse método, observamos e analisamos nosso sistema. De uma perspectiva puramente comercial, uma capacidade comercial é qualquer capacidade essencial que agregue valor à empresa ou a seus clientes. Isso pode incluir itens como receita, marketing, experiência do cliente e assim por diante.



Depois de identificarmos esses recursos de negócios, podemos dedicar um microsserviço separado e uma equipe para se responsabilizar totalmente por ele. Agora, há algumas maneiras de identificar esses recursos de negócios. Minha maneira favorita é fazer um experimento mental em que você descreve o sistema para uma pessoa não técnica e tenta explicar o que o sistema faz e o valor que cada recurso oferece.



Por exemplo, se fôssemos descrever uma loja on-line, provavelmente mencionaríamos os seguintes recursos comerciais:

## A capacidade de navegar pelos produtos usando um navegador da Web padrão

## A capacidade de pesquisar produtos e visualizar detalhes do produto

## Ler as avaliações de cada produto deixadas pelos clientes que o compraram

## Adicione o produto ao carrinho de compras

## Faça um pedido para esse produto

## Receba-o em seu endereço



Também precisamos da capacidade de atualizar e manter o estoque de produtos, tanto da perspectiva do cliente ao comprar um produto quanto da perspectiva do comerciante que atende ao pedido. Portanto, se mapearmos esses recursos comerciais essenciais para microsserviços, teremos o seguinte design.







Mas como podemos saber se esses serviços seguem nossos três princípios fundamentais? Bem, em primeiro lugar, apenas observando os nomes dos serviços, já podemos ver que esse design segue o princípio da responsabilidade única, e isso é intencional, porque cada serviço é responsável por um recurso comercial inteiro.



Também podemos verificar facilmente se cada serviço é coeso, considerando as alterações que precisam ser feitas em nosso sistema. Se quisermos estender uma funcionalidade específica, por exemplo, se quisermos adicionar novos produtos ou atributos a produtos existentes, o único lugar que precisaremos alterar além da interface do usuário será o serviço do produto, mas os outros serviços permanecerão intocados. Da mesma forma, se quisermos definir novas políticas ou recursos para a forma como os usuários vivem ou filtram as avaliações, o único serviço que precisa ser atualizado é o serviço de avaliação.



E se quisermos alterar a empresa terceirizada de processamento de cartões de crédito com a qual trabalhamos ou adicionar um novo tipo de pagamento aceito, o único serviço que precisaremos atualizar é o serviço de pedidos.



Também podemos verificar se esses serviços não são muito interdependentes e estão fracamente acoplados, analisando algumas jornadas de usuários ou casos de uso. Por exemplo, quando um usuário deseja carregar nossa loja on-line, essa solicitação pode ser atendida pelo serviço de aplicativo Web.  Quando um usuário deseja pesquisar um produto ou visualizar um produto específico, essa solicitação pode ser atendida pelo serviço de produtos. Para ver as avaliações do produto, só precisamos envolver o serviço de avaliação, fazer um pedido e enviar o produto.



Os únicos serviços envolvidos são o serviço de pedidos, o serviço de estoque e o serviço de remessa, respectivamente, em que cada um cuida de uma parte claramente definida da transação.







Agora vamos discutir outra maneira de decompor um aplicativo monolítico em microsserviços.  Essa técnica é chamada de composição por domínio ou subdomínio. Diferentemente da técnica anterior, que analisa o sistema apenas do ponto de vista comercial. Nessa técnica, adotamos o ponto de vista do desenvolvedor do sistema. Em outras palavras, os critérios para definir os limites dos subdomínios baseiam-se no entendimento que o engenheiro tem do sistema, e é por isso que geralmente é mais intuitivo. Nesse método, decompomos o sistema em pequenos subdomínios, onde cada subdomínio é definido como uma esfera de conhecimento, influência ou atividade.



Esses subdomínios podem ser de três tipos.

Um domínio que representa um recurso comercial essencial.

Um domínio que oferece suporte a uma capacidade de negócios e um subdomínio genérico.

Um recurso comercial essencial é o principal diferencial de nossa empresa em relação a qualquer outro concorrente no setor.



Trata-se de um recurso que não pode ser comprado no mercado ou terceirizado. É onde colocamos nosso melhor esforço e investimento. Sem isso, nosso negócio não agrega valor.



Um subdomínio de suporte ainda é essencial para a operação de nossos negócios e apoia a entrega de nossos domínios principais. Mas isso não é algo que nos diferencia de nossos concorrentes. Um subdomínio genérico é um recurso que não é específico de nenhuma empresa. Muitas outras empresas o utilizam e, em muitos casos, podemos até obter esse componente da prateleira. Essa categorização de subdomínios nos ajuda a priorizar o investimento em cada subdomínio. Também pode nos ajudar a descobrir onde queremos alocar nossos melhores e mais experientes engenheiros e onde podemos economizar tempo ou custos e obter soluções já existentes.



Voltando ao exemplo de nossa loja on-line, o subdomínio principal é claramente o catálogo de produtos. Por quê? Bem, porque se formos a qualquer outra loja on-line, não veremos os mesmos produtos nem teremos a mesma experiência. É por isso que nossa loja on-line é única em relação a qualquer outra existente. Para apoiar a capacidade de vender esses produtos em nossa loja, temos os subdomínios de pedidos, estoque e remessa. Sem eles, não podemos vender produtos. Mas eles podem ser semelhantes em termos de funcionalidade a outras lojas on-line. Por fim, temos as análises, os pagamentos, a pesquisa de imagens, a compactação de imagens, a segurança e a interface do usuário da Web.



Subdomínios que são subdomínios genéricos. Esses subdomínios ainda são essenciais, mas são muito genéricos porque muitas outras empresas, nem mesmo as lojas on-line, precisam e usam esses subdomínios. Também podemos nos livrar facilmente do uso de implementações prontas desses componentes. Depois de identificarmos esses subdomínios, temos algumas opções. Podemos dedicar um microsserviço separado para cada subdomínio ou, se percebermos que determinados subdomínios estão muito acoplados uns aos outros ou não são coesos o suficiente, podemos agrupar vários subdomínios em um único microsserviço. Por exemplo, se percebermos que o serviço de imagem do produto e a compactação de imagem são muito interdependentes, podemos agrupar os dois no mesmo microsserviço. Ou se, no início, percebermos que o serviço de pagamento não tem lógica suficiente para justificar um serviço separado ou que está muito fortemente acoplado ao serviço de pedidos, também poderemos agrupá-los em um único microsserviço.



É claro que isso não é definitivo e, se depois de um tempo percebermos que agora faz mais sentido separá-los, sempre poderemos fazer isso. E o tamanho reduzido desses microsserviços permite que essas migrações ocorram com muita facilidade e rapidez. Como observação adicional, esses dois métodos de definição dos limites dos microsserviços não são os únicos. Alguns outros métodos incluem a composição por ação em ou entidades. No entanto, definir os limites por recursos comerciais ou subdomínios é a maneira mais popular e fácil de fazer isso. Portanto, agora que aprendemos as duas principais técnicas para dividir um aplicativo monolítico existente em microsserviços, vamos compará-las lado a lado.





De modo geral, a primeira técnica de decomposição por capacidade de negócios geralmente produz serviços mais coesos e pouco acoplados do que a composição por subdomínio. Por outro lado, a arquitetura de microsserviços que obtemos com a decomposição por capacidade de negócios geralmente é mais granular, o que significa microsserviços maiores. E quando decompomos por subdomínio, tendemos a obter uma arquitetura de microsserviços mais refinada, o que significa microsserviços menores.



A arquitetura que recebemos do posicionamento por recursos comerciais geralmente é muito mais estável. E isso se deve ao fato de que o negócio principal geralmente é muito mais estável do que a engenharia e a tecnologia. Por outro lado, a composição por recursos comerciais exige um entendimento muito melhor do negócio. Isso significa que esse processo produzirá um design menos intuitivo para os engenheiros do que a composição por subdomínio.



Antes de concluirmos, há alguns pontos que gostaria de destacar. Primeiro, é importante entender que não há uma maneira correta de definir os limites dos microsserviços, e o que funciona bem no momento pode não funcionar tão bem no futuro. Portanto, a arquitetura continua evoluindo à medida que novos recursos chegam e novos recursos comerciais são adicionados. Também não há decomposição perfeita em microsserviços, e algum atrito ou acoplamento é inevitável. Portanto, o objetivo de definir os limites corretamente é minimizar esse atrito e não eliminá-lo completamente.



Por fim, as técnicas que aprendemos neste capítulo não são infalíveis.Elas são apenas diretrizes ou ferramentas para nos ajudar a chegar a uma boa arquitetura. No entanto, ele não substitui o bom julgamento e a intuição da engenharia. Neste capítulo, aprenderemos duas maneiras de decompor um aplicativo monolítico em microsserviços. A primeira maneira foi por recursos de negócios, e a segunda foi por subdomínio. Na segunda técnica, definimos três tipos de subdomínios. Subdomínios principais, subdomínios de suporte e subdomínios genéricos. O uso de qualquer uma dessas técnicas nos ajudou a definir os limites dos microsserviços. Por fim, mencionamos que nenhuma dessas técnicas é totalmente suficiente para garantir uma migração perfeita para microsserviços, e sempre é necessário algum julgamento de engenharia para fazer o design final.





## Migração para Microsserviços - Passos, Dicas e Padrões



Neste capítulo, aprenderemos a realizar a migração real de um grande aplicativo monolítico legado para microsserviços. Primeiro, falaremos sobre onde começar a migração para garantir que ela não seja descarrilada ou abandonada. Depois disso, discutiremos como se preparar para a migração. Em seguida, falaremos sobre como executar a migração usando o padrão strangler fig. E concluiremos com uma dica importante para garantir que não tenhamos problemas ao realizar a migração.



Supondo que tenhamos uma base de código muito grande que desejamos modernizar e migrar para microsserviços. Por onde podemos começar?

## Etapas para migrações:

## Adicionar/garantir cobertura de teste de código

## Definir API de componente

## Isolar o componente removendo interdependências para o resto do aplicativo



A abordagem mais comum que os desenvolvedores pensam é a abordagem big bang. Nessa abordagem, a equipe mapeia os limites desejados para a futura arquitetura de microsserviços e, em seguida, tenta obter a adesão da gerência para interromper o desenvolvimento de qualquer recurso e se concentrar totalmente na migração na superfície. Parece uma boa ideia, mas se toda a equipe se concentrar totalmente na migração e não se distrair com o desenvolvimento de novos recursos, ela poderá concluí-la muito mais rapidamente.



Pelo menos essa é a teoria. No entanto, essa abordagem é, na verdade, a pior em termos de produtividade e impacto nos negócios. E vamos ver por quê. Em primeiro lugar, ter muitos desenvolvedores trabalhando no mesmo projeto, que, neste caso, é a refatoração do monólito para microsserviços, é uma má ideia. Lembre-se de que queremos migrar para microsserviços principalmente porque nossa equipe já tem problemas de produtividade e comunicação, que é o que chamamos de escalabilidade organizacional.



Portanto, ter muitos cozinheiros na cozinha para um projeto tão grande criará muito atrito. O segundo motivo é que estimar o esforço para um projeto tão grande é muito difícil. E, assim como no caso de muitos projetos grandes e ambíguos, muitas vezes nos deparamos com problemas técnicos que não  havíamos previsto. Portanto, se prometermos aos nossos gerentes concluir a migração em quatro meses e ainda não tivermos terminado, cinco meses depois, os gerentes começarão a ficar nervosos.



Isso coloca todo o processo em risco de abandono. Para minimizar a perda de tempo adicional, finalmente, interromper o desenvolvimento de novos recursos por muitos meses pode ser muito prejudicial para os negócios. Os gerentes de produto podem ficar entediados e não ter como ser promovidos, o que, por sua vez, pode levá-los a deixar a empresa.



Os vendedores não têm nada para vender ou apresentar a novos clientes, e os usuários que realmente não estão nem aí para nossa arquitetura interna podem começar a pensar que nosso negócio está com problemas ou que nossa empresa não está disposta a continuar melhorando sua experiência. Portanto, a melhor abordagem é incremental e contínua. Nessa abordagem, identificamos os componentes em nossa base de código que podem se beneficiar mais da migração para um microsserviço separado.



Os melhores candidatos para a migração, classificados de acordo com o benefício que obtemos ao migrá-los, são as seguintes áreas com maior desenvolvimento e mudanças frequentes. Componentes que têm requisitos de alta escalabilidade que não podem ser atendidos enquanto fizerem parte do grande aplicativo monolítico. E, por fim, os componentes com muito pouco débito técnico e boa separação lógica que se encaixam no escopo de um microsserviço.



Preferimos migrar o código com mais desenvolvimento, porque migrar o código que ninguém toca não nos traz nenhum valor, pois não é a fonte do nosso problema. Por outro lado, a lógica que está em constante evolução é a maior fonte de conflitos de mesclagem. É também o maior contribuinte para as versões de todo o nosso aplicativo monolítico. Portanto, se o separarmos em um microsserviço, essas alterações não exigirão que reimplantemos uma nova versão do nosso código.



A separação dessas partes do código em um microsserviço separado nos ajudará a desvincular sua lógica comercial do restante do aplicativo, o que facilita muito o raciocínio e diminui a probabilidade de introdução. Depois que migramos essa parte do código para um microsserviço, identificamos o próximo candidato e continuamos continuamente até chegarmos a um ponto em que o monólito original tenha desaparecido. Ou o que resta nesse aplicativo monolítico nunca muda. Portanto, não vale a pena tocar mais no assunto.



Essa abordagem incremental tem vários benefícios importantes. Primeiro, não precisamos estabelecer prazos rígidos para concluir a migração, mesmo que leve um ano ou mais para chegar ao ponto final. Estamos constantemente fazendo progressos visíveis e mensuráveis. Nossos negócios também não serão interrompidos e, mesmo que a migração de uma parte de nosso código exceda as estimativas, será da ordem de dias ou semanas, e não de meses ou anos.



Agora vamos falar sobre como se preparar para a migração. Depois de identificar o componente ou os componentes que queremos migrar, precisamos garantir que tenhamos uma boa cobertura de teste. Essa etapa é fundamental porque, com uma boa cobertura de código, temos a confiança de que não quebramos nenhuma funcionalidade durante a refatoração. Caso contrário, toda a migração poderá ser atrasada se as coisas começarem a quebrar.  Quando tivermos uma boa cobertura de testes, é importante definir uma API clara e bem pensada para o componente que planejamos migrar e, na última etapa, também queremos isolar o componente removendo todas as interdependências com o restante do aplicativo.



Por fim, vamos falar sobre como executar a migração real e aprender sobre um padrão muito popular, chamado de padrão Strangler Fig.







O padrão Strangler Fig introduzido por Martin Fowler é inspirado em uma planta que começa como uma pequena videira que cresce no topo e ao lado de uma árvore velha existente. E, com o tempo, ela se espalha e cresce, consumindo completamente a árvore antiga que ocupa seu lugar. A ideia por trás desse padrão é primeiro introduzir um proxy na frente do aplicativo legado monolítico. Ele simplesmente permite a passagem de solicitações. Esse proxy é comumente chamado de fachada Strangler e normalmente é implementado usando um gateway de API.



Se você não estiver familiarizado com um gateway de API, ele é um componente de código aberto ou baseado em nuvem que roteia as solicitações com base na API a que se destinam.



Depois que o microsserviço recém-criado tiver sido completamente testado e implantado, desviamos o tráfego para essa API do aplicativo monolítico e o enviamos para o microsserviço recém-criado. Essa alteração ocorre de forma totalmente transparente para os usuários e minimiza o risco de problemas durante a migração.



Depois de monitorar o desempenho e a funcionalidade do novo microsserviço por algum tempo, podemos remover o componente antigo com a mesma funcionalidade dentro do aplicativo monolítico. Em seguida, repetimos as mesmas etapas com o novo microsserviço até ficarmos com um aplicativo antigo vazio ou com um aplicativo legado para dar suporte a clientes antigos.



Antes de concluirmos, gostaria de abordar uma última dica para garantir uma migração tranquila e sem bugs. Ao migrar um aplicativo monolítico antigo para uma arquitetura de microsserviço nova e moderna, é difícil conter a empolgação e começar a usar tecnologias e linguagens de programação mais novas imediatamente. No entanto, a melhor abordagem, ao migrar para uma nova arquitetura, é manter o código e a pilha de tecnologia inalterados o máximo possível. O motivo disso é que cada alteração adicional que fazemos é uma fonte potencial de um bug, e a migração em si já é complexa e arriscada o suficiente. Portanto, não queremos acrescentar ainda mais fatores de risco ao processo. Quando a migração estiver concluída e o novo microsserviço estiver em execução e estável, poderemos começar a refatorá-lo facilmente para usar tecnologias mais novas, se necessário.



Neste capítulo, aprenderemos a preparar e executar a migração de um grande aplicativo monolítico para microsserviços.



Primeiro, aprendemos a identificar os componentes que podem ser os melhores candidatos. Datas para a migração. Esses candidatos incluíam áreas que mudavam com mais frequência, exigiam maior escalabilidade ou tinham a menor quantidade de dívida técnica.



Em seguida, discutimos o processo de preparação e execução da migração, que envolveu a adição de cobertura de teste, a definição da API, o isolamento dos componentes do restante do aplicativo e, por fim, o uso do padrão strangler fig para fragmentar as diferentes partes do monólito e migrá-las para microsserviços implantados e gerenciados separadamente.



## Bancos de dados em arquitetura de microsserviços



Nesta seção, exploraremos os princípios fundamentais e as práticas recomendadas para o uso de bancos de dados em arquitetura de microsserviços. Seguindo essas diretrizes, você maximizará os benefícios dos microsserviços e minimizará problemas relacionados à escalabilidade e manutenção.



Essas recomendações são baseadas em experiências acumuladas por arquitetos de software e líderes técnicos que lidam com sistemas em larga escala. Vamos discutir o princípio do banco de dados por microsserviço, sua importância e seus impactos.



Esses princípios e práticas recomendadas vêm de anos de experiência compartilhada por arquitetos de software e líderes técnicos que executam sistemas de grande escala usando microsserviços. Falaremos sobre o primeiro princípio e a prática recomendada do banco de dados por microsserviço.



Então, primeiro, vamos ver o que significa esse princípio de banco de dados por microsserviço e por que ele é tão importante. Vamos considerar a arquitetura de uma companhia de seguros que segue a arquitetura tradicional de três camadas. Nessa arquitetura, temos um aplicativo monolítico na camada intermediária e um banco de dados na camada de dados para aumentar a escalabilidade organizacional.



Migramos esse aplicativo monolítico para um conjunto de microsserviços com uma equipe separada responsável por cada microsserviço. Supondo que definamos corretamente os limites desses microsserviços, devemos esperar que as equipes operem de forma independente com muito pouco atrito. Permitir que os diferentes microsserviços compartilhem dados faz todo o sentido. Por exemplo, o serviço de relatórios precisa acessar os dados de compra de apólices, os dados de sinistros e os dados dos clientes, de modo que podemos tornar as solicitações muito mais eficientes permitindo que o serviço de relatórios acesse esses dados diretamente do banco de dados, em vez de pagar a sobrecarga de desempenho para obter os mesmos dados por meio dos serviços apropriados.



No entanto, com essa otimização de desempenho aparentemente lógica, temos um problema. Por exemplo, o serviço de compra de apólices recebe muito tráfego de possíveis compradores de apólices, portanto, a equipe proprietária desse serviço decidiu aproveitar sua autonomia e substituir seu lento banco de dados relacional legado por um banco de dados NoSQL otimizado e de leitura. No entanto, como o código do serviço de relatórios está fortemente acoplado à tecnologia de banco de dados, onde os dados de compra de apólices são armazenados, as alterações devem ocorrer em ambas as bases de código e ser liberadas simultaneamente.



Da mesma forma, a equipe proprietária do serviço de reclamações decidiu alterar o esquema da tabela de reclamações renomeando algumas colunas, removendo algumas colunas antigas e não utilizadas e adicionando novas colunas. Agora, como o serviço de relatórios depende desse esquema antigo, essas duas equipes terão de se reunir e discutir o novo esquema que funcione para ambas e, novamente, fazer essas alterações nas duas bases de código e lançá-las simultaneamente.



Por fim, a equipe proprietária do serviço de atendimento ao cliente decidiu adicionar uma grande quantidade de segurança refinada em relação aos dados do usuário que podem ser lidos ou modificados com base em diferentes funções organizacionais. No entanto, essas políticas de segurança estão fora do escopo do domínio da equipe de serviços de relatórios, portanto, a equipe de atendimento ao cliente terá que comunicar essas alterações, incluindo todos os detalhes de implementação para a equipe de serviços de relatórios. E, mais uma vez, ambas as equipes devem alterar sua base de código, escrever seus próprios testes e, simultaneamente, liberar e monitorar essas alterações.



Portanto, como podemos ver, apesar de todo o esforço de migração, nossas equipes ainda estão fortemente acopladas e exigem muita comunicação e coordenação, o que está afetando negativamente a produtividade e a velocidade de desenvolvimento da organização. É aqui que entra o princípio do banco de dados por microsserviço.



Com esse princípio, cada equipe de microsserviço é totalmente proprietária de seus dados e não os expõe diretamente a nenhum outro serviço, mesmo ao custo de latência adicional.



Sempre que um determinado serviço requer dados de outro serviço. A solicitação deve passar pela API do serviço de destino. Além disso, cada serviço precisa abstrair a tecnologia ou a estrutura real do banco de dados no nível da API.



Dessa forma, se a equipe proprietária desse microsserviço decidir alterar o banco de dados, a tecnologia ou o esquema, essa alteração será totalmente transparente para os consumidores de sua API.



Além disso, se as alterações também exigirem algumas mudanças em sua API, sempre poderemos oferecer duas versões da API por algumas semanas ou até meses. Isso permite que as outras equipes tenham tempo suficiente para fazer suas alterações e atualizar para a nova API sem a necessidade de qualquer coordenação.







Portanto, agora que entendemos a motivação do princípio de banco de dados por microsserviço e os benefícios que ele nos proporciona se o seguirmos, vamos falar sobre algumas desvantagens e repercussões.



A primeira desvantagem óbvia que já mencionamos é a latência adicional. Envio de uma solicitação de rede para outro serviço:

Analisar a solicitação.

Consultar o banco de dados.

Enviá-la de volta e analisar a resposta definitivamente adiciona uma sobrecarga de desempenho em comparação com uma simples consulta ao banco de dados diretamente.



## Desvantagens:

## Adicionou latência

## Nenhuma operação "Join"

## Nenhum suporte para transações



Quando essa sobrecarga de desempenho se torna um problema, não há problema em armazenar em cache ou até mesmo armazenar alguns dos dados que pertencem a outro microsserviço no banco de dados, que pertence ao microsserviço que precisa desses dados.



No entanto, é importante garantir que a fonte da verdade continue sendo o único microsserviço. Se armazenarmos em cache ou armazenarmos dados que pertençam a um microsserviço diferente, é claro que perderemos a consistência estrita e teremos que nos contentar com a consistência eventual (Teorema CAP). E isso ocorre porque os dados que armazenamos localmente podem estar obsoletos até que obtenhamos os novos dados da fonte da verdade.



A próxima desvantagem é a perda da capacidade de unir dados de várias tabelas quando todos os dados eram representados como tabelas no mesmo banco de dados. Poderíamos facilmente realizar as operações conjuntas com base em uma chave ou coluna comum. Quando dividimos esses dados em diferentes bancos de dados, alguns dos quais podem nem mesmo ser bancos de dados relacionais. Não podemos mais realizar essas operações de união. A única maneira de obter a mesma funcionalidade seria extrair dados de dois bancos de dados diferentes, transformar os dados para que ambos os objetos sejam representados no mesmo formato e, em seguida, realizar essa união de forma programática.



A próxima desvantagem é a perda de garantias de transação. Voltando a um único banco de dados, poderíamos modificar linhas em várias tabelas como parte de uma única transação e garantir que a alteração em todas essas tabelas seria atômica.



Realizar uma transação distribuída em vários serviços é muito difícil. Portanto, embora seja teoricamente possível, quase nunca é usado. Mas não se preocupe. Mais adiante, ofereceremos alguns padrões que podem resolver todos esses desafios com muita eficiência.



Neste capítulo, aprenderemos sobre um princípio muito importante e uma prática recomendada para a arquitetura de microsserviços, o banco de dados por microsserviço.



Primeiro, obtivemos a motivação para esse princípio explorando um cenário da vida real nesse cenário. Vimos que o compartilhamento de um banco de dados entre microsserviços une fortemente seus pares, suas bases de código e suas equipes, causando muita sobrecarga de coordenação.



Essa sobrecarga é eliminada quando cada microsserviço possui seus próprios dados e os expõe somente por meio de uma API de abstração.



Por fim, mencionamos os desafios e as desvantagens de usar o princípio de banco de dados por microsserviço. Esses desafios incluem pior desempenho, operações de junção mais complexas e a perda de garantias de transação.



## Resumo deste capítulo:



## O Princípio do Banco de Dados por Microsserviço

O princípio do banco de dados por microsserviço estabelece que cada microsserviço é responsável por seus próprios dados, sem expô-los diretamente a outros microsserviços. Essa abordagem promove autonomia das equipes e reduz o acoplamento, mesmo que introduza alguma latência adicional.

## Exemplo: Transição de Monolítico para Microsserviços

Considere uma companhia de seguros com uma arquitetura monolítica de três camadas. A migração para microsserviços implica dividir o sistema em serviços menores, cada um gerenciado por uma equipe dedicada. Idealmente, as equipes devem operar de forma independente. No entanto, permitir que diferentes microsserviços compartilhem dados diretamente do banco pode parecer eficiente, mas cria problemas de acoplamento e coordenação.

## Problemas de Acoplamento:

## Alterar tecnologias ou esquemas de banco de dados:

Se um serviço altera seu banco de dados, outros serviços que dependem desse banco precisam ajustar suas bases de código.

## Coordenação entre equipes:

Alterar esquemas ou implementar novas regras exige comunicação constante entre as equipes, afetando a agilidade organizacional.

## Políticas de segurança complexas:

Implementar regras refinadas de acesso em dados compartilhados complica a gestão e aumenta o risco de erros.

## Benefícios do Banco de Dados por Microsserviço:

Adotar o princípio de um banco de dados dedicado por serviço resolve esses problemas ao:

Garantir que cada serviço possua controle total sobre seus dados.

Prover acesso aos dados apenas via APIs, abstraindo detalhes de implementação.

Permitir atualizações independentes na API, possibilitando convivência de versões diferentes por períodos de transição.



## Desafios do Princípio

## Embora vantajoso, o princípio apresenta alguns desafios:

## Latência adicional:

Consultas que antes eram diretas ao banco agora envolvem solicitações de rede, processamento de APIs e respostas, aumentando o tempo de execução.

## Perda de operações “JOIN”:

A separação de dados entre bancos impede a realização de junções diretas, exigindo soluções programáticas para combinar dados de fontes diferentes.

## Ausência de transações globais:

Garantias atômicas em múltiplos bancos são complexas. Embora transações distribuídas sejam possíveis, raramente são viáveis devido à sua complexidade e custo.



## Soluções Alternativas:

## Cache ou Armazenamento Local:

Microsserviços podem armazenar localmente dados de outro serviço, mas devem garantir que a fonte da verdade permaneça no serviço original. Isso implica aceitar consistência eventual em vez de consistência estrita.

## Padrões Avançados:

Usar padrões como CQRS (Command Query Responsibility Segregation) e Event Sourcing pode mitigar os desafios de desempenho e integração entre serviços.



## Conclusão

O princípio do banco de dados por microsserviço promove autonomia, desacoplamento e agilidade no desenvolvimento de software. Apesar dos desafios de desempenho, junções e transações, esses problemas podem ser mitigados por meio de boas práticas e soluções arquiteturais.

Ao aplicar essas práticas, você criará sistemas mais escaláveis, resilientes e adaptáveis às demandas de negócios dinâmicos e distribuídos.







## O Princípio DRY em Microsserviços e Bibliotecas Compartilhadas



Neste capítulo, revisitaremos o princípio "DRY ou não se repetir" no contexto dos microsserviços. Primeiro, vamos relembrar rapidamente o que o princípio significa e por que ele é tão importante. Em seguida, discutiremos os desafios de seguir esse princípio na arquitetura de microsserviços. Depois disso, discutiremos algumas alternativas às bibliotecas compartilhadas. E, por fim, concluiremos com uma breve discussão sobre o compartilhamento e a duplicação de dados em diferentes microsserviços. Portanto, vamos começar com um rápido lembrete do princípio DRY e sua importância.



De modo geral, o DRY é um dos princípios mais fundamentais da engenharia de software. Se você se encontrar repetindo a mesma lógica ou os mesmos dados, deve sempre consolidá-los em um único local como um método, uma classe ou uma variável compartilhada. Em um escopo mais amplo, se você tiver uma lógica mais complexa usada em vários projetos ou aplicativos, é uma prática comum empacotar essa lógica em uma biblioteca compartilhada que outros aplicativos possam importar e usar.



Dessa forma, se precisarmos alterar essa lógica, poderemos fazê-lo em um único lugar e não precisaremos procurar duplicatas em várias bases de código. Ele também reduz a duplicação de esforços, de modo que o trabalho de um único engenheiro pode ser reutilizado por outros. No entanto, o princípio DRY nem sempre é verdadeiro na arquitetura de microsserviços, principalmente no que diz respeito às bibliotecas compartilhadas.



Então, vamos falar sobre alguns motivos pelos quais as bibliotecas compartilhadas podem ser um grande problema nos microsserviços. O primeiro problema é o acoplamento estreito. Como lembrete, um dos princípios fundamentais do microsserviço era o acoplamento frouxo (baixo acoplamento). No entanto, quando vários microsserviços compartilham e dependem da mesma biblioteca, as alterações nessa biblioteca se tornam uma fonte de forte acoplamento e atrito entre os diferentes microsserviços e os proprietários dessa biblioteca.



Se houver alterações na API dessa biblioteca, essas alterações precisarão ser comunicadas às outras equipes que possuem esses microsserviços. Em seguida, essas equipes terão que fazer as alterações apropriadas em sua base de código para que possam continuar usando essa biblioteca.



Mas, mesmo que a API não mude, os microsserviços ainda precisarão ser reconstruídos, testados novamente e reimplantados a cada alteração na biblioteca compartilhada. Além disso, um bug ou uma vulnerabilidade nessa biblioteca compartilhada pode afetar todos os serviços que a utilizam, o que anula o objetivo de isolar esses microsserviços como unidades de tempo de execução separadas.



Outro problema ao usar uma biblioteca compartilhada é comumente chamado de inferno de dependências (Dependency Hell). Vamos considerar uma situação em que um determinado microsserviço usa uma biblioteca compartilhada.

Biblioteca A: essa biblioteca usa internamente outra biblioteca, a Biblioteca B;

Além disso, o microsserviço está usando a biblioteca B diretamente em outra parte de sua base de código para uma finalidade diferente.

Vamos supor também que o microsserviço e a Biblioteca A estejam usando a mesma versão da Biblioteca B em um determinado momento.







Agora vamos imaginar que uma nova e importante atualização foi feita na Biblioteca A, da qual nosso microsserviço precisa com urgência. No entanto, a nova versão da Biblioteca A agora depende de outra versão mais recente da Biblioteca B do que a que estamos usando diretamente. Dependendo da linguagem de programação e do tempo de execução que estivermos usando, em alguns casos, não poderemos depender de duas versões da mesma biblioteca simultaneamente. Se esse for o caso, seremos forçados a fazer uma alteração desnecessária no código em que estamos usando a biblioteca B diretamente apenas para podermos atualizar para uma nova versão da biblioteca A. Em outros casos em que podemos depender de duas versões diferentes da mesma biblioteca e carregá-las, estamos basicamente quebrando o princípio DRY. E isso ocorre porque nosso aplicativo de microsserviço agora precisa carregar duas versões da mesma biblioteca em que a maior parte do código é idêntica.

## Desafios das bibliotecas compartilhadas:

## Acoplamento rígido

## Toda mudança requer:

## Reconstrução

## Reteste

## Reimplantação

## Bug/vulnerabilidade em um compartilhamento afeta todos os microsserviços

## "Inferno da dependência" (Dependency Hell)



Outra desvantagem disso é que também aumenta o tamanho do nosso binário e o tempo necessário para criá-lo e testá-lo.



Portanto, agora que entendemos os problemas das bibliotecas compartilhadas e os desafios decorrentes do princípio DRY e dos microsserviços, vamos falar sobre algumas alternativas que podemos usar.



O primeiro cenário que discutiremos é quando a lógica comercial complexa é compartilhada entre vários microsserviços. Essa situação pode indicar que definimos incorretamente os limites entre esses dois microsserviços. Lembre-se de que um dos princípios fundamentais dos microsserviços é o princípio da responsabilidade única. Portanto, se seguíssemos a decomposição por capacidade de negócios ou subdomínio, muito raramente chegaríamos a essa situação. E, se o fizermos, talvez devamos considerar a reavaliação desses limites. Portanto, uma opção seria ajustar os limites desses dois microsserviços. Portanto, apenas um deles contém essa lógica comercial e o outro não.



Outra opção é, se essa lógica comercial for complexa o suficiente, separá-la em seu próprio microsserviço.



Outra situação é quando precisamos compartilhar modelos de dados comuns para a comunicação entre dois microsserviços. Nesse caso, ter bibliotecas ou arquivos compartilhados é, na verdade, uma boa prática. O motivo disso é que, quando se trata de comunicação entre dois microsserviços, na verdade queremos que as duas equipes e bases de código sejam codependentes. Se a API ou o modelo de dados de um microsserviço mudar a ponto de não conseguir se comunicar. Na verdade, queremos interromper os testes o mais rápido possível. Caso contrário, se não compartilharmos, mas duplicarmos esse código, os testes de cada microsserviço poderão ser aprovados com êxito e não detectar a alteração no outro microsserviço. Portanto, esses dois serviços podem não ser capazes de se comunicar em tempo de execução e só descobriremos isso na produção.



Outra abordagem para esse problema é usar ferramentas de geração de código baseadas em modelos ou esquemas de dados. Nesse caso, temos um esquema compartilhado que representa o modelo de dados comum para a comunicação entre os dois microsserviços. Dependendo do tipo de linguagem ou tecnologia de API, podemos usar a ferramenta apropriada para gerar os modelos de dados correspondentes e o código padrão para a comunicação entre os microsserviços. Desde que o código seja gerado com base em uma definição de interface compartilhada e que a geração seja realizada como parte do processo de compilação e teste, essa é uma abordagem muito comum e segura quando se trata de outros códigos, como métodos utilitários que mudam com frequência. É melhor duplicá-lo em diferentes microsserviços em vez de tentar reutilizá-lo em uma biblioteca compartilhada.



Dessa forma, cada microsserviço pode ter sua própria implementação mais específica dessa lógica otimizada para seu próprio caso de uso. Isso também facilita a migração de toda a base de código de um microsserviço para outra linguagem de programação, se quisermos.



Agora, se não quisermos absolutamente duplicar um código específico, temos duas opções adicionais.



A primeira opção é usar o Sidecar Pattern. Usando esse padrão, empacotamos e implantamos a funcionalidade compartilhada como um processo separado.  Mas, em vez de executá-lo como um serviço separado, executamos esse processo nos mesmos hosts que as instâncias do microsserviço. Dessa forma, podemos compartilhar a mesma funcionalidade em várias instâncias do mesmo microsserviço e em várias instâncias de diferentes microsserviços. A instância do microsserviço pode se comunicar com seu processo Sidecar co-localizado usando os protocolos de rede padrão e conhecidos. Como o processo Sidecar e o processo de microsserviço estão sendo executados no mesmo host. A sobrecarga de desempenho dessa comunicação é relativamente menor do que se executássemos nos processadores em hosts diferentes.

## Nota:

O Sidecar Pattern é um padrão arquitetural utilizado principalmente em sistemas baseados em microsserviços. Ele consiste em acoplar um contêiner ou processo auxiliar (o sidecar) a um serviço principal para fornecer funcionalidades complementares, sem modificar diretamente o código do serviço. Como funciona: O sidecar é executado em paralelo ao serviço principal e é implantado junto a ele (geralmente no mesmo pod, se for no Kubernetes). Ele opera como uma extensão ou auxiliar do serviço principal, compartilhando o mesmo ciclo de vida e recursos (rede, armazenamento, etc.).
(Ver estudo no outro doc)


Por outro lado, essa sobrecarga ainda é maior do que se executássemos essa lógica como uma biblioteca compartilhada dentro do processo do microsserviço. Como segunda opção, nos raros casos em que temos um código muito genérico e estável que raramente muda, como registro, repetição e correspondência de padrões, não há problema em usar bibliotecas compartilhadas, desde que elas não nos levem a esse inferno de dependências (dependency hell). Essas bibliotecas devem ser tão autônomas e independentes umas das outras quanto possível. Mas isso deve ser usado como último recurso.



Como observação final, dentro da base de código de cada microsserviço individual, ainda devemos seguir o princípio DRY como de costume. A duplicação de código em um microsserviço é inaceitável e devemos sempre extrair a lógica comum em uma única classe ou módulo de método.

## ‘

Agora vamos mudar de marcha e falar sobre a duplicação de dados. Duplicar os mesmos dados nos microsserviços e armazená-los em bancos de dados pode parecer um desperdício de espaço de armazenamento. Entretanto, como já vimos na aula anterior, às vezes é necessário melhorar o desempenho se não quisermos pagar o preço de enviar uma solicitação de dados a outro serviço, então podemos armazenar um cache desses dados dentro do nosso microsserviço.



Na arquitetura de microsserviços, essa abordagem é totalmente aceitável, desde que nos lembremos de duas coisas. A primeira é que apenas um dos microsserviços precisa ser claramente o proprietário e a fonte da verdade para esses dados. Isso significa que apenas um microsserviço pode obter, gravar, atualizar ou excluir operações desses dados, e os outros microsserviços que contêm uma cópia desses dados recebem apenas operações de leitura.



A segunda coisa a entender, que também mencionamos no capítulo anterior, é que, quando duplicamos os dados entre os microsserviços, podemos garantir apenas a consistência eventual. Portanto, em situações em que a consistência rigorosa é importante, a duplicação de dados deve ser evitada.



Por exemplo, no caso de uma loja on-line, talvez queiramos armazenar a classificação ou até mesmo algumas avaliações recentes de um produto em seu serviço de produtos. Dessa forma, quando um usuário quiser ver um produto, poderemos carregar rapidamente esses dados do serviço de produtos e não precisaremos esperar para carregar todas essas avaliações e classificações comunicando-nos com o serviço de avaliação. No entanto, se fizermos isso, poderemos estar em uma situação em que nossa classificação para um determinado produto não seja a mais precisa, e as avaliações exibidas na seção de avaliações recentes poderão não ser mais as mais recentes para um usuário que esteja pensando em comprar esse produto.



Essa imprecisão não é tão importante e a consistência eventual é totalmente aceitável. Por outro lado, quando se trata das informações mais atualizadas sobre o estoque de um determinado produto ou o saldo da conta de um determinado usuário, precisamos garantir uma consistência rigorosa. Nesse caso, não duplicaríamos esses dados em nenhum outro serviço que não fosse o proprietário.



Neste capítulo, revisitamos o princípio DRY para o compartilhamento de bibliotecas e dados na arquitetura de microsserviços.



Primeiro, analisamos os benefícios de seguir esse princípio em geral e aprendemos que ele nem sempre se aplica à arquitetura de microsserviços.



Em seguida, mencionamos alguns dos desafios do compartilhamento de uma biblioteca entre os microsserviços, que incluíam o acoplamento rígido, a necessidade de reconstruir, testar novamente e reimplantar todos os microsserviços a cada alteração na biblioteca e o inferno de dependências (dependecy hell).



Depois disso, aprenderemos algumas alternativas às bibliotecas compartilhadas, como separar a lógica de negócios complexa em um novo microsserviço usando o padrão sidecar de geração de código e duplicando alguns códigos nos microsserviços.



E, por fim, falamos sobre a duplicação de dados em microsserviços e aprendemos que, às vezes, isso é inevitável e totalmente aceitável por motivos de desempenho. Lembre-se de que a consistência de nossos dados será afetada e também é importante lembrar que apenas um microsserviço precisa continuar sendo o proprietário claro de cada dado.



## Soluções:

## Novo Microserviço

## Geração de código

## Duplicação de código

## Padrão Sidecar



## Resumo deste capítulo:



## O que é o Princípio DRY?

O princípio DRY é um dos fundamentos da engenharia de software, incentivando a eliminação de repetições de lógica ou dados ao consolidá-los em um único local, como métodos, classes ou variáveis compartilhadas. Em um escopo mais amplo, a lógica compartilhada entre projetos é geralmente empacotada em bibliotecas reutilizáveis, facilitando a manutenção e reduzindo a duplicação de esforços.

No entanto, em arquiteturas de microsserviços, seguir o princípio DRY com bibliotecas compartilhadas pode criar problemas significativos, especialmente relacionados ao acoplamento e à gestão de dependências.

## Desafios das Bibliotecas Compartilhadas em Microsserviços

Acoplamento Rígido: A utilização de uma biblioteca compartilhada por vários microsserviços cria dependência entre eles. Alterar a API da biblioteca exige comunicação com todas as equipes envolvidas, demandando atualizações, recompilações, novos testes e reimplantações de todos os microsserviços dependentes.

Propagação de Bugs: Um bug em uma biblioteca compartilhada pode afetar todos os microsserviços que a utilizam, contrariando o objetivo de isolar os serviços.

Inferno de Dependências (Dependency Hell): Atualizações em bibliotecas podem gerar conflitos de versões, especialmente quando uma biblioteca compartilhada depende de outra versão de uma dependência já usada diretamente pelos microsserviços. Isso pode levar a duplicidade de código ou à necessidade de ajustes desnecessários na base de código.

Impacto no Desempenho: A inclusão de versões duplicadas aumenta o tamanho dos binários e o tempo de compilação e testes.

## Alternativas às Bibliotecas Compartilhadas

## Ajuste de Limites de Microsserviços

Quando a lógica complexa é compartilhada entre microsserviços, pode ser um sinal de que os limites dos serviços estão incorretos. Reavaliar a decomposição por capacidades de negócio pode evitar a necessidade de compartilhamento de lógica.

## Microsserviço Específico para Lógica Compartilhada

Se a lógica for complexa o suficiente, ela pode ser isolada em seu próprio microsserviço, permitindo que outros serviços consumam sua funcionalidade via APIs.

## Modelos de Dados Compartilhados

Para comunicação entre microsserviços, compartilhar modelos de dados é uma prática recomendada. Isso garante consistência e permite identificar rapidamente inconsistências através de testes. Alternativamente, ferramentas de geração de código baseadas em esquemas podem ser usadas para criar modelos consistentes de maneira automatizada.

## Duplicar Códigos Simples

Para códigos utilitários que mudam frequentemente, é melhor duplicá-los em diferentes microsserviços. Isso reduz o acoplamento e facilita a adaptação do código ao caso específico de cada serviço.

## Uso do Sidecar Pattern

No padrão Sidecar, funcionalidade compartilhada é empacotada em um processo separado, executado no mesmo host dos microsserviços que o utilizam. Isso reduz o acoplamento sem comprometer significativamente o desempenho.

## Bibliotecas Altamente Estáveis

Em casos raros, códigos altamente genéricos e estáveis (ex.: registro ou correspondência de padrões) podem ser compartilhados em bibliotecas, desde que não gerem dependências críticas.

## Duplicação de Dados em Microsserviços

## A duplicação de dados é aceitável para melhorar o desempenho, desde que:

Propriedade Definida: Apenas um microsserviço é o proprietário da fonte de verdade dos dados, permitindo operações de escrita, enquanto os demais apenas leem os dados duplicados.

Consistência Eventual: Entenda que os dados duplicados podem não estar sempre atualizados, sendo essa uma limitação aceitável em muitos cenários, como para exibições de produtos em lojas on-line. Contudo, dados críticos, como estoque ou saldo, devem evitar duplicação.









## Autonomia Estruturada para Equipes de Desenvolvimento



Neste capítulo, exploraremos um conjunto de práticas recomendadas para alcançar uma arquitetura de microsserviços eficaz. Começaremos discutindo os problemas potenciais de conceder liberdade excessiva às equipes de desenvolvimento para escolher suas ferramentas e processos tecnológicos. Em seguida, apresentaremos três níveis de definição de limites de autonomia para cada equipe e, por fim, analisaremos os fatores que influenciam a definição desses limites.



Primeiro, é importante abordar um mito comum relacionado à liberdade das equipes em arquiteturas de microsserviços. O equívoco é que o maior benefício dos microsserviços seria conceder total autonomia às equipes para decidir tecnologias, ferramentas, bancos de dados, APIs e frameworks. Essa ideia, embora atraente, é uma das principais armadilhas enfrentadas por organizações que migram para microsserviços, e veremos por quê.



Um dos principais problemas dessa abordagem é o custo inicial da infraestrutura. Em sistemas monolíticos, o esforço inicial para definir estruturas, organizar o código em módulos, pacotes ou bibliotecas, e decidir ferramentas de teste e execução, geralmente é significativo, mas centralizado. Além disso, as ferramentas de compilação, scripts de automação e pipelines de integração contínua são configurados e ajustados para facilitar a resolução de problemas em produção. Também há investimentos substanciais em ferramentas de monitoramento e alerta, que exigem tempo e especialização.



Agora imagine que, após a migração para microsserviços, cada equipe precise replicar todo esse esforço para sua própria base de código e ecossistema. Isso significa que o custo e a complexidade se multiplicam proporcionalmente ao número de microsserviços. Para agravar a situação, a manutenção dessa infraestrutura não é um esforço pontual, mas contínuo. Se houver uma equipe central de DevOps ou QA, esses profissionais terão que lidar com centenas de microsserviços, muitas vezes com arquiteturas e ferramentas completamente diferentes, tornando a padronização e o suporte extremamente desafiadores.



Essas equipes ficarão rapidamente sobrecarregadas e terão que contratar mais pessoas para acompanhar essa selva de tecnologias. Mas, além do custo de instalação e manutenção, há também um custo associado ao aprendizado e à produtividade no uso de todas essas ferramentas. Portanto, qualquer novo desenvolvedor de uma determinada equipe precisa ler a documentação, aprender e memorizar todas as práticas recomendadas e se acostumar a segui-las em seu trabalho diário.





Mas e se eles precisarem trabalhar na base de código de outra equipe para fazer uma pequena alteração? Ou se eles simplesmente precisarem examinar a base de código de outra equipe e descobrir como eles definiram um determinado teste de integração ou como é a configuração deles. Seria uma enorme curva de aprendizado que simplesmente não se dimensiona em uma grande organização. Além disso, há outro problema que é a API não uniforme. Não podemos nos esquecer de que todos esses microsserviços, no final das contas, precisam se unir como um único sistema e se comunicar entre si para atingir um objetivo comum de maneira fácil e eficiente. Então, imagine o que aconteceria se cada equipe proprietária de um microsserviço pudesse definir sua própria API em seu próprio estilo, seguindo suas próprias práticas recomendadas.



Agora, um engenheiro de front-end que precisa extrair dados de diferentes microsserviços teria que aprender a API de cada equipe e integrar-se a ela, chamando pontos de extremidade com diferentes convenções de nomenclatura e usando muitos estilos e tecnologias de API diferentes, o que tornará o código de front-end uma enorme bagunça difícil de ler e manter.



Da mesma forma, se um determinado microsserviço precisar se comunicar com vários microsserviços diferentes em cenários diferentes, teremos o mesmo problema. O engenheiro que precisar adicionar ou atualizar essa chamada de API terá que passar horas lendo a documentação da outra equipe para garantir que ela esteja em conformidade. Suas melhores práticas. Portanto, como podemos ver, ao permitir que cada equipe tenha total autonomia, estamos, na verdade, piorando muito as coisas e introduzindo muitas despesas gerais.



A essa altura, você pode estar se perguntando: o objetivo da migração para microsserviços não é permitir que cada equipe seja totalmente independente?



Bem, sim, mas o sucesso de uma arquitetura de microsserviços depende de encontrar o equilíbrio entre a autonomia das equipes e a estrutura organizacional. O conceito que descreve bem esse equilíbrio é autonomia estruturada. Isso significa que cada equipe é autônoma dentro de limites bem definidos, organizados em três níveis.



## Primeiro Nível: Padronização Total

A camada mais restritiva estabelece áreas que devem ser uniformes em toda a organização e não ficar sob a jurisdição de equipes individuais. Isso inclui:

Infraestrutura compartilhada: ferramentas de monitoramento, alertas, integração e entrega contínuas.

Um investimento inicial na criação ou adoção de uma infraestrutura comum traz economias de escala, já que o esforço é amortizado por toda a organização.

APIs públicas e internas: diretrizes padronizadas para a definição e uso de APIs.

Isso garante consistência tanto na experiência de clientes externos quanto na integração entre microsserviços internos, facilitando a comunicação e a interoperabilidade entre equipes.

## Políticas de segurança e conformidade de dados:

A uniformidade em segurança é crucial. Um único microsserviço vulnerável pode comprometer todo o sistema. Da mesma forma, violações de conformidade podem expor a organização a penalidades legais, independentemente de qual microsserviço foi o responsável.

## Segundo Nível: Liberdade Controlada

O segundo nível permite certa flexibilidade para as equipes, mas dentro de limites pré-estabelecidos. Exemplos incluem:

## Escolha de linguagens de programação e bancos de dados:

Cada caso de uso pode exigir soluções específicas. No entanto, o conjunto de tecnologias disponíveis deve ser restrito para evitar uma "selva tecnológica", que tornaria o sistema difícil de gerenciar.

Limitar as opções permite que a organização desenvolva especialização na configuração, operação e suporte dessas tecnologias em produção.

## Práticas de implementação técnica:

Embora cada equipe tenha liberdade para adaptar suas ferramentas de desenvolvimento e teste, isso deve ocorrer dentro de um ecossistema alinhado às diretrizes organizacionais.

Empresas maduras tendem a adotar apenas um pequeno número de linguagens e bancos de dados aprovados, permitindo um equilíbrio entre diversidade e controle operacional.

## Terceiro Nível: Total Autonomia

## O último nível concede total liberdade às equipes em áreas como:

## Processo de liberação:

Cada equipe define seu próprio cronograma, frequência e prioridades de lançamento, adaptando-se às suas necessidades específicas.

## Ferramentas personalizadas:

As equipes podem desenvolver scripts e ferramentas específicas para suas operações locais, otimizando o desenvolvimento e os testes.

## Documentação e integração:

Cada equipe é responsável por documentar seu microsserviço e estruturar o processo de integração para novos membros.

Essa autonomia garante que as equipes operem de forma independente, priorizando entregas rápidas e adaptando-se às suas realidades de trabalho.

## Fatores que Influenciam os Limites

Os limites entre esses níveis podem variar dependendo de fatores organizacionais, como:

## Força das equipes de DevOps ou SRE:

Empresas com equipes de DevOps/SRE dominantes tendem a favorecer padronizações mais rígidas para facilitar a manutenção e escalabilidade do sistema.

## Experiência dos desenvolvedores:

Desenvolvedores experientes geralmente preferem maior liberdade para criar ou configurar suas próprias infraestruturas.

## Cultura organizacional:

Algumas empresas adotam uma única linguagem de programação, como Java, Python ou C, limitando a escolha de tecnologias. Essa abordagem simplifica a movimentação de desenvolvedores entre equipes, reduzindo custos de treinamento e adaptação.

O equilíbrio entre padronização e autonomia é a base de uma arquitetura de microsserviços bem-sucedida. Padronizar áreas essenciais reduz complexidade e custos, enquanto conceder liberdade controlada às equipes permite inovação e agilidade. Ajustar esses níveis às necessidades e à cultura da empresa é o que garante a eficácia do modelo.



Neste capítulo, aprendemos sobre as desvantagens de dar muita liberdade a cada equipe de microsserviço. Essas desvantagens incluíam custos iniciais e contínuos de manutenção, uma curva de aprendizado acentuada, despesas gerais e uma API não uniforme. Para resolver esses problemas, introduzimos o conceito de autonomia estruturada, que permite que as equipes ainda sejam independentes, mas dentro de um conjunto de limites.



E, por fim, falamos sobre alguns fatores que podem influenciar esses limites, como a influência da equipe de DevOps ou SRE, a senioridade dos desenvolvedores contratados e a cultura da empresa.



## Os 3 níveis de autonomia da equipe:

## Restrição total:

## Infraestrutura

# API

## Segurança

## Liberdade com limites:

## Linguagens de programação

## Tecnologias de banco de dados

## Autonomia completa:

## Processo de lançamento

## Cronograma e frequência de lançamento

## Scripts personalizados para desenvolvimento e teste local

## Documentação

## O processo de integração para novos desenvolvedores





## Padrão de Arquitetura de Micro-frontends



Já abordamos todas as práticas recomendadas para organizar e armazenar nossos dados na arquitetura de microsserviços e também discutimos as práticas recomendadas para dividir, gerenciar e operar cada microsserviço por uma equipe independente. Agora, vamos abordar a última parte da arquitetura, que é o front-end. Neste capítulo, discutiremos primeiro os problemas de um front-end monolítico. Em seguida, aprenderemos sobre um padrão de arquitetura chamado micro-frontends que resolve esses problemas. Depois disso, ilustraremos como esse padrão funciona com um exemplo da vida real. E, por fim, discutiremos os benefícios e as práticas recomendadas para o uso desse padrão.



Então, o que é um front-end monolítico? Vamos imaginar que temos uma plataforma de aprendizagem on-line em que os usuários podem pesquisar, inscrever-se e fazer cursos on-line. O front-end inclui a página inicial, que exibe uma barra de pesquisa na qual o usuário pode procurar cursos por palavras-chave ou por categorias, e a área de recomendação de cursos, que mostra os cursos nos quais o usuário pode estar interessado. Além disso, no canto superior direito, temos o botão de perfil dos alunos. Quando um usuário pesquisar um curso com base em uma palavra-chave ou categoria, a lista de cursos relevantes será exibida na página. E quando um usuário clicar em um curso específico, ele será levado à página de destino do curso.  Quando eles decidem se inscrever nesse curso. Eles podem clicar no botão de inscrição, que os leva à página de inscrição. E nessa página de inscrição, eles podem fornecer suas informações de pagamento, nome e endereço de cobrança e concluir a inscrição. Além disso, se voltarmos à página inicial, quando um usuário clicar no botão de perfil, ele verá seu perfil de usuário e todos os cursos em que está matriculado.



Não vamos abordar todas as diferentes partes da plataforma, mas você já entendeu a ideia. Agora, no lado do back-end, arquitetamos nosso sistema usando a arquitetura de microsserviços, seguindo todas as práticas recomendadas de decomposição de microsserviços que já aprendemos. Temos uma equipe separada de desenvolvedores de back-end que são responsáveis por cada microsserviço. Cada microsserviço mantém seus dados em seu próprio banco de dados e os microsserviços se comunicam entre si por meio de uma API bem definida que segue o padrão de toda a empresa. Eles também compartilham um conjunto comum de ferramentas e infraestrutura para testar, implantar e monitorar o sistema em produção.



No entanto, no front-end, temos uma equipe de front-end que mantém uma única base de código responsável por todas as experiências de usuário que acabamos de mencionar, e todo o código do aplicativo Web reside em um único repositório e é obtido do serviço de aplicativo Web para o navegador do usuário. Agora, sempre que a equipe de descoberta de cursos quiser adicionar um novo recurso que permita que os usuários pesquisem cursos usando atributos adicionais, como duração do curso, classificação do idioma ou categorias adicionais, teremos o problema de que a equipe terá que implementá-lo primeiro em seu microsserviço e, em seguida, pedir à equipe de front-end que dedique seu tempo para adicionar esse recurso ao front-end. Da mesma forma, quando a equipe de recomendações de cursos quiser mostrar aos usuários mais dados ou dados diferentes, ela terá que coordenar e cooperar com a mesma equipe de front-end para fornecê-los.



Isso cria uma dependência para todas as equipes de microsserviços dessa única equipe de front-end, o que se torna um gargalo na organização de desenvolvimento. Por outro lado, quando a equipe de front-end, por exemplo, quiser melhorar a página de perfil do usuário, os desenvolvedores de front-end terão que aprender e se integrar com a equipe de atendimento ao usuário e, para otimizar o processo de inscrição e checkout, os desenvolvedores de front-end terão que se familiarizar muito bem com o domínio de negócios e as APIs dos serviços de inscrição e pagamento. Portanto, a equipe de front-end precisa desenvolver constantemente conhecimentos especializados em domínios que pertencem a outras equipes.



Isso une fortemente as equipes de back-end e a já limitada equipe de front-end, que é o que queríamos. Para evitar a migração para microsserviços, além desses problemas organizacionais. Essa base de código front-end monolítica tem um problema mais técnico. À medida que nossos negócios crescem, o mesmo acontece com o front-end. Assim, a base de código única se torna muito grande para ser mantida e analisada.  Também leva muito mais tempo para testar. E se quisermos lançar um novo recurso de interface do usuário, todo o código de front-end precisará ser reconstruído, testado novamente e reimplantado.



Todos esses são os mesmos problemas com os quais já lidávamos em um aplicativo monolítico de back-end, mas agora também os temos no front-end. Para resolver esses problemas, podemos seguir um padrão de arquitetura chamado Micro-frontends.



Nesse padrão, dividimos o aplicativo monolítico da Web em vários módulos ou bibliotecas de front-end que atuam como aplicativos independentes de página única. A divisão pode ser feita por capacidade de negócios ou domínio, assim como fizemos nos microsserviços. Na maioria dos casos, cada página do aplicativo Web se torna um microfrontend separado, mas também podemos ter vários microfrontends visíveis na mesma página.



Cada microfrontend é completamente desacoplado dos outros microfrontends e deve saber como carregar, montar e desmontar a si mesmo do dome no navegador. Cada microfrontend também pode ser carregado no navegador da Web como um aplicativo da Web autônomo para fins de teste.



E o mais importante é que ele pertence a uma equipe separada com recursos técnicos de pilha completa e o conhecimento do domínio para desenvolver e manter esse microfrontend. Todos esses micro-frontends são então reunidos em tempo de execução por um aplicativo da Web em contêiner. Quando o usuário carrega nosso site em seu navegador. A função do aplicativo contêiner é renderizar elementos comuns, como cabeçalhos e rodapés de página, cuidar de funcionalidades comuns, como autenticação e bibliotecas compartilhadas, e informar a cada microfrontend quando e onde eles precisam ser renderizados na página.



Agora, antes de ilustrarmos como isso pode funcionar em um cenário da vida real, quero destacar dois aspectos que geralmente são uma grande fonte de confusão. A primeira coisa é que os microfrontends são um padrão arquitetônico. Não se trata de uma estrutura ou biblioteca da Web. Muitas estruturas da Web oferecem suporte a esse padrão, mas não precisamos usar nenhuma delas em particular para implementá-lo. A segunda fonte comum de confusão é entre componentes da Web compartilhados e microfrontends. Um microfrontend não é um botão genérico de barra de pesquisa ou algum outro elemento de interface do usuário que possa ser reutilizado em diferentes locais da página. Em vez disso, é um aplicativo da Web de página única com funcionalidade comercial muito limitada. Microfrontends diferentes podem reutilizar elementos comuns da interface do usuário, mas os dois conceitos não estão relacionados.



Agora que entendemos a ideia por trás desse padrão, vamos ilustrá-lo com o mesmo cenário de plataforma de aprendizagem on-line. Quando o usuário envia uma solicitação para a página inicial, o serviço de aplicativo da Web envia de volta o aplicativo contêiner para o usuário. Esse aplicativo de contêiner lida primeiro com a autenticação do usuário. Em seguida, ele armazena o token de autenticação no dispositivo do usuário para que ele não precise se autenticar novamente a cada solicitação ou recarga de página. Após a conclusão da autenticação, o aplicativo contêiner renderiza o cabeçalho e o rodapé da nossa plataforma de aprendizagem e, em seguida, chama os pontos de entrada do microfrontend do Discovery do curso e as recomendações do curso.



Micro-frontend: o código de cada um desses micro-frontends fará uma solicitação ao serviço de backend relevante para criar o HTML com todos os dados relevantes e, em seguida, renderizar-se na página onde o aplicativo contêiner o instruir. Da mesma forma, quando um usuário navega para a página de perfil do usuário, ele aciona primeiro a desmontagem dos microfrontends de descoberta de curso e de recomendações de curso e, em seguida, a renderização do microfrontend de perfil do usuário, que é mantido pelo profile e está obtendo dados de seu serviço de back-end.



O mesmo acontece com a página de inscrição no curso, que obtém seu microfrontend do serviço de inscrição e é mantida pela equipe de inscrição. E todas as outras partes do nosso aplicativo Web seguem o mesmo padrão. Portanto, agora que entendemos o padrão de arquitetura de microfrontends e temos uma intuição de como ele funciona, vamos falar sobre os benefícios desse padrão.



A principal vantagem é que substituímos a grande base de código de front-end complexa e monolítica por algumas bases de código pequenas e muito mais gerenciáveis, cada uma para um micro-front-end diferente. Além disso, agora cada equipe é totalmente proprietária de seu domínio e pilha técnica de ponta a ponta. Portanto, se uma equipe de recomendações de cursos, de inscrições ou de descoberta de cursos quiser oferecer um novo recurso, ela poderá fazer isso de forma independente, sem esperar ou depender de outra equipe. Além disso, cada microfrontend é muito mais fácil e rápido de testar isoladamente, pois seu escopo é muito menor. Cada microfrontend tem seu próprio processo de integração contínua, pipeline e implementação, e a equipe que o possui pode lançar novos recursos em seu próprio cronograma.



Agora vamos falar sobre algumas práticas recomendadas para o uso do padrão Micro-frontends. A primeira prática recomendada é garantir que os microfrontends sejam carregados em tempo de execução e não sejam expressos como dependências de tempo de compilação ou construção do aplicativo de contêiner. Caso contrário, tudo o que faríamos seria apenas separar a base de código logicamente, mas, no tempo de execução, ainda teríamos um frontend monolítico que exigiria uma reimplantação completa para cada novo recurso. Essa prática recomendada é muito semelhante à que tínhamos no back-end, em que dividir um aplicativo monolítico em módulos ou bibliotecas não proporcionava os mesmos benefícios que dividi-lo em microsserviços.



A próxima prática recomendada é garantir que os microfrontends não compartilhem o estado, e o estado de compartilhamento do navegador seria o equivalente a diferentes microsserviços. Compartilhar um banco de dados que já conhecemos é uma abordagem ruim. Portanto, diferentes microfrontends precisam se comunicar uns com os outros. Eles podem fazer isso de uma das seguintes maneiras: usando eventos personalizados, passando retornos de chamada ou usando a barra de endereços do navegador.



## Resumo deste capítulo:



Já discutimos as práticas recomendadas para organizar e armazenar dados em uma arquitetura de microsserviços, além de estratégias para dividir, gerenciar e operar cada microsserviço por equipes independentes. Agora, vamos abordar o último componente dessa arquitetura: o front-end.

## Neste capítulo, seguiremos os seguintes passos:

Identificar os problemas associados a um front-end monolítico.

Introduzir o padrão arquitetural micro-frontends como solução.

Demonstrar seu funcionamento com um exemplo prático.

Discutir os benefícios e práticas recomendadas para sua implementação.



## Problemas de um Front-End Monolítico

Imagine uma plataforma de aprendizado online onde usuários podem pesquisar, inscrever-se e realizar cursos. O front-end inclui:

Uma página inicial com barra de pesquisa para encontrar cursos por palavras-chave ou categorias, área de recomendação de cursos e botão de perfil.

Páginas de curso, acessadas ao selecionar um curso, onde o usuário pode obter mais informações e decidir inscrever-se.

Uma página de inscrição que coleta dados de pagamento e informações do usuário.

Uma página de perfil, que exibe informações do usuário e cursos em que está matriculado.

## No back-end, o sistema já segue as melhores práticas de microsserviços:

Cada microsserviço é gerenciado por uma equipe dedicada, possui seu próprio banco de dados e se comunica por APIs padronizadas.

Compartilha uma infraestrutura comum para testes, implantação e monitoramento.

No entanto, no front-end, todo o código reside em uma única base monolítica mantida por uma única equipe, criando dependências organizacionais e técnicas.

## Problemas organizacionais:

## Dependência cruzada entre equipes:

Se a equipe de "Descoberta de Cursos" precisar adicionar filtros de pesquisa, ela dependerá da equipe de front-end para implementar a funcionalidade.

Da mesma forma, a equipe de "Recomendações" precisará colaborar para exibir novos dados na interface.

## Conhecimento disperso:

A equipe de front-end precisa entender detalhes de múltiplos domínios, como APIs e lógica de negócios de inscrição, pagamento e perfil.

## Problemas técnicos:

## Crescimento da base de código:

À medida que a aplicação cresce, a base de código monolítica torna-se mais complexa, difícil de manter e demorada para testar.

## Gargalos em releases:

Qualquer novo recurso exige a reconstrução, reteste e reimplantação de todo o front-end.

Esses problemas refletem os mesmos desafios enfrentados por um back-end monolítico antes da migração para microsserviços.



## Introdução ao Padrão Micro-Frontends

Para resolver esses problemas, aplicamos o padrão de arquitetura Micro-frontends. Ele divide o aplicativo monolítico em módulos independentes, cada um funcionando como um aplicativo de página única.

## Características do Micro-Frontend:

## Divisão por domínios de negócio:

Cada página ou funcionalidade principal é implementada como um micro-frontend.

Exemplo: páginas de perfil, descoberta de cursos e inscrição seriam micro-frontends independentes.

## Autonomia:

Cada micro-frontend é mantido por uma equipe com conhecimentos completos sobre seu domínio.

Pode ser testado e executado de forma independente.

## Desacoplamento:

O micro-frontend carrega, monta e desmonta dinamicamente no navegador, sem dependências diretas entre si.

Esses módulos são reunidos em tempo de execução por um aplicativo contêiner, responsável por:

Renderizar elementos comuns (ex.: cabeçalho e rodapé).

Garantir autenticação e gerenciamento de estados globais.

Informar a cada micro-frontend quando e onde deve ser renderizado.







## Exemplo Prático

## Quando o usuário acessa a página inicial da plataforma:

O aplicativo contêiner é carregado no navegador.

Ele executa a autenticação e renderiza os elementos comuns.

## Em seguida, invoca os pontos de entrada dos micro-frontends de:

Descoberta de cursos.

Recomendações de cursos.

Cada micro-frontend se comunica com seu respectivo serviço de back-end, renderiza os dados obtidos e insere o conteúdo na página conforme instruído pelo contêiner.

## Quando o usuário navega para a página de perfil, o contêiner:

Desmonta os micro-frontends da página inicial.

Renderiza o micro-frontend de perfil, que se comunica com o serviço de back-end correspondente.

Esse mesmo padrão se aplica a todas as outras partes do aplicativo.



## Benefícios dos Micro-Frontends

## Manutenção simplificada:

A base de código é dividida em partes menores e mais gerenciáveis.

## Autonomia das equipes:

Cada equipe é responsável pelo desenvolvimento e implantação de seu domínio.

## Implantações independentes:

Cada micro-frontend possui pipelines de CI/CD próprios e pode ser atualizado sem afetar o restante do sistema.

## Testes mais rápidos:

O escopo reduzido de cada módulo acelera o processo de testes e validação.



## Práticas Recomendadas

## Carregamento em tempo de execução:

Os micro-frontends devem ser carregados dinamicamente pelo contêiner, evitando dependências de tempo de compilação.

## Isolamento de estado:

Os micro-frontends não devem compartilhar estado global diretamente. A comunicação deve ser feita por eventos personalizados, callbacks ou alterações na barra de endereços.

## Reutilização inteligente:

Elementos comuns (ex.: botões ou barras de busca) podem ser compartilhados, mas cada micro-frontend deve operar como uma unidade independente.



## Conclusão

Adotar micro-frontends transforma um front-end monolítico em módulos independentes, alinhando o front-end à filosofia de microsserviços. Com isso, eliminamos gargalos, promovemos autonomia e melhoramos a escalabilidade do sistema.





## Gerenciamento de API para Arquitetura de Microsserviços



Neste capítulo, abordaremos o gerenciamento de APIs na arquitetura de microsserviços. Começaremos discutindo os problemas associados a esse gerenciamento, seguiremos com a apresentação do padrão de gateway de API como solução e concluiremos esclarecendo a diferença entre um balanceador de carga e um gateway de API.



Então, vamos começar com o problema que estamos tentando resolver quando se trata de gerenciamento de API. Vamos imaginar que somos uma empresa de saúde e fitness que fornece serviços digitais a clientes e empresas, como academias de ginástica, hospitais e consultórios médicos. No lado do cliente, temos diferentes dispositivos, como smartwatches, telefones celulares e outros acessórios vestíveis, interagindo com nossa plataforma. Além disso, temos outras empresas, servidores, desenvolvedores, computadores e profissionais de saúde que utilizam nosso sistema usando seus navegadores da Web internamente.



Temos dezenas ou até centenas de microsserviços que expõem diferentes APIs específicas para sua funcionalidade. Portanto, o primeiro problema é que os diferentes pontos de extremidade de API expostos por diferentes microsserviços são codificados em muitos front-ends e SDKs de clientes.



Isso une firmemente o código do lado do cliente à implementação interna do nosso sistema. Por exemplo, vamos imaginar que em algum momento decidimos dividir um microsserviço existente em dois microsserviços e agora cada microsserviço expõe uma nova API com IDs e pontos de extremidade relevantes somente para esse microsserviço. Devido a esse forte acoplamento, também teremos que refatorar todo o código do lado do cliente em cada tipo de dispositivo para usar as novas APIs.



Outro problema é que diferentes microsserviços podem expor sua API a diferentes clientes. Por exemplo, podemos expor pontos de extremidade de APIs públicas externamente a clientes, pontos de extremidade de APIs privadas que expomos somente a serviços internos e APIs de parceiros que expomos somente a empresas e desenvolvedores parceiros.



Embora internamente possamos fazer o possível para seguir diretrizes específicas de API, nem sempre é possível fazer isso com APIs externas.

Por exemplo, no mesmo serviço, podemos ter que expor um tipo de API para uma empresa parceira que só oferece suporte a alguma tecnologia de API antiga, mas depois temos que expor a mesma funcionalidade de API para duas outras empresas que oferecem suporte a tecnologias de API mais novas, porém diferentes.



Além disso, podemos ter diferentes versões da mesma API para diferentes níveis de clientes com diferentes recursos com base em seu nível de assinatura. Por exemplo, podemos ter uma API que seja mais limitada e projetada para usuários gratuitos, enquanto oferecemos outra API com mais recursos para nossos clientes premium.



Como podemos ver, essa selva de APIs na arquitetura de microsserviços pode rapidamente se tornar muito difícil de gerenciar e raciocinar. Outro problema é controlar e monitorar como cada cliente ou dispositivo interage com nosso sistema. Por exemplo, ao carregar um painel de controle de seu exercício diário, o aplicativo móvel de um determinado usuário pode ter que fazer várias chamadas de API para diferentes microsserviços, mas como o front-end faz essas chamadas diretamente para nossos serviços, é muito difícil monitorá-las e rastreá-las em todo o sistema.



Por fim, muitos códigos padrão, como autorização e limitação de taxa, precisam ser implementados em cada microsserviço. Isso gera muito esforço, duplicação e desperdiça muito tempo de cada equipe, que poderia se concentrar em outra coisa. Portanto, para desacoplar o lado do cliente da arquitetura interna e facilitar o gerenciamento da API, podemos usar o padrão de gateway de API.



O padrão de gateway de API é particularmente útil para a arquitetura de microsserviços e é usado por muitas empresas. Esse padrão coloca um componente chamado gateway de API na entrada do nosso sistema e é responsável por todo o gerenciamento da API.



No cenário mais simples, o gateway de API simplesmente encaminha as solicitações de um determinado endpoint de API para o microsserviço relevante que o manipula. Mas, na maioria dos casos, ele pode fazer muito mais do que apenas o roteamento de solicitações. Por exemplo, vamos supor que temos três clientes que precisam interagir com o mesmo microsserviço para obter alguns dados. Mas a tecnologia de API e o formato de dados para esses clientes são diferentes do gateway de API e, em seguida, transformam as solicitações em um tipo de API canônica e no formato de dados que o microsserviço suporta. Da mesma forma, ele pode fazer essa tradução inversa para a resposta de volta ao cliente.



Isso torna a definição e o gerenciamento da API muito mais fáceis e limpos para cada serviço de microsserviço, porque eles não precisam se preocupar com os diferentes clientes e suas limitações específicas, e todos podem seguir um padrão e utilizar a mesma infraestrutura, além de rotear a solicitação para o microsserviço correspondente.



O gateway de API também pode executar o gerenciamento e a limitação do tráfego. Por exemplo, se tivermos um parceiro de negócios que esteja tentando consultar dados do nosso sistema a uma taxa muito alta, podemos facilmente limitar essa consulta no nível do gateway de API, evitando que ela sobrecarregue o microsserviço ou os microsserviços que precisam lidar com essas solicitações.



Também podemos delegar a autorização e o encerramento do TLS ao gateway de API. Portanto, os microsserviços não precisam se preocupar com isso e podem se concentrar na implementação da lógica de negócios. Além disso, como todo o tráfego de nossos front-ends passa pelo gateway de API, podemos monitorá-lo facilmente.



Isso nos permite detectar problemas em APIs específicas ou analisar o comportamento de nossos clientes e empresas parceiras. Por fim, algumas implementações de um gateway de API podem até permitir a distribuição de uma determinada solicitação para vários serviços e a agregação dos resultados antes de enviá-los de volta ao cliente. Esse é um recurso essencial por vários motivos. O primeiro motivo é que isso desvincula ainda mais os clientes de nossa implementação interna. Por exemplo, internamente, podemos refatorar esses serviços combinando vários microsserviços em um só ou dividindo um microsserviço existente em vários microsserviços. E todos esses detalhes de implementação permanecerão completamente transparentes para o usuário.



Esse recurso também é muito importante para dispositivos móveis e IOT, pois cada solicitação de rede afeta diretamente a vida útil da bateria. Agora, antes de concluirmos, quero discutir uma fonte comum de confusão entre a função de um balanceador de carga e um gateway de API para a arquitetura de microsserviços.



Tanto um balanceador de carga quanto um gateway de API encaminham as solicitações de rede recebidas de um cliente para um único destino. No entanto, é aí que terminam as semelhanças entre os dois componentes. A principal diferença entre os dois componentes é sua finalidade. A função de um balanceador de carga é, sem surpresa, equilibrar a carga de tráfego em um grupo de servidores. Esses servidores geralmente executam cópias idênticas do mesmo aplicativo. No contexto dos microsserviços, normalmente temos um balanceador de carga na frente de cada microsserviço, onde cada microsserviço é implantado como um grupo de instâncias idênticas. Por outro lado, o objetivo do gateway de API é ser a interface pública do nosso sistema. Sua função é rotear solicitações, não para servidores, mas para serviços com base em critérios diferentes.



Agora, além da diferença em sua finalidade, há também uma diferença sutil em sua funcionalidade. O balanceador de carga deve ser o mais simples possível para reduzir a sobrecarga de desempenho. Ele também costuma realizar verificações de integridade em seus servidores de back-end para garantir que não encaminhe solicitações para servidores que não respondem.



E também costuma oferecer diferentes algoritmos de balanceamento de carga para diferentes cargas de trabalho. Por outro lado, espera-se que o gateway de API ofereça muitos outros recursos, como limitação, monitoramento, controle de versão da API e protocolo de gerenciamento e tradução de formato de dados, entre outros. Portanto, como esses componentes têm finalidades diferentes, eles geralmente são usados juntos na arquitetura de microsserviços.



## O Problema do Gerenciamento de APIs

Imagine uma empresa de saúde e fitness que oferece serviços digitais para clientes e parceiros, como academias, hospitais e consultórios médicos. No lado do cliente, temos dispositivos como smartwatches e smartphones interagindo com a plataforma. Além disso, empresas, servidores, desenvolvedores e profissionais de saúde acessam o sistema via navegadores.

Com dezenas ou centenas de microsserviços expondo APIs específicas, surgem os seguintes problemas:

Acoplamento excessivo: Pontos de extremidade de APIs são codificados diretamente em front-ends e SDKs de clientes. Mudanças internas, como dividir um microsserviço em dois, exigem grandes refatorações no código cliente.

Gerenciamento de diferentes APIs: Necessidade de expor APIs públicas, privadas e de parceiros, muitas vezes com versões e tecnologias distintas, dependendo do cliente ou nível de assinatura.

Monitoramento e controle: Chamadas diretas de front-ends para microsserviços dificultam rastreamento, monitoramento e controle do tráfego.

Repetição de lógica padrão: Funcionalidades como autenticação, autorização e limitação de taxa precisam ser implementadas em múltiplos microsserviços, gerando esforço redundante.



## A Solução: Gateway de API

Para desacoplar o lado cliente da arquitetura interna e simplificar o gerenciamento de APIs, utilizamos o padrão de gateway de API. Esse componente funciona como a entrada central do sistema, oferecendo:

Roteamento inteligente: Direciona solicitações para os microsserviços apropriados, abstraindo detalhes internos.

Transformação de dados: Converte formatos e tecnologias de APIs, unificando a interação entre clientes e serviços.

Gestão de tráfego: Implementa limitação de taxa e balanceamento de uso para proteger serviços de sobrecarga.

Centralização de segurança: Lida com autenticação, autorização e encerramento de TLS, aliviando microsserviços dessas responsabilidades.

Monitoramento centralizado: Fornece visibilidade total sobre o tráfego de API, facilitando análises e detecção de problemas.

Agregação de respostas: Consolida dados de múltiplos microsserviços antes de retornar ao cliente, reduzindo o número de chamadas e economizando recursos.

Esses recursos simplificam o gerenciamento de APIs, permitindo que os microsserviços se concentrem exclusivamente na lógica de negócio.



## Gateway de API vs. Balanceador de Carga

Apesar de ambos encaminharem solicitações de rede, suas finalidades são distintas:

Balanceador de carga: Distribui tráfego entre instâncias idênticas de um microsserviço, garantindo alta disponibilidade e desempenho. Geralmente, realiza verificações de integridade e usa algoritmos otimizados para balanceamento.

Gateway de API: Atua como interface pública, gerenciando funcionalidades como roteamento, limitação de taxa, monitoramento e transformação de dados. Seu foco é fornecer uma abstração eficiente para clientes e parceiros.

Ambos desempenham papéis complementares e são frequentemente utilizados em conjunto na arquitetura de microsserviços.



## Conclusão

O padrão de gateway de API resolve diversos desafios relacionados ao gerenciamento de APIs na arquitetura de microsserviços. Ele desacopla clientes da implementação interna, simplifica o gerenciamento, melhora a escalabilidade e centraliza funcionalidades comuns. Além disso, compreendemos que o gateway de API e o balanceador de carga têm finalidades distintas, mas trabalham juntos para garantir uma operação eficiente e robusta.





## Introdução à Arquitetura Orientada a Eventos



Neste capítulo, aprenderemos outro estilo arquitetônico chamado arquitetura orientada por eventos e como combinar esse estilo com a arquitetura de microsserviços. Primeiro conheceremos a motivação da arquitetura orientada por eventos e por que precisamos dela. Em seguida, falaremos sobre os conceitos fundamentais da arquitetura orientada por eventos. Depois disso, compararemos o modelo de resposta à solicitação com o modelo orientado por eventos para ilustrar seus benefícios. E, por fim, demonstraremos o uso do modelo orientado por eventos em um exemplo real.



Antes de discutir a arquitetura orientada por eventos, vamos nos motivar com um cenário da vida real. Vamos considerar um serviço de assinatura de vídeo sob demanda que projetamos usando a arquitetura de microsserviços. Depois que o usuário experimenta nosso serviço gratuitamente, ele está pronto para prosseguir e fazer o upgrade para uma assinatura paga em nossa plataforma, que lhe dá acesso a todos os nossos filmes e a muitos outros recursos avançados. No backend, temos os seguintes microsserviços participando dessa transação. Nosso serviço de assinatura mantém todas as informações sobre cada assinante, inclusive o nível da assinatura, a data de vencimento e assim por diante. Também temos um serviço de pagamento que, com as informações do cartão de crédito do usuário, comunica-se com empresas terceirizadas para criar um usuário. Também temos o serviço de recomendações e personalização, que cria e mantém um perfil exclusivo para cada cliente pagante para fornecer a ele seu histórico de exibição e recomendações de filmes futuros com base no que ele assistiu no passado e também com base em seu país.



É importante observar que, para que um usuário seja totalmente inscrito em nosso serviço, precisamos garantir que cada um desses serviços receba e processe com êxito a solicitação de inscrição. Vamos explorar algumas maneiras de implementar uma assinatura de usuário e identificar os problemas de cada abordagem.



A primeira abordagem seria enviar uma solicitação contendo todas as informações do usuário para o serviço de assinatura. Esse serviço de assinatura atualizará seu próprio banco de dados e, em seguida, enviará a solicitação ao serviço de pagamento. O serviço de pagamento entrará em contato com o serviço terceirizado de processamento de cartão de crédito e, assim que obtiver uma confirmação, atualizará seu próprio banco de dados e enviará a solicitação ao serviço de recomendação. Quando o serviço de recomendação atualizar com êxito seu banco de dados, ele enviará uma resposta ao serviço de pagamento. O serviço de pagamento enviará uma resposta de confirmação ao serviço de assinatura, e o serviço de assinatura responderá ao front-end mostrando ao usuário uma página de assinatura bem-sucedida.



A vantagem dessa abordagem é que, quando o usuário recebe a resposta, há 100% de garantia de que a assinatura foi bem-sucedida e que todos os três serviços receberam e processaram a solicitação. A desvantagem, é claro, é que essa longa cadeia de comunicação mantém o usuário preso por muito tempo. Isso torna a experiência do usuário ruim, mesmo que tudo corra bem. Mas, na pior das hipóteses, se o serviço de terceiros com o qual o serviço de pagamento se comunica estiver com problemas de desempenho ou se a conexão do serviço de pagamento com o serviço de recomendação for interrompida e exigir uma nova tentativa, toda a transação fará com que o usuário espere ainda mais.



Por outro lado, não podemos nos dar ao luxo de economizar e diminuir o tempo de espera enviando uma confirmação do serviço de assinatura para o usuário antes que ele realmente receba a resposta do serviço de pagamento. E isso porque, se fizermos isso e o serviço de pagamento falhar ou nunca receber a solicitação, o usuário não será cobrado corretamente. Da mesma forma, se tentarmos otimizar e fazer com que o serviço de pagamento responda antes que o serviço de recomendação responda, corremos o risco de ter um estado inconsistente. Esse estado pode ocorrer se o serviço de recomendação falhar logo antes ou durante o processamento da solicitação, de modo que o usuário não receberá nenhum dos recursos de recomendação e personalização como parte de sua assinatura.



Portanto, como podemos ver com uma solicitação, modelo de resposta, quanto mais microsserviços tivermos na cadeia, mais tempo teremos que manter o usuário para garantir um estado consistente. E, em muitos casos, a latência é muito longa para ser aceitável. Vamos tentar uma abordagem diferente.



Em vez de fazer uma cadeia de solicitações, podemos usar um padrão de orquestração usando o padrão de orquestração (SAGA). Adicionamos um único serviço que orquestra uma transação comercial complexa envolvendo várias operações ou serviços. Esse serviço de orquestração pode, tecnicamente, ser combinado com o gateway de API, mas vamos supor que seja um serviço separado. No nosso caso, uma solicitação irá para o serviço de orquestração e, em seguida, será transmitida para os serviços relevantes em paralelo. Essa execução paralela reduzirá a latência geral da soma das latências de todos os serviços para apenas o máximo do serviço mais lento da transação. No entanto, em alguns casos, essa latência ainda pode ser muito alta. Por exemplo, considere uma situação em que o serviço terceirizado de processamento de cartão de crédito está tendo problemas de desempenho porque outra empresa ou empresas estão enviando muitas solicitações simultâneas. Embora essa situação não esteja sob nosso controle, ela pode afetar negativamente nosso sistema e nossos clientes. Além disso, esse serviço de orquestração agora está fortemente acoplado a todos os serviços que devem estar envolvidos na transação. Portanto, se a API de um dos serviços for alterada ou se precisarmos adicionar outra etapa à assinatura na forma de outro serviço, precisaremos atualizar esse serviço de orquestração para chamar esse serviço. Por fim, se tivermos problemas temporários com apenas um dos serviços na transação, todas as solicitações de assinatura terão que ser negadas, perdendo clientes valiosos dos EUA.



Para resolver todos esses problemas e muitos outros, podemos usar a abordagem de arquitetura orientada por eventos. O principal conceito da arquitetura orientada por eventos é um Event. Um evento representa um fato, uma ação ou uma mudança de estado que ocorre em nosso sistema e é sempre imutável, ao contrário de uma solicitação, que é efêmera. Um evento pode ser armazenado indefinidamente em nosso sistema e, ao contrário de uma solicitação que deve ser consumida uma vez e somente por um servidor, um evento pode ser consumido várias vezes por diferentes serviços.



Agora, há três entidades que participam da troca de eventos em uma arquitetura orientada por eventos. O produtor que produz os eventos, um message agent que armazena e encaminha esses eventos e o consumidor ou consumidores que recebem e processam esses eventos. O message agent nos permite encaminhar um único evento para quantos consumidores quisermos e também acrescenta um nível de redundância ao nosso sistema, porque, uma vez que o evento é produzido no message agent, ele não será perdido e sempre poderemos recuperá-lo do message agent.



Agora vamos falar sobre as duas diferenças fundamentais entre o modelo de resposta a solicitações e o modelo orientado por eventos. A primeira diferença é se a comunicação no modelo de Request-Response é síncrona. A comunicação no modelo orientado por eventos é assíncrona. Isso significa que, no modelo de resposta à solicitação, quando o remetente envia uma solicitação, ele deve aguardar uma resposta, mesmo que ela não contenha informações úteis. Se a resposta nunca chega, isso geralmente indica um problema. Por outro lado, no modelo orientado por eventos, o editor não precisa nem espera receber nenhuma resposta do consumidor ou dos consumidores dos eventos. E a entrega do evento ao consumidor está fora de seu controle e responsabilidade. Isso permite que o produtor prossiga com o processamento da próxima tarefa em vez de esperar por uma resposta de que não precisa de fato. A segunda diferença fundamental é a inversão do controle no modelo de resposta à solicitação. Quando o remetente envia uma solicitação ao destinatário, ele precisa primeiro estar ciente do destinatário e dele. Também precisa saber exatamente como chamar a API. Se o remetente precisar enviar uma solicitação a vários receptores, ele precisará estar ciente de todos eles e também enviar a solicitação a cada um usando seus próprios parâmetros exclusivos. Isso faz com que o remetente dependa dos receptores da solicitação. Por outro lado, na abordagem orientada por eventos, o editor não se importa e pode nem mesmo estar ciente dos consumidores dos eventos. Isso separa completamente o produtor dos consumidores.



O acoplamento frouxo (baixo acoplamento) dos microsserviços é uma das principais qualidades que desejamos em nossa arquitetura de microsserviços. É por isso que a arquitetura orientada por eventos e a arquitetura de microsserviços combinam com tanto sucesso. Portanto, agora que entendemos os principais conceitos da arquitetura orientada por eventos, vamos aplicá-la ao nosso cenário de assinatura de usuário.



Uma das maneiras de aplicar a arquitetura orientada por eventos ao nosso caso de uso é colocar um message broker entre cada um dos nossos serviços. Quando o serviço de assinatura recebe a solicitação do usuário, ele a armazena em seu próprio banco de dados e emite um evento para o message broker. Nesse momento, ele pode enviar uma resposta ao usuário, que não precisa aguardar a conclusão do restante da transação. Agora, o serviço de pagamento consumirá esse evento, processará o armazenamento de pagamentos, o resultado em seu próprio banco de dados e, em seguida, emitirá um novo evento para o próximo serviço. Observe que o usuário não é afetado, mesmo que essa parte tenha levado muito tempo. Em seguida, o serviço de recomendação consumirá o evento, o processará e, opcionalmente, produzirá outro evento para um serviço de notificação. O Notification Service consumirá seu próprio evento e enviará ao usuário um e-mail de confirmação ou uma notificação push para seu aplicativo móvel. E é isso.



Neste capítulo, apresentamos a motivação para a arquitetura orientada por eventos usando um cenário da vida real. Nesse cenário, vimos que, independentemente de como organizamos nossos microsserviços com um modelo de resposta a solicitações síncronas, nossos serviços ainda estão fortemente acoplados e o usuário ainda corre risco se um de nossos serviços demorar a responder. Posteriormente, discutimos os conceitos fundamentais da arquitetura orientada por eventos, que gira em torno do evento que representa um fato, uma ação ou uma mudança de estado. Esse evento é emitido pelo produtor e é encaminhado de forma assíncrona pelo message broker para um ou vários consumidores. E, por fim, demonstramos como usar esse modelo em nosso exemplo real.



## Resumo:

Neste capítulo, exploraremos a arquitetura orientada a eventos e sua integração com a arquitetura de microsserviços. Iniciaremos com a motivação por trás desse estilo arquitetônico, seus conceitos fundamentais e uma comparação com o modelo tradicional de requisição-resposta. Por fim, aplicaremos esses conceitos em um exemplo prático.



## Motivação

Imagine um serviço de assinatura de vídeo sob demanda desenvolvido com microsserviços. Após o período de teste gratuito, o usuário pode fazer o upgrade para uma assinatura paga, que desbloqueia acesso a filmes e recursos premium. No backend, temos:

Serviço de assinatura: gerencia informações do assinante, como nível de assinatura e vencimento.

Serviço de pagamento: processa transações financeiras via terceiros.

Serviço de recomendação: personaliza sugestões com base no histórico do usuário.

Para concluir a inscrição, todos esses serviços devem ser acionados com sucesso.



## Abordagem Tradicional: Modelo de Requisição-Resposta

## Uma solução seria encadear solicitações:

O serviço de assinatura recebe a solicitação, atualiza seu banco de dados e aciona o serviço de pagamento.

O serviço de pagamento confirma o pagamento com terceiros e notifica o serviço de recomendação.

O serviço de recomendação processa a solicitação e devolve a resposta, concluindo o ciclo.

## Vantagem:

Ao receber a confirmação, o usuário sabe que a transação foi concluída com sucesso.

## Desvantagens:

Latência elevada: o usuário espera até que todos os serviços concluam suas tarefas.

Fragilidade: falhas em qualquer serviço interrompem o fluxo, exigindo novas tentativas.

Dependência: os serviços estão fortemente acoplados.



## Alternativa: Padrão de Orquestração

Uma abordagem melhor é introduzir um serviço de orquestração que coordena a transação:

A solicitação é recebida pelo orquestrador, que dispara tarefas paralelas para os serviços.

A latência geral é reduzida, mas podem ocorrer problemas em serviços externos (ex.: processadores de pagamento) podem impactar o desempenho global.

O orquestrador se torna um ponto de acoplamento central, exigindo alterações quando APIs ou fluxos mudam.

Embora melhore a eficiência, essa abordagem ainda apresenta desafios significativos de escalabilidade e flexibilidade.



## Solução: Arquitetura Orientada a Eventos

Na arquitetura orientada a eventos, o fluxo é baseado em eventos imutáveis que representam fatos do sistema, armazenados e processados de forma assíncrona. Os principais componentes são:

Produtor: emite eventos quando ocorre uma ação relevante.

message agent: gerencia e entrega eventos a múltiplos consumidores.

Consumidor: processa os eventos recebidos, podendo gerar novos eventos.



## Benefícios

Comunicação assíncrona: o produtor não espera respostas, reduzindo o tempo de espera e a dependência direta entre serviços.

Desacoplamento: o produtor não precisa conhecer os consumidores, promovendo flexibilidade e escalabilidade.



## Exemplo Prático

## Para o cenário de assinatura:

O serviço de assinatura registra a solicitação, emite um evento no message agent e responde imediatamente ao usuário.

O serviço de pagamento consome o evento, processa a transação e emite outro evento.

O serviço de recomendação consome o novo evento, personaliza o perfil do usuário e, opcionalmente, dispara um evento para o serviço de notificação, que informa o usuário.

Essa abordagem elimina gargalos síncronos e aumenta a resiliência, permitindo que serviços independentes processem eventos em seu próprio ritmo.







## Conclusão

A arquitetura orientada a eventos é uma solução eficaz para cenários complexos com microsserviços. Sua comunicação assíncrona e desacoplamento reduzido permitem maior escalabilidade, resiliência e melhor experiência do usuário. Aplicando esses conceitos ao exemplo de assinatura, conseguimos otimizar o fluxo, minimizar latências e garantir a consistência do sistema sem comprometer a flexibilidade.





## Casos de uso e padrões de arquitetura orientada a eventos



No capítulo anterior, vimos alguns dos grandes benefícios do uso da arquitetura orientada por eventos. No entanto, como era de se esperar, não é uma bala de prata que podemos usar para resolver todos os problemas de design. Neste capítulo, discutiremos os casos de uso em que a arquitetura orientada por eventos é uma boa opção para nós e em quais casos de uso devemos preferir o modelo tradicional de Request-Response. E, por fim, concluiremos o capítulo discutindo dois padrões de event sourcing para a arquitetura orientada por eventos.



Então, em que casos de uso devemos usar a arquitetura orientada por eventos? O primeiro caso de uso é para ações que podem ser classificadas como "disparar e esquecer" e são assíncronas por natureza. Nesses casos, o remetente não espera nenhum dado em troca imediatamente ou nenhum. Um bom exemplo é quando um usuário nos envia uma solicitação para gerar um relatório que pode levar alguns minutos ou até mesmo algumas horas para ser concluído. Portanto, nesse caso, nosso evento é a ação de gerar relatório e o resultado provavelmente será enviado para o e-mail do usuário quando essa ação for concluída. Outro exemplo é um usuário que deixa uma avaliação de um produto que comprou. Nesse caso, o usuário não espera nenhum dado como resposta, nem agora nem no futuro, e tudo o que lhe interessa é saber se a avaliação foi aceita ou não em nosso sistema. Outro caso de uso é a entrega confiável. Isso é especialmente importante em transações financeiras, nas quais não podemos nos dar ao luxo de perder mensagens em trânsito ou precisamos garantir uma entrega certa.



Um ótimo exemplo desse caso de uso é uma loja on-line em que um usuário faz o pedido de um produto. Nesse caso, se dissermos ao usuário que ele receberá seu pedido, devemos cumprir nossa promessa ou enviar um e-mail explicando por que o pedido não foi atendido. Mas não podemos ter uma situação em que um usuário envia um pedido, mas simplesmente o perdemos em trânsito porque algum servidor caiu no processo.



Outro exemplo seria uma transferência de dinheiro entre contas ou bancos. Essa também é uma situação em que essa ação exige certa confiabilidade e não podemos nos dar ao luxo de perdê-la.



Outro caso de uso da arquitetura orientada por eventos é para fluxos infinitos de dados ou eventos. Um exemplo desse caso de uso pode ser dados de localização de dispositivos móveis ou dados de sensores de dispositivos Iot, como aspiradores de pó ou carros autônomos. Nesse caso, temos um fluxo contínuo e infinito de dados entrando em nosso sistema, e precisamos analisar, agregar, transformar ou armazenar esses dados em tempo real.



O próximo caso de uso é para detecção de anomalias ou reconhecimento de padrões. Nesse caso, cada evento pode representar um fato, como o valor atual de solicitações por segundo provenientes de cada um de nossos servidores. Cada ponto de dados isolado não é tão interessante ou útil. No entanto, quando colocamos esses eventos em uma sequência, podemos obter percepções interessantes. Por exemplo, se a solicitação por segundo de um determinado servidor ou serviço aumentar, saberemos que devemos expandir nosso sistema e adicionar mais servidores. Caso contrário, nosso sistema não conseguirá lidar com o tráfego de entrada por muito mais tempo. Da mesma forma, se as solicitações por segundo caírem repentinamente para zero, isso indica alguma falha de hardware ou software que precisamos investigar imediatamente.



O próximo caso de uso é quando temos um serviço com algum tipo de alteração de estado que ele deseja transmitir a qualquer outro serviço que esteja interessado nesse evento. Esse cenário é uma escolha perfeita para a arquitetura orientada por eventos, pois o produtor do evento não precisa saber nada sobre quem o está consumindo e como o utiliza. Um exemplo desse caso de uso pode ser um usuário que clica em um anúncio digital em nosso site. Quando nosso serviço de anúncios recebe essa solicitação do front-end, ele pode emitir esse evento em uma mensagem. O message broker transmitirá esse evento a todos os serviços interessados nele, e cada serviço tem sua própria função no processo, que é completamente desconhecida pelo produtor e pelos outros consumidores desse evento.



O último caso de uso é o armazenamento de mensagens em buffer para tolerar picos de tráfego em nosso sistema. Nesse cenário, podemos tolerar um pico repentino de eventos provenientes de um serviço colocando um message broker e comunicando de forma síncrona entre os serviços. Vamos considerar uma situação em que temos uma empresa de mídia social e, de repente, um evento global desencadeou um grande número de publicações ou comentários em uma determinada publicação. Nesse caso, podemos armazenar esses eventos em um intermediário de mensagens e entregá-los aos outros serviços. Apenas na velocidade em que esses serviços podem lidar com eles.



Então, agora que falamos sobre os casos de uso que são adequados para a arquitetura orientada por eventos, vamos falar sobre alguns cenários em que preferimos o modelo de request response síncrona.



O primeiro caso de uso é quando precisamos responder ao usuário ou enviar seu serviço imediatamente com alguns dados. Por exemplo, se um usuário solicitar uma página da Web que contenha todos os produtos de uma determinada categoria, precisaremos responder a essa solicitação de forma síncrona e imediata. Caso contrário, o usuário simplesmente sairá da nossa loja on-line.



Outro tipo de cenário em que não devemos usar a arquitetura orientada por eventos é quando a interação é muito simples e não obteremos nenhum benefício com o uso do modelo orientado por eventos. O problema é que a configuração e a execução de um message agent distribuído ou gerenciado na nuvem têm alguma complexidade e custo. Portanto, se, nesse caso, quisermos simplesmente nos beneficiar desse modelo, não vale a pena.



Agora, na realidade, uma arquitetura típica de microsserviços combina a arquitetura orientada por eventos e o modelo simples de resposta a solicitações.  Também é melhor começar com um modelo simples de resposta a solicitações e, em seguida, atualizar as partes críticas para a arquitetura orientada por eventos, quando necessário.



Agora vamos falar brevemente sobre dois padrões para a entrega de eventos em uma arquitetura orientada por eventos. O primeiro padrão é chamado de streaming de eventos. Nesse padrão, o message agent é usado como um armazenamento temporário ou permanente para eventos. Os consumidores têm acesso total ao registro desses eventos, mesmo que eles já tenham sido consumidos pelo mesmo consumidor ou por outros consumidores. Os novos consumidores que ingressarem posteriormente também terão acesso a esses eventos antigos e poderão reproduzi-los a partir de qualquer ponto que desejarem.



O padrão de streaming de eventos é uma ótima opção para casos de uso de entrega confiável, e isso porque o message agent retém esses eventos indefinidamente ou por um período de tempo, o que nos permite recuperar esses eventos e auditá-los, se necessário. Também é uma escolha perfeita para o caso de uso de detecção de padrões ou anomalias, pois o consumidor precisa acessar todos os eventos passados em uma determinada janela.



O segundo padrão é o publisher subscriber ou pub sub. Em resumo, nesse padrão, os consumidores se inscrevem em uma fila de tópicos ou em um canal específico e recebem somente novos eventos após a inscrição. Nesse caso, os assinantes não têm acesso a eventos antigos e, assim que todos os assinantes atuais receberem o evento, o message agent normalmente o excluirá de sua fila. Além disso, se um novo assinante se registrar para eventos de um determinado tópico, ele será notificado apenas sobre novos eventos. Esse padrão é ideal quando o message agent é usado apenas como um armazenamento temporário ou um mecanismo de transmissão. Depois que os assinantes consomem os eventos, eles são normalmente transformados e armazenados permanentemente em um banco de dados ou são passados para outro serviço. Todos os cenários que se enquadram no buffer de transmissão "dispare e esqueça". Preocupar-se ou lidar com um fluxo infinito de eventos.



Os casos de uso são uma boa opção para esse padrão. Neste capítulo, aprenderemos alguns dos casos de uso mais comuns da arquitetura orientada por eventos. Esses casos de uso incluíam entrega confiável do tipo "dispare e esqueça" e um fluxo infinito de eventos. Detecção de anomalias e reconhecimento de padrões. Transmissão e buffering. Também mencionamos que nem todos os cenários são adequados para a arquitetura orientada por eventos. Portanto, em situações em que precisamos de uma resposta imediata contendo dados, ou se o caso de uso não justificar a complexidade e o custo de manter um message agent, devemos usar o modelo tradicional de Request-Response. Por fim, falamos sobre dois padrões de entrega de eventos. Esses padrões são o streaming de eventos e o padrão de assinatura do editor.



## Resumo:

## Casos de Uso para a Arquitetura Orientada a Eventos

Ações Assíncronas ("disparar e esquecer")
Ideal para operações em que o remetente não precisa de resposta imediata ou nenhuma. Exemplos:

Geração de relatórios enviados posteriormente ao usuário.

Registro de avaliações de produtos, onde apenas a confirmação de recebimento importa.

## Entrega Confiável
Essencial em transações críticas, como:

Pedidos em lojas online, garantindo que a solicitação seja processada ou o erro seja comunicado.

Transferências financeiras, onde perder mensagens é inaceitável.

Fluxos Contínuos de Dados
Adequado para cenários com eventos ou dados constantes, como:

Dados de localização de dispositivos móveis.

Informações de sensores IoT em dispositivos autônomos.

Detecção de Anomalias e Reconhecimento de Padrões
Útil para identificar tendências ou problemas a partir de sequências de eventos. Exemplos:

Monitoramento de solicitações por segundo para detectar picos ou falhas em sistemas.

Identificação de padrões para decisões em tempo real.

Alterações de Estado e Notificação
Quando serviços precisam notificar outros sobre mudanças de estado. Exemplo:

Cliques em anúncios gerando eventos processados por diversos serviços de forma independente.

Buffering para Picos de Tráfego
Ideal para lidar com sobrecarga momentânea, armazenando eventos em um intermediário até que possam ser processados. Exemplo:

Aumento repentino de postagens em redes sociais devido a eventos globais.



## Casos em que o Modelo de Request-Response é Preferível

Respostas Imediatas
Quando o usuário ou serviço precisa de dados de forma síncrona, como:

Exibição de páginas de produtos em lojas online.

Interações Simples
Quando o custo de configurar e gerenciar um sistema orientado a eventos supera os benefícios. Exemplo:

Operações triviais em que a complexidade adicional não é justificada.

## Combinação de Modelos

Na prática, uma arquitetura de microsserviços eficaz combina os dois estilos. É recomendável iniciar com um modelo de Request-Response e migrar partes críticas para a arquitetura orientada a eventos conforme necessário.



## Padrões de Entrega de Eventos

Streaming de Eventos
O message agent atua como um repositório, armazenando eventos para que consumidores possam acessá-los a qualquer momento, incluindo eventos passados.

## Uso Ideal:

Entrega confiável com retenção de eventos para auditoria.

Reconhecimento de padrões em uma sequência temporal.

Publisher-Subscriber (Pub/Sub)
Os consumidores recebem apenas novos eventos após a inscrição. Eventos antigos não são acessíveis, e o message agent os descarta após a entrega.

## Uso Ideal:

Cenários de "disparar e esquecer".

Transmissão de eventos temporários para processamento imediato ou armazenamento em outro local.



## Conclusão

Este capítulo destacou os casos mais comuns para a arquitetura orientada a eventos, como ações assíncronas, entrega confiável, detecção de anomalias e buffering. Também reforçou que cenários que requerem respostas imediatas ou possuem interações simples podem ser melhor atendidos pelo modelo de Request-Response. Por fim, discutimos os padrões de entrega de eventos, "streaming de eventos" e "pub/sub", e seus respectivos usos.





## Semântica de entrega de mensagens em arquitetura orientada a eventos



Neste capítulo, falaremos sobre entrega de mensagens, semântica em microsserviços e arquitetura orientada por eventos. Primeiro, ilustraremos o problema usando o modelo de comunicação simples de solicitação e resposta. Depois disso, ampliaremos nossa discussão para a arquitetura orientada por eventos. Em seguida, apresentaremos a semântica de entrega máxima uma vez e pelo menos uma vez (At least once). E, por fim, falaremos sobre a semântica de entrega exatamente uma vez (Exactly once), alguns equívocos sobre ela e como podemos alcançá-la em uma arquitetura orientada por eventos e de microsserviços.



Então, primeiro, vamos discutir o problema que estamos tentando resolver. Vamos imaginar que temos uma comunicação muito simples entre dois microsserviços. Em circunstâncias normais, o remetente envia a solicitação para o serviço receptor. O serviço receptor aceita a solicitação, processa-a e atualiza seu banco de dados. Após a conclusão desse processamento, ele envia uma resposta ao serviço de envio. No entanto, em alguns casos, podemos estar em uma situação em que o remetente nunca recebe essa resposta. Essa situação pode ocorrer se o destinatário nunca o recebeu de fato ou se não o recebeu, mas foi esmagado logo antes de processá-lo com sucesso. Como alternativa, ele pode tê-la processado com êxito e armazenado em um banco de dados, mas a resposta não chegou ao remetente. Portanto, como, do ponto de vista do remetente, nunca podemos dizer a diferença entre esses dois casos, o que devemos fazer? Devemos reenviar a solicitação, correndo o risco de o destinatário receber a mesma mensagem duas vezes? Ou não devemos reenviar a solicitação e correr o risco de perder esses dados?



Quando lidamos com a arquitetura orientada por eventos, temos o mesmo problema de entrega de eventos, mas é muito mais complexo do que o modelo de request-response, porque agora temos três entidades: o editor do evento, o message agent e o assinante ou consumidor. O editor pode produzir um evento para o message agent, mas essa solicitação pode ser perdida na rede, ou o message agent pode receber o evento e armazená-lo em seus registros. Mas a confirmação para o produtor se perde na rede. Da mesma forma, o message broker pode enviar o evento para o assinante, mas este nunca o recebe, ou o recebe, mas falha logo antes de processá-lo. Como alternativa, ele pode processá-lo com êxito, mas a confirmação é perdida na rede. Portanto, para lidar com essa situação, o editor, o message broker e o assinante precisam concordar com a semântica de entrega dos eventos com antecedência, antes de discutir essa semântica de entrega. É importante ressaltar que os conceitos discutidos nestea capítulo são universais e não são específicos de nenhuma tecnologia de message broker. No entanto, as configurações e garantias específicas variam de uma tecnologia para outra. A primeira semântica de entrega é o máximo. Uma vez que, nessa situação, não temos problemas com a possível perda de alguns dados, mas queremos evitar a duplicação de eventos quando usamos a semântica de entrega no máximo uma vez (At most once), dizemos ao nosso editor que, se ele não receber uma confirmação do message agent, não deverá reenviar o evento. Portanto, na melhor das hipóteses, se o evento chegou ao message agent, mas a confirmação simplesmente se perdeu na rede, não perderemos nenhum dado, mas se o message agent não recebeu a solicitação ou falhou antes de armazenar o evento, poderemos perder esse evento completamente. Além disso, dizemos ao assinante para confirmar que recebeu o evento antes de processá-lo ou armazená-lo em um banco de dados. Dessa forma, se o consumidor falhar e reiniciar depois de processar o evento, ainda estaremos bem porque esse evento já foi processado. Porém, se ele travar e reiniciar após o reconhecimento, mas antes de ter a chance de processá-lo, o assinante não receberá esse evento novamente, perdendo-o efetivamente.



Essa semântica de entrega é perfeita para cenários em que não há problema com alguma perda de dados e podemos extrapolar o que precisamos de outros eventos. Por exemplo, se formos um serviço de compartilhamento de carona e cada motorista nos enviar suas atualizações de localização, que armazenamos como eventos em nosso message broker, podemos nos dar ao luxo de perder alguns desses eventos, mas ter a mesma atualização de localização armazenada duas vezes ou processada duas vezes simplesmente não será um bom uso de nossos recursos. Essa semântica também nos proporciona a menor sobrecarga e a menor latência. Portanto, para o processamento em tempo real de eventos, como registros ou métricas de centenas de servidores em nuvem, essa semântica de fornecimento será a mais econômica.



Agora, a segunda opção é a semântica de entrega pelo menos uma vez (At least once). Nessa semântica, concordamos que, se um editor não receber uma confirmação em um determinado período de tempo, ele reenviará o evento para o message agent. Isso garante que nunca perderemos o evento, mas pode fazer com que o mesmo evento seja armazenado no message agent mais de uma vez. Da mesma forma, configuramos o assinante para processar primeiro o evento e, somente depois de concluído, enviar a confirmação de volta ao message agent. Dessa forma, se o assinante receber o evento, mas falhar antes de processá-lo e armazená-lo, ele receberá o mesmo evento novamente após ser reiniciado depois de recebê-lo pela segunda vez. Ele pode processá-lo novamente e, em seguida, enviar a confirmação. Quando o message broker receber essa confirmação, ele não a entregará mais ao mesmo assinante. No entanto, se o assinante falhar logo depois de processá-lo, mas antes de enviar a confirmação, ou se a confirmação for perdida na rede, o message broker reenviará o mesmo evento ao assinante depois que ele for reiniciado. Isso fará com que o assinante processe o mesmo evento duas vezes, mas o evento nunca será perdido.



Essa semântica de entrega é ideal para casos de uso em que a não entrega de determinados eventos pode resultar na perda de dados valiosos, mas alguma duplicação de dados é aceitável. Um bom exemplo desse caso de uso é se quisermos enviar a um usuário uma notificação push para seu celular sobre o envio do produto. Se, em alguns casos raros, enviarmos a mesma notificação ao usuário duas vezes, isso não será um grande problema. Mas definitivamente queremos notificar o usuário pelo menos uma vez (At least once).



Outro exemplo é quando o usuário deixa uma avaliação de um produto em nosso site. Nesse caso, como a avaliação está vinculada ao usuário e já temos uma lógica que permite que o usuário deixe uma avaliação de um produto apenas uma vez, essa avaliação será simplesmente substituída ou ignorada pelo nosso sistema.



Além da possível duplicação de eventos, essa semântica de entrega tem mais uma desvantagem, que é o aumento da latência. Quando o editor envia o evento para o message agent, ele terá que aguardar um determinado período de tempo para poder reenviar o mesmo evento. Isso pode ser da ordem de milissegundos ou até segundos, dependendo da configuração que definimos para o editor. Da mesma forma, o message agent terá de aguardar e permitir que o assinante envie de volta a confirmação antes de concluir que o assinante falhou ou que a confirmação foi perdida devido a essa possível latência adicional. Essa semântica de entrega não é uma boa opção para sistemas em tempo real ou de alto rendimento.



Agora vamos falar sobre a terceira semântica de entrega, que é a entrega exatamente uma vez (Exactly once). Essa é a semântica de entrega mais desejável, especialmente para casos de uso que envolvem transações financeiras. Infelizmente, isso é o mais difícil de conseguir e tem a maior sobrecarga e latência. Também vale a pena ressaltar que nem todas as tecnologias de message broker oferecem a semântica, e as que oferecem nem sempre oferecem o que você espera. Portanto, qualquer que seja a tecnologia que você decida usar, é importante ler a documentação com atenção, especialmente se estiver lidando com dados de impacto financeiro.



A ideia por trás da obtenção dessa semântica de entrega é a seguinte. Primeiro, no lado do editor, antes de enviar um evento para o message agent, precisamos obter o que chamamos de ID de potência do item ou um número de sequência exclusivo. Alguns message brokers podem gerar isso para nós internamente, enquanto em outros casos talvez seja necessário usar um serviço separado. A ideia é obter um identificador exclusivo que possamos enviar ao message agent junto com o evento. Agora, se o editor enviar o evento para o message agent e nunca receber uma confirmação, ele seguirá o mesmo procedimento da semântica de entrega pelo menos uma vez (At least once) e reenviará o evento com a mesma ID. Agora, se o message agent for aquele que forneceu esse ID exclusivo, ele verificará se um evento com o mesmo ID já está no registro. Se for, o evento será ignorado e, se não for, será adicionado ao registro. Isso permite obter a semântica de entrega exatamente uma vez (Exactly once) no lado do produtor, o que significa que nunca perdemos eventos e nunca acabamos com eventos duplicados.



Agora, há algo que possamos fazer no lado do assinante? Bem, vamos considerar o cenário mais comum em que o assinante recebe algum evento financeiro, como um evento de cobrança ou uma transferência de dinheiro entre contas, quando o assinante o recebe. Ele precisa processá-lo primeiro, talvez fazendo algumas validações ou cálculos, e depois colocá-lo no banco de dados. Nas situações em que a assinatura do evento inclui uma atualização de estado fora do message agent, o message agent não pode garantir mais do que pelo menos uma vez (At least once) a semântica de entrega, mesmo quando anuncia que suporta exatamente uma semântica de entrega. Nesse caso, depois que o assinante receber o evento do message agent, ele terá que processá-lo e armazená-lo no banco de dados e, em seguida, enviar uma confirmação ao message agent de que o evento foi processado com êxito. Quando o message broker receber essa confirmação, ela não será entregue novamente ao mesmo assinante. No entanto, se o assinante falhar depois de processá-lo e armazenar o evento, mas antes de enviar a confirmação, o message agent continuará esperando. E, depois que o período de espera expirar, ele presumirá que o evento não foi entregue. Portanto, quando a mesma instância do assinante for reiniciada ou uma nova instância for iniciada, o agente de mensagens enviará o mesmo evento ao assinante, o que resultará no processamento do mesmo evento duas vezes. Para evitar essa duplicação, precisamos adicionar manualmente um ID de potência do item ao registro do evento em nosso banco de dados. Se o mesmo evento for processado novamente, poderemos rejeitá-lo programaticamente. Se outro evento com o mesmo ID de potência de item já estiver presente no banco de dados. Quero enfatizar que isso é algo que precisamos fazer nós mesmos e não é algo que o message broker possa fazer para que alcancemos a semântica de entrega exatamente uma vez (Exactly once). Podemos aproveitar a mesma identificação de idempotência que acompanha o evento do message agent.



Neste capítulo, aprenderemos sobre o potencial da entrega não confiável de eventos e os problemas que ela pode criar. Se não projetarmos nosso sistema antecipadamente para lidar com isso, então introduzimos três semânticas de event sourcing para implementar em uma arquitetura orientada por eventos. A primeira e mais simples foi a semântica de entrega no máximo uma vez (At most once), em que podemos perder alguns dados, mas nunca haverá duplicação de dados. A segunda, mais complexa, foi a semântica de entrega pelo menos uma vez (At least once). Com essa abordagem, introduzimos mais latência no sistema, mas garantimos que os eventos nunca serão perdidos. No entanto, é possível processar o mesmo evento várias vezes. Por fim, falamos sobre a semântica de entrega exatamente uma vez (Exactly once), que tem a maior latência e sobrecarga, mas garante que cada evento seja produzido uma vez para o message agent e seja consumido e processado apenas uma vez pelo assinante.



## Resumo:

## O Problema da Comunicação entre Microsserviços

Imagine dois microsserviços: o remetente envia uma solicitação ao receptor, que a processa, atualiza o banco de dados e retorna uma resposta. Entretanto, problemas como perda de mensagens ou falhas antes da confirmação podem ocorrer. O remetente, incapaz de distinguir entre falhas, enfrenta duas escolhas: reenviar a mensagem (risco de duplicação) ou não reenviar (risco de perda de dados).



## Entrega em Arquiteturas Orientadas a Eventos

Na arquitetura orientada a eventos, a complexidade aumenta devido às três entidades envolvidas: produtor, agente de mensagens (message broker) e consumidor. A entrega confiável depende de como estas partes lidam com falhas e confirmações. Vamos analisar as semânticas de entrega disponíveis.



## Semântica de Entrega "Máximo uma vez” (At most once)

Nessa abordagem, o produtor não reenviará eventos sem confirmação do agente. Isso reduz a duplicação de eventos, mas aceita perdas em caso de falhas. O consumidor confirma o recebimento antes do processamento, evitando duplicações em reinicializações.

Cenário Ideal: Processos onde perdas são toleráveis, mas duplicações não, como atualizações frequentes e sobrepostas, por exemplo, localização em tempo real de motoristas em um serviço de transporte.

## Vantagens:

Menor sobrecarga e latência.

Adequada para processamento de eventos em tempo real.

## Desvantagens:

Dados podem ser perdidos em falhas.



## Semântica de Entrega "Pelo menos uma vez” (At least once)

Aqui, o produtor reenviará eventos sem confirmação em um prazo definido, garantindo que nenhum evento seja perdido. No entanto, podem ocorrer duplicações. O consumidor processa eventos antes de enviar confirmações, minimizando perdas, mas aumentando a probabilidade de reprocessamento em falhas.

Cenário Ideal: Sistemas onde a perda de eventos é crítica, mas a duplicação é aceitável, como notificações push ou avaliações de usuários.

## Vantagens:

Garantia contra perda de eventos.

## Desvantagens:

Maior latência devido ao tempo de espera por confirmações.

Risco de duplicação exige lógica de idempotência.



## Semântica de Entrega "Exatamente uma vez” (Exactly once)

Essa semântica é a mais desejada, especialmente para dados financeiros, mas também a mais complexa. Ela depende de identificadores exclusivos (IDs) gerados pelo agente ou pelo produtor. No caso de falhas, eventos duplicados podem ser detectados e ignorados pelo sistema.

Cenário Ideal: Transações financeiras ou dados críticos, onde duplicações ou perdas são inaceitáveis.

## Vantagens:

Eventos não são perdidos nem duplicados.

## Desvantagens:

Alta latência e sobrecarga.

Requer implementação manual de idempotência no consumidor.



## Conclusão

Neste capítulo, exploramos os desafios de entrega de eventos em arquiteturas orientadas a eventos. Para mitigar riscos, analisamos três semânticas de entrega:

máximo uma vez (At most once): simples e eficiente para sistemas tolerantes a perdas.

pelo menos uma vez (At least once): evita perdas, mas pode introduzir duplicações.

exatamente uma vez (Exactly once): ideal para dados críticos, mas com maior complexidade e custo.

Cada abordagem tem vantagens e desvantagens, e a escolha deve considerar os requisitos do sistema, a criticidade dos dados e o impacto de duplicações ou perdas.





## Microsserviços Orientados a Eventos - Padrões de Design



## Saga Pattern



Neste capítulo, aprenderemos o primeiro padrão em que podemos usar microsserviços e arquitetura orientada por eventos. Esse padrão é chamado de padrão saga. Primeiro, vamos entender o problema que estamos resolvendo com esse padrão. Em seguida, apresentaremos o padrão em si. Mais adiante, discutiremos duas maneiras de implementar esse padrão usando microsserviços e arquitetura orientada por eventos. Portanto, vamos começar definindo o problema que estamos tentando resolver.



Como lembrete, um dos principais princípios dos microsserviços é um banco de dados por microsserviço. Essa separação nos permitiu desacoplar as equipes e as bases de código de cada microsserviço da empresa. Usando esse princípio, o banco de dados é apenas um detalhe de implementação dessa equipe de microsserviços e não é exposto externamente a outros microsserviços de forma alguma. Isso permite que cada equipe use a tecnologia de banco de dados certa para sua carga de trabalho e, o que é mais importante, itere e faça alterações nela sem precisar comunicar ou coordenar essas alterações com ninguém. Entretanto, como todos sabemos, tudo na arquitetura de software é uma troca. Portanto, essa dissociação introduz um novo problema. Quando tínhamos um único aplicativo monolítico com todos os seus dados armazenados em um único banco de dados, tínhamos a capacidade de modificar várias fontes de dados atomicamente como parte de uma única transação. Como lembrete, uma transação garante que, para um observador externo, uma sequência de operações apareça como uma única operação, mesmo que essas operações possam envolver vários registros em uma tabela ou, o que é mais importante, vários registros em tabelas diferentes. Isso é o que normalmente chamamos de garantias de transação ACID, onde ACID significa consistência de atomicidade, isolamento e durabilidade.



No entanto, quando migramos para microsserviços, não temos mais um banco de dados para realizar essa transação. Pior ainda, cada operação nesse fluxo de trabalho é executada por um microsserviço separado, que só tem conhecimento de sua parte do fluxo de trabalho. Portanto, o padrão saga nos ajuda a realizar uma transação distribuída que abrange vários microsserviços e bancos de dados.



Nesse padrão, executamos as operações individuais que fazem parte dessa transação como uma sequência de transações locais em cada banco de dados. Cada operação bem-sucedida aciona a próxima operação na sequência e, se uma determinada operação falhar, o padrão da saga reverte a operação ou as operações anteriores aplicando operações de compensação que têm o efeito oposto ao das operações originais.



Em geral, há duas maneiras de implementar esse padrão. A primeira é usar um serviço de gerenciamento de fluxo de trabalho com estado que orquestra toda a transação. O único objetivo desse serviço é orquestrar a transação na ordem correta e também aplicar as operações de compensação na ordem oposta se as coisas derem errado.



Para ilustrar como isso funciona, vamos usar o cenário de um serviço de reserva de férias que oferece pacotes de férias aos clientes. Um pacote de férias inclui um voo de ida e volta para o destino de férias, depois uma reserva de hotel e um aluguel de carro para as datas determinadas. Esse é um exemplo perfeito de uma transação, pois só podemos permitir um de dois cenários, ou temos todos os componentes das férias reservados e pagos, o que torna a transação um sucesso, ou se alguma das partes falhar, a transação inteira é considerada uma falha e é abortada.



Então, vamos ver como podemos implementá-lo usando o serviço de gerenciamento de fluxo de trabalho em nossa arquitetura de microsserviços. Em nosso serviço de reserva de férias, podemos ter os seguintes microsserviços. O serviço de pagamento, o serviço de reserva de voos. O serviço de reserva de hotéis, o serviço de aluguel de carros e o serviço de pedidos. Portanto, a primeira coisa que precisamos fazer é definir a ordem do fluxo de trabalho dentro do fluxo de trabalho ou serviço de restauração. As operações dentro desse fluxo de trabalho também são comumente chamadas de atividades. Nesse caso, podemos fazer isso de várias maneiras, mas digamos que primeiro garantimos o pagamento do usuário pelo valor total das férias. Em seguida, reservamos os voos de ida e volta para o destino de férias. Considerando as preferências de assento que o usuário nos forneceu. Em seguida, fazemos a reserva de um quarto de hotel para o usuário. Depois disso, fazemos uma reserva com a empresa de aluguel de carros para as datas determinadas e, por fim, adicionamos uma entrada de pedido para o usuário em questão com todos os detalhes sobre a reserva. Depois de definirmos a ordem das atividades para o cenário bem-sucedido, também precisamos adicionar as operações de compensação para cada atividade, caso seja necessário desfazê-la. Portanto, para garantir o pagamento do usuário, a operação de compensação seria creditar a conta ou o cartão de crédito do usuário com o mesmo valor. A operação de compensação para a reserva de voo é cancelar os voos de e para o destino de férias. A operação para desfazer a reserva do hotel é cancelar a reserva do hotel e desfazer a reserva do carro. Também precisamos simplesmente cancelá-lo. E, embora a última operação na sequência seja inserir os detalhes do pedido, ainda precisamos definir a operação de compensação para ela, caso queiramos adicionar mais operações a esse fluxo em algum momento no futuro. Portanto, a operação de compensação nesse caso seria atualizar a ordem para um status de cancelamento.



Agora, a segunda etapa é implementar as operações de fluxo de trabalho, para chamar a API dos microsserviços correspondentes. E a terceira etapa é implementar as operações de compensação para chamar as mesmas APIs ou APIs diferentes desses microsserviços, dependendo da operação. E é isso. Agora, quando um usuário quiser reservar férias conosco, ele fará uma solicitação ao nosso serviço de aplicativo da Web. O serviço, por sua vez, mostrará ao usuário as opções disponíveis e solicitará que ele forneça suas datas preferidas e outros detalhes. Quando o usuário enviar a solicitação de reserva de férias, essa solicitação passará pelo gateway da API para o serviço de orquestração do fluxo de trabalho. O serviço iniciará o fluxo de trabalho passo a passo. Se tudo correr bem, o usuário será cobrado. Os voos são reservados, o quarto de hotel é reservado, o aluguel do carro no destino de férias é providenciado e, assim que o serviço de pedidos for atualizado, o serviço de orquestração retornará uma confirmação ao usuário. No entanto, se algo der errado, toda a transação terá que ser abortada e o usuário receberá um erro.



Por exemplo, digamos que, no momento em que o nosso serviço de orquestração de fluxo de trabalho fizer a solicitação ao serviço de aluguel de carros, a empresa não tenha mais carros naquele local para as datas determinadas. Nesse ponto do fluxo de trabalho, o usuário já foi cobrado por todas as férias, incluindo o carro, os voos e o hotel, que também já estavam reservados. Portanto, o serviço de orquestração de fluxo de trabalho aplicará as operações de compensação, chamando o serviço de reserva de hotel e o serviço de voo para cancelar essas reservas. Em seguida, ele creditaria o valor total no cartão de crédito do usuário. E, por fim, ele enviará um erro ao usuário explicando o que deu errado.







A segunda maneira de implementar o padrão saga é usar um modelo puramente orientado por eventos usando a arquitetura orientada por eventos. Nesse método, removemos o serviço de orquestração do fluxo de trabalho e delegamos o gerenciamento de todo o fluxo de trabalho aos próprios microsserviços. Para isso, a comunicação entre os microsserviços é feita de forma assíncrona por meio de eventos publicados em um message broker para compensar a remoção do serviço de orquestração. Agora, cada microsserviço precisa saber sua função no fluxo de trabalho.



Em outras palavras, ele precisa saber para onde enviar um evento quando a operação for bem-sucedida e para onde precisa enviar um evento em caso de falha. E ele precisa acionar a operação de compensação para o serviço anterior na sequência. Para demonstrar isso, vamos voltar ao exemplo do serviço de reserva de férias. Agora, quando um usuário fizer uma solicitação de pedido de férias, essa solicitação irá diretamente para o serviço de pagamento, pois o fluxo de trabalho agora é assíncrono. O serviço de pagamento responderá ao usuário imediatamente. Em seguida, ele iniciará a sequência cobrando o usuário e enviando um evento correspondente ao agente de mensagens. O serviço de reserva de voo pegará esse evento, fará a reserva e, se for bem-sucedido, emitirá outro evento para um tópico no qual o serviço de reserva de hotel está inscrito. Supondo que todas as operações sejam bem-sucedidas, toda essa cadeia de eventos acabará levando o serviço de pedidos a receber o evento de que todas as reservas foram concluídas, de modo que ele atualizará seu próprio banco de dados. No entanto, observe que, como usamos uma arquitetura assíncrona orientada por eventos, a resposta ao usuário sobre o sucesso ou a falha também precisa ser assíncrona. Portanto, para isso, publicaremos outro evento em outro serviço chamado Notification Service. O serviço notificará o usuário sobre o resultado do fluxo de trabalho por meio de um e-mail ou de uma notificação por push.







Agora vamos ver como funciona a implementação desse padrão saga. Se uma das operações falhar e precisarmos reverter a transação usando o mesmo exemplo anterior. Digamos que o faturamento do usuário, a reserva do voo e a reserva do hotel tenham sido bem-sucedidos. No entanto, por qualquer motivo, o serviço de reserva de carro não pôde fazer a reserva. Nesse caso, para acionar a reversão da transação, ele publicará um evento. Para outro tópico que indique uma falha na realização da reserva do carro. Agora, o serviço de reserva de hotel, que está inscrito nesse tópico, captará esse evento e saberá que deve desfazer sua operação cancelando a reserva do hotel. Em seguida, ele publicará outro evento em outro tópico no qual o serviço de reserva de voo está inscrito. Da mesma forma, o serviço de reserva de voos cancelará os voos e publicará outro evento que o serviço de pagamento irá captar. De forma semelhante, o serviço de pagamento creditará o usuário e emitirá outro evento para o tópico no qual o serviço de notificação está inscrito. Esse evento indica que toda a transação é uma falha. Agora, o Notification Service captará esse evento e notificará o usuário com todos os detalhes e as próximas etapas que ele precisa realizar.







Portanto, agora que aprendemos sobre o padrão Saga e suas duas implementações, vamos resumir rapidamente o que aprendemos neste capítulo.



Neste capítulo, aprenderemos sobre a perda de garantias de transações de ativos ao migrar de um aplicativo monolítico com um único banco de dados para uma arquitetura de microsserviços. Resolvemos esse problema usando o padrão saga, que divide a transação em uma sequência de operações que cada microsserviço executa em caso de sucesso e uma sequência de operações de compensação executadas em ordem inversa em caso de falha. Mais adiante, discutiremos as duas maneiras de implementar esse padrão. A primeira usou um serviço de gerenciamento de fluxo de trabalho com estado para orquestrar a transação, e a segunda usa a arquitetura orientada por eventos, em que cada microsserviço é responsável por acionar a próxima operação na sequência ou acionar a operação de compensação no microsserviço anterior em caso de falha.



## Resumo:

Neste capítulo, exploraremos o padrão Saga, que é uma solução para implementar transações distribuídas em arquiteturas de microsserviços e orientadas por eventos. O objetivo deste padrão é resolver problemas relacionados à perda de garantias de transações ACID ao migrar de uma arquitetura monolítica para uma arquitetura de microsserviços.

## 1. O Problema a Ser Resolvido

Princípio do microsserviço: Cada microsserviço deve ter seu próprio banco de dados, desacoplando as equipes e as bases de código.

Vantagens: Permite que cada equipe escolha a tecnologia de banco de dados ideal para sua carga de trabalho e modifique seu banco sem coordenação externa.

Desafio: A migração para microsserviços remove a possibilidade de realizar transações atômicas que envolvam várias fontes de dados em um único banco de dados.

## 2. O Conceito de Transações ACID

ACID: Garante Atomicidade, Consistência, Isolamento e Durabilidade em uma transação.

Problema: Ao usar microsserviços, perdemos o controle centralizado, impossibilitando transações atômicas entre múltiplos microsserviços e bancos de dados.

## 3. Como o Padrão Saga Resolve o Problema

Transações distribuídas: O padrão Saga divide uma transação em várias transações locais, cada uma executada por um microsserviço.

Operações de compensação: Se uma operação falhar, o padrão Saga aplica operações de compensação para reverter as transações anteriores.

Garantia de sucesso ou falha: Se todas as operações forem bem-sucedidas, a transação é concluída. Se algo falhar, a transação é revertida.

## 4. Implementação do Padrão Saga

## Existem duas maneiras principais de implementar o padrão Saga:

## 4.1 Orquestração com Serviço de Fluxo de Trabalho

Visão geral: Um serviço centralizado orquestra o fluxo de trabalho, gerenciando as transações e as compensações.

Exemplo: Serviço de reserva de férias, que inclui pagamento, voo, hotel e aluguel de carro.

## Etapas do fluxo de trabalho:

Garantir pagamento.

Reservar voo.

Reservar hotel.

Reservar aluguel de carro.

Criar pedido.

## Operações de compensação:

Se o pagamento falhar, reverter o pagamento.

Se o voo falhar, cancelar a reserva do voo.

Se o hotel falhar, cancelar a reserva do hotel.

Se o aluguel de carro falhar, cancelar a reserva do carro.

Se o pedido falhar, atualizar o status para “cancelado”.

## Fluxo de execução:

O serviço de orquestração inicia a transação.

Caso tudo ocorra bem, o serviço de pedidos é atualizado e o usuário é notificado.

Se algo der errado (ex. falta de carros no aluguel), o serviço de orquestração aplica as compensações (cancelando reservas, revertendo pagamentos).

## 4.2 Arquitetura Orientada por Eventos

Visão geral: Cada microsserviço é responsável por gerenciar seu próprio fluxo de trabalho, comunicando-se de forma assíncrona por meio de eventos.

## Eventos:

O serviço de pagamento inicia a transação e emite um evento.

O serviço de reserva de voo processa o evento e, se bem-sucedido, emite outro evento para o serviço de reserva de hotel.

O serviço de hotel emite um evento para o serviço de aluguel de carros, e assim por diante.

Se algo falhar (ex. falha no aluguel de carro), o serviço de reserva de carro emite um evento de erro.

## Reversão de transação:

O evento de erro acionará uma série de eventos de compensação.

Cada serviço, ao receber o evento de erro, reverterá sua operação (ex. cancelando a reserva de voo, revertendo o pagamento).

O serviço de notificações enviará uma notificação ao usuário, informando sobre a falha e as ações corretivas tomadas.

## 5. Comparando as Abordagens

## Orquestração com fluxo de trabalho:

Centraliza o controle, tornando o fluxo de execução mais fácil de gerenciar.

Ideal para cenários em que o controle centralizado é necessário.

## Arquitetura orientada por eventos:

Mais escalável e desacoplada.

Cada microsserviço gerencia seu próprio estado e decisões.

## 6. Conclusão

Padrão Saga: Essencial para garantir transações distribuídas em microsserviços.

Implementação: Pode ser feita por orquestração com um serviço centralizado ou por eventos assíncronos, dependendo dos requisitos de flexibilidade e escalabilidade.

Benefício: Soluciona a perda de garantias de transações ACID ao dividir a transação em partes gerenciáveis e permitir a compensação em caso de falhas.



## CQRS Pattern



Neste capítulo, aprenderemos outro padrão muito poderoso em que usamos a combinação de microsserviços e arquitetura orientada por eventos. Esse padrão é chamado de CQRS. Primeiro, teremos uma introdução geral ao padrão dos search engines. Depois disso, discutiremos dois tipos de casos de uso em que esse padrão pode beneficiar muito os sistemas de grande escala projetados com a arquitetura de microsserviços. E concluiremos com um exemplo real desse padrão.



Então, primeiro, o que são os search engines? CQRS significa Command and Query Responsibility Segregation (Segregação de responsabilidade de comando e consulta) em um sistema típico que envolve dados armazenados em um banco de dados. Podemos agrupar as possíveis operações nesses dados em dois tipos.



O primeiro tipo é um comando. Um comando é uma ação. Executamos isso resultando em alteração de dados em nosso sistema. Essas ações envolvem a inserção de novos registros, como a adição de um novo usuário, atualizações de registros existentes, como a edição de uma avaliação de produto ou a atualização do número de telefone do usuário, ou a exclusão de registros, como quando um usuário exclui seu próprio comentário em uma plataforma de mídia social.



O segundo tipo de operação é uma consulta, em contraste com o comando. Uma consulta apenas lê dados do banco de dados, mas não os altera. Nosso sistema pode retornar os dados como estão ou realizar uma transformação simples nesses dados, como classificação ou agregação. No entanto, os dados dentro do banco de dados nunca serão alterados devido a essa consulta. Um exemplo de consulta seria uma solicitação para mostrar todos os produtos em uma determinada categoria em ordem alfabética. Quando usamos a segregação de responsabilidade de comando (segregation of command responsibility) e consulta em microsserviços, basicamente separamos ou segregamos o código e o armazenamento da parte de comando do nosso sistema. Na parte de consulta do nosso sistema, todas as alterações de dados passam pelo serviço de comando (command service) para o banco de dados de comando e todas as consultas passam pelo serviço de consulta para o banco de dados de consulta, que contém uma cópia dos dados no banco de dados de comando para manter os bancos de dados de comando e de consulta sincronizados.



Usamos a arquitetura orientada por eventos. Tudo o que precisamos fazer é adicionar um intermediário de mensagens entre o serviço de comando (command service) e o serviço de consulta. E toda vez que o serviço de comando (command service) recebe uma solicitação que altera os dados em seu banco de dados, ele também publica um evento no agente de mensagens que o serviço de consulta pode consumir. Quando o serviço de consulta recebe esse evento, ele atualiza seu próprio banco de dados com os novos dados.



Agora, o padrão tem dois casos de uso principais na arquitetura de microsserviços. A primeira é a separação das preocupações entre as cargas de trabalho de comando e de consulta em termos de lógica comercial e desempenho. Quando usamos o secures para separar a parte de comando do nosso sistema da parte de consulta em bancos de dados e serviços separados, podemos obter muitos benefícios. Primeiro, esse padrão combina muito bem com o princípio de responsabilidade única para microsserviços. Isso nos permite ter toda a complexidade de gerenciamento, permissões de gravação, validação de entrada e outras lógicas comerciais no serviço de comando (command service), mantendo o serviço de consulta limpo, simples e focado na melhor maneira de apresentar os dados ao usuário.



Essa separação de preocupações no lado do serviço também nos permite evoluir facilmente cada parte de forma independente, usando o modelo de dados ideal em nossa linguagem de programação para cada carga de trabalho. Além disso, se apenas uma parte, por exemplo, o serviço de comando (command service), for atualizada com uma nova lógica comercial ou de validação, o lado da consulta não precisará ser testado novamente ou reimplantado, pois não foi alterado.



Além da separação de preocupações, também obtemos benefícios de desempenho muito importantes. Como todas as operações do tipo comando que envolvem alterações de dados vão para o banco de dados de comandos. Podemos usar o esquema de estrutura e a tecnologia de banco de dados mais adequados para operações de gravação.



O banco de dados de consulta. Podemos organizar nossos dados para tornar essas consultas muito eficientes. Especificamente para as operações de leitura. E também podemos escolher a tecnologia e a configuração de banco de dados mais adequadas para cargas de trabalho com uso intensivo de leitura, que normalmente são muito diferentes das usadas para cargas de trabalho com uso intensivo de gravação. Basicamente podemos otimizar nosso sistema para ambos os tipos de operações, o que, de outra forma, seria impossível. Se tivéssemos apenas um banco de dados para operações de comando e consulta. Em termos de escalabilidade, também obtemos muitos benefícios. Por exemplo, podemos ajustar o número de instâncias para cada microsserviço, dependendo do tráfego. E como estamos lidando com bancos de dados distribuídos, também podemos ajustar o número de instâncias de banco de dados para cada banco de dados, dependendo da taxa de operações que obtemos de cada tipo.







Agora, o segundo tipo de caso de uso do padrão seguro está resolvendo outro problema da aplicação do princípio de um banco de dados por microsserviço, que é a perda da capacidade de unir dados de fontes diferentes. Quando tínhamos todas as nossas tabelas de dados em um único banco de dados relacional, podíamos realizar com relativa facilidade operações conjuntas entre várias tabelas. No entanto, quando dividimos nosso aplicativo monolítico em microsserviços, cada um com seu próprio banco de dados, não temos mais essa opção. Portanto, agora, para unir os dados, primeiro precisamos fazer uma chamada de API para cada um desses dois microsserviços. Em seguida, cada microsserviço obterá os dados relevantes de seu próprio banco de dados e os retornará ao chamador. E somente depois de analisarmos e formatarmos os dados dos dois microsserviços diferentes é que poderemos uni-los programaticamente em uma única exibição. Essa operação de união programática pode ser muito difícil, propensa a erros e, o mais importante, muito lenta. Obviamente, essa sobrecarga é absolutamente inaceitável se estivermos tentando mostrar esses dados ao usuário em um navegador ou em um aplicativo móvel. Portanto, para resolver esse problema, seguiremos o padrão e criaremos um novo microsserviço com um banco de dados otimizado para leitura.



Esse microsserviço receberá apenas solicitações de consulta para os dados específicos que estamos tentando obter para o usuário dentro do banco de dados desse novo microsserviço de consulta. Armazenaremos uma visualização conjunta de todos os dados de ambos os microsserviços, formatada de forma ideal para leitura ou consulta para criar e atualizar essa visualização. Vamos adicionar um message broker em que o microsserviço A e o microsserviço B possam publicar um evento sempre que alterarem seus dados. Portanto, agora, sempre que os dados forem alterados no microsserviço A, por exemplo, esse microsserviço também publicará um evento no agente de mensagens. O serviço de consulta captará esse evento e atualizará sua exibição conjunta com os novos dados. Da mesma forma, se uma solicitação de alteração de dados for enviada ao microsserviço B, esse microsserviço também publicará um evento para o serviço de consulta depois de atualizar seu próprio banco de dados. E assim que o serviço de consulta consumir esse evento, ele atualizará sua exibição para refletir a nova alteração. Agora, todas as solicitações de consulta que exigem uma visualização conjunta dos dados do microsserviço A e do microsserviço B simplesmente irão para o serviço de consulta, e o serviço de consulta pode simplesmente retorná-los com o mínimo de formatação ou filtragem. Portanto, o ganho de desempenho para o usuário ou qualquer outro serviço que chame a API do serviço de consulta pode ser bastante substancial.



Uma ressalva importante com os search engines, já que agora só podemos garantir a consistência eventual entre as operações de leitura e de direito. Isso significa que, nesse intervalo de tempo entre a alteração dos dados e o banco de dados de comando e a atualização no banco de dados de consulta, determinadas operações de leitura verão os dados antigos. Portanto, agora que entendemos os princípios e os benefícios do padrão CQRS, vamos demonstrá-lo com um exemplo real.





Digamos que tenhamos um serviço on-line que forneça avaliações de empresas por meio de crowdsourcing, como restaurantes, padarias e carros, concessionárias, salões de cabeleireiro e assim por diante. Por exemplo, um usuário que janta em um restaurante de sushi pode usar nosso aplicativo para deixar uma avaliação e uma classificação descrevendo sua experiência nesse estabelecimento comercial. Posteriormente, com base em todas essas avaliações de usuários diferentes. Qualquer pessoa pode abrir nosso aplicativo e procurar um restaurante de sushi em uma determinada área. Nosso sistema, por sua vez, retornará uma lista de restaurantes classificados pelo número de avaliações, classificação média e relevância para as palavras-chave que o usuário digitou em sua pesquisa. Supondo que usemos a decomposição por domínio, devemos ter os seguintes microsserviços. No entanto, essa arquitetura atual tem alguns problemas e requisitos conflitantes. Primeiro, no lado do comando, temos regras comerciais muito rígidas sobre quem pode adicionar ou atualizar uma informação comercial. Por exemplo, precisamos garantir que somente os proprietários verificados de uma empresa possam atualizar seu site, endereço, número de telefone e outros detalhes. Da mesma forma, quando um usuário visita uma empresa e deseja deixar uma avaliação, podemos ter muita validação e lógica comercial no serviço de avaliação. Por exemplo, precisamos autenticar o usuário para garantir que não se trata de um bot que deixa avaliações falsas. Também queremos garantir que o usuário não tenha deixado uma avaliação da mesma empresa recentemente e, se tiver deixado, devemos solicitar que ele atualize a avaliação existente em vez de deixar uma nova avaliação. Também precisamos validar se o texto da avaliação e a classificação por estrelas são entradas válidas. Do ponto de vista do desempenho, temos mudanças muito pouco frequentes nas informações comerciais. Por outro lado, recebemos muitas avaliações diariamente, portanto, o serviço de avaliação precisa ter um esquema de banco de dados e uma tecnologia otimizada para operações de gravação.



Agora vamos dar uma olhada na parte de consulta do nosso sistema. Quando um usuário pesquisa uma empresa, como um restaurante de sushi ou uma padaria vegana, precisamos unir os dados do serviço de negócios e do serviço de avaliação. Isso significa que o serviço comercial deverá retornar todas as empresas do sistema que correspondam à consulta de pesquisa e, em seguida, precisaremos solicitar todas as classificações de cada empresa para que possamos calcular e classificar essas empresas adequadamente. Como podemos ver, essa operação pode ser extremamente lenta e ineficiente. Para resolver esse problema, podemos usar o padrão de descanso seguro (safe rest pattern) e introduzir outro serviço chamado Business Search Service.



O serviço terá um banco de dados otimizado para leitura especial com um mecanismo de pesquisa de texto projetado especificamente para consultas de texto. Agora, qualquer operação para adicionar um novo negócio ou atualizar um negócio existente no serviço de negócios será publicada como um evento no serviço de pesquisa de negócios. O serviço Business Search indexará seu nome, descrição e metadados e os colocará em seu banco de dados. Da mesma forma, sempre que uma avaliação for enviada e aprovada pelo serviço de avaliação, ela também será publicada como um evento em um tópico correspondente no agente de mensagens. O Business Search Service juntará essa avaliação à empresa correspondente e recalculará sua nova classificação média. Portanto, agora qualquer solicitação de pesquisa passará pela parte de consulta do nosso sistema para o serviço de pesquisa comercial. O serviço é totalmente livre de autenticação de validação ou de qualquer lógica comercial complexa. Tudo o que ele faz é analisar e formatar a solicitação e passá-la para o banco de dados de pesquisa de texto e, quando obtiver o resultado, retornará uma lista de todas as empresas classificadas pela relevância para a consulta de pesquisa e a classificação com base em uma fórmula predefinida.







Neste capítulo, aprenderemos outro padrão que combina microsserviços e arquitetura orientada por eventos usando search engines. Temos muitos benefícios para os microsserviços, como a separação de preocupações, maior desempenho para operações de leitura e gravação e maior escalabilidade. Além disso, com o uso de search engines, resolvemos o problema de unir dados de vários microsserviços, o que, de outra forma, seria muito difícil alcançar de forma eficiente e eficaz. E, por fim, demonstramos o uso da segurança em um exemplo real.



## Resumo:

## 1. O Que É o Padrão CQRS?

Definição: O padrão CQRS separa as responsabilidades de comando (ações que alteram dados) e consulta (ações que apenas leem dados) em sistemas que utilizam banco de dados.

## Operações de comando:

## Alteram o estado do sistema, como:

Inserção de registros (ex.: adicionar um novo usuário).

Atualização de registros existentes (ex.: editar uma avaliação de produto).

Exclusão de registros (ex.: deletar um comentário de uma rede social).

## Operações de consulta:

Apenas leem os dados, sem alterá-los.

## Exemplos:

Listar produtos de uma categoria em ordem alfabética.

Realizar agregações ou filtragens.



## 2. Como Funciona o CQRS?

## Separação de responsabilidades:

## Serviço de comando:

Realiza alterações nos dados.

Atualiza o banco de dados de comandos.

Publica eventos em um intermediário de mensagens.

## Serviço de consulta:

Consome eventos do intermediário de mensagens.

Atualiza seu banco de dados com uma cópia otimizada para leitura.

Retorna dados diretamente aos consumidores.



## 3. Benefícios do Padrão CQRS

## Separação de Preocupações:

Lógica de negócio de comandos é isolada do processamento de consultas.

Serviços mais simples, limpos e focados em suas responsabilidades.

## Evolução Independente:

Serviços de comando e consulta podem evoluir de forma independente.

Modelos de dados e tecnologias otimizados para suas respectivas cargas de trabalho.

## Desempenho Otimizado:

## Banco de dados de comandos:

Focado em operações de gravação.

## Banco de dados de consultas:

Organizado para leituras rápidas e eficientes.

## Escalabilidade:

Serviços e bancos de dados podem ser escalados separadamente.

Ajustes de infraestrutura de acordo com o volume de tráfego de cada operação.



## 4. Casos de Uso do CQRS em Microsserviços

## Otimização de Operações de Leitura e Escrita:

Separar comandos e consultas permite otimizar cada operação com tecnologias e esquemas de banco apropriados.

Exemplo: Serviços de alto tráfego de leitura podem usar bancos especializados em busca, enquanto os de escrita utilizam bancos otimizados para transações.

## Unificação de Dados em Sistemas Distribuídos:

## Resolução do problema de união de dados:

Sistemas monolíticos permitem operações conjuntas entre tabelas em um único banco.

Em microsserviços, a união de dados exige integração de APIs, o que pode ser lento e propenso a erros.

## Solução com CQRS:

Criar um serviço de consulta com um banco otimizado para leitura.

Armazenar uma visualização unificada de dados de múltiplos microsserviços.

Atualizar essa visualização por eventos publicados pelos serviços de comando.



## 5. Considerações Importantes

## Consistência Eventual:

Operações de leitura podem apresentar dados desatualizados durante o intervalo entre a alteração no banco de comandos e a sincronização no banco de consultas.

É essencial garantir que os sistemas consumidores estejam preparados para lidar com essa característica.



## 6. Exemplo Real: Sistema de Avaliações por Crowdsourcing

## Contexto:

Um serviço online permite que usuários deixem avaliações de empresas (ex.: restaurantes, padarias).

Usuários podem buscar empresas e classificá-las com base em critérios como número de avaliações e relevância.

## Desafios:

## Comando:

## Garantir validação e lógica comercial rigorosa:

Apenas proprietários podem atualizar informações de empresas.

Avaliações precisam ser validadas e autenticar usuários.

Banco de dados otimizado para operações de gravação.

## Consulta:

Necessidade de unir dados de diferentes microsserviços (ex.: empresas e avaliações).

Operações de consulta precisam ser rápidas e eficientes.

## Solução com CQRS:

## Criar um serviço de busca de negócios:

Banco de dados otimizado para leitura, com suporte a busca de texto.

Atualizações realizadas por eventos publicados pelos serviços de comando (ex.: serviços de empresas e de avaliações).

## Fluxo:

O serviço de empresa publica eventos ao alterar dados.

O serviço de avaliações publica eventos ao receber novas avaliações.

O serviço de busca consome eventos e mantém uma visualização atualizada.

Consultas são direcionadas ao serviço de busca, que retorna os dados de forma eficiente.



## Conclusão

## O padrão CQRS oferece soluções práticas para arquiteturas de microsserviços ao:

Separar responsabilidades de comando e consulta.

Melhorar desempenho, escalabilidade e organização do sistema.

Facilitar a unificação de dados em sistemas distribuídos.

A implementação do padrão proporciona um sistema mais eficiente e robusto, essencial para lidar com demandas de larga escala e sistemas altamente desacoplados.



## Event Sourcing Pattern



Neste capítulo, falaremos sobre event sourcing, um padrão de arquitetura muito útil, mas comumente mal compreendido. Portanto, antes de falarmos sobre o event sourcing, vamos falar sobre a maneira típica como os aplicativos lidam com os dados. Em geral, os dados que os aplicativos armazenam no banco de dados refletem o estado atual de nossos negócios, e qualquer modificação nesses dados reflete o novo estado que substitui o estado anterior. Obviamente, se quisermos descobrir o estado anterior depois que ele for substituído, sempre poderemos encontrar seu backup. Na maioria dos casos, a menos que algo tenha dado errado, não nos importamos com o estado ou estados anteriores de nossos dados. Só nos preocupamos com o que temos no momento. Além disso, todas as interações que temos com esses dados geralmente acontecem com as operações Crud, que são criar, ler, atualizar e excluir. E, para a maioria dos casos de uso, isso é tudo de que precisamos.



Exemplo, vamos supor que temos uma loja on-line e, em nosso banco de dados NoSQL, temos uma coleção de produtos para cada produto armazenamos informações como nome, descrição, preço e links para imagens. Agora, se em algum momento o proprietário do produto atualizar o preço ou a descrição do produto, o usuário não se importará. Tudo o que importa para eles é o preço e a descrição mais atualizados, e o histórico dessas alterações não tem nenhum valor. No entanto, isso nem sempre é o caso em determinadas situações. Precisamos conhecer não apenas o estado atual, mas também todas as etapas que levaram a ele. Por exemplo, se formos um banco on-line, imagine qual seria a reação de um cliente se déssemos a ele seu saldo atual e nada mais. Não há explicação sobre como eles chegaram a esse equilíbrio. Não há dados sobre saques, depósitos, taxas ou créditos. Apenas o saldo atual e nada mais. Isso seria inconcebível, certo? E o motivo disso é que a forma como o saldo foi calculado é importante não apenas para visualização, mas também para auditoria e possíveis correções.



Outro exemplo é se formos um comerciante que vende produtos em uma loja on-line. Agora imagine que tudo o que temos em um determinado momento é apenas o estado atual do estoque que temos de nossos produtos no depósito. Então, imagine que entramos no sistema pela manhã e vemos que há 200 itens do nosso produto disponíveis no momento. Em seguida, fazemos login novamente à noite e vemos que agora só restam 100 itens do nosso produto. Então, fizemos 100 vendas individuais? Se conseguimos, isso é ótimo. Mas e se vendêssemos 200 itens e recebêssemos 100 devoluções? Nesse caso, não é tão bom assim, certo? Ou talvez tenhamos apenas uma compra única em massa de alguma empresa. Portanto, nesse caso, apenas ter o estado atual não é suficiente. E queremos ver as etapas que levaram ao estado atual.



É aqui que o padrão de event sourcing entra em cena. Em vez de armazenar o estado atual, temos apenas eventos. Cada evento descreve uma alteração ou um fato sobre uma determinada entidade em nosso sistema. O mais importante é que os eventos são imutáveis, o que significa que, uma vez que um evento é inserido em nosso sistema, ele nunca muda. E a única coisa que podemos fazer é anexar novos eventos ao final do registro. Agora, para encontrar o estado atual de uma entidade, simplesmente aplicamos ou reproduzimos todos os eventos que aconteceram com essa entidade. Isso é basicamente como o controle de versão, mas para dados em que cada evento representa apenas o delta ou a alteração do estado anterior.



Por exemplo, no caso de uma conta bancária, em vez de manter e atualizar o saldo atual, armazenamos apenas as transações que movimentam dinheiro para fora ou para dentro da conta. E, ao reproduzir essas transações desde o dia em que a conta foi aberta, sempre podemos obter o saldo atual mais atualizado. A vantagem de armazenar essas transações em vez do saldo é que agora temos o histórico completo de como chegamos a esse saldo, que pode ser relatado e auditado.



Por exemplo, ao analisar essas transações, podemos notar transações duplicadas que podem ter ocorrido, aconteceu, por acaso. Também podemos detectar padrões suspeitos que podem indicar atividades fraudulentas das quais o cliente não estava ciente.



Por fim, também podemos fornecer insights, como conselhos para melhorar os hábitos de gastos ou talvez recomendar outro produto, como uma conta poupança ou um cartão de crédito. Agora, antes de falarmos sobre os poucos benefícios adicionais do uso desse padrão, vamos falar sobre algumas maneiras de armazenar e representar esses eventos.



A primeira maneira é simplesmente armazenar cada evento como um registro separado em um banco de dados. Por exemplo, no caso de uso da loja on-line, podemos armazenar todos os novos pedidos na tabela de pedidos e, toda vez que o status do pedido for alterado, anexamos uma nova linha com o mesmo ID do pedido, seu novo estado e o registro de data e hora. Agora podemos ver todo o histórico de cada ordem fazendo a transição de um estado para outro ao longo do tempo. A vantagem de armazenar eventos em um banco de dados é a capacidade de realizar consultas e análises em conjuntos de dados inteiros.



Por exemplo, podemos rastrear a progressão de um pedido, mas também podemos analisar e rastrear a progressão de vários pedidos de uma só vez e obter determinados insights. Por exemplo, podemos descobrir que em uma determinada data recebemos muitos pedidos novos que podem estar relacionados a uma venda. Ou também podemos descobrir que em um determinado dia tivemos muitos problemas de entrega de pedidos. Outra maneira de armazenar eventos é usar um message broker. Nesse caso, em vez de armazenar os eventos em um banco de dados privado que pertence a um serviço, podemos publicá-los para que qualquer pessoa possa consumi-los. Diferentemente da maioria dos bancos de dados, os intermediários de mensagens são especialmente otimizados para lidar com muitos eventos e também facilitam a manutenção da ordem entre diferentes eventos na mesma entidade. Por outro lado, realizar consultas complexas em fluxos de eventos em um message broker é um pouco mais difícil e menos intuitivo.



Agora, um benefício adicional ao uso do event sourcing é o desempenho de gravação. Sem o event sourcing, se tivermos uma carga de trabalho com uso intensivo de gravação, teremos uma alta contenção sobre as mesmas entidades em um banco de dados, o que normalmente resulta em baixo desempenho. Por exemplo, podemos ter uma tabela de inventário que mantém o controle do inventário atual de cada produto. Se tivermos muitas atualizações simultâneas para a mesma tabela ou, pior ainda, para o mesmo produto, todas as atualizações competirão entre si e ficarão mais lentas, assim como todos os leitores dessa tabela. Por outro lado, se mudarmos para o event sourcing, cada compra ou devolução se tornará um evento somente de acréscimo, o que não exige nenhum bloqueio de banco de dados e é muito mais eficiente.



Agora vamos falar sobre algumas maneiras eficientes que podemos usar para ler e reconstruir o estado mais atualizado de uma entidade com base em eventos. É claro que reproduzir todas as transações na conta bancária de alguém toda vez que queremos mostrar ao cliente seu saldo não é muito eficiente. Portanto, para resolver isso, podemos aplicar algumas estratégias. A primeira estratégia é tirar snapshots em determinados pontos do registro de eventos. Por exemplo, podemos tirar um snapshot do saldo da conta de cada usuário uma vez por mês. Portanto, ainda temos todo o histórico de todas as transações desde o início dos tempos, se o usuário quiser acessá-lo. Mas agora, usando esses snapshots, o usuário pode obter o saldo atual da conta apenas reproduzindo as transações do último snapshot em vez do momento em que a conta foi aberta. A segunda otimização é usar um padrão que já conhecemos muito bem, que é o de search engines usando search engines. Podemos separar a parte que anexa eventos ao nosso sistema e os armazena da parte de consulta, que armazena o estado atual em um banco de dados otimizado para leitura. Esse banco de dados somente para leitura pode ser até mesmo um banco de dados na memória, o que torna as leituras ainda mais rápidas.



Agora, como sempre, toda vez que um novo evento chegar, se armazenarmos esses eventos em um agente de mensagens, o serviço de consulta poderá se inscrever nesse mesmo tópico ou canal e extrair os dados diretamente dele. E o lado do comando não precisa de nada especial do banco de dados. A combinação entre o sourcing seguro e o de eventos é muito popular no setor. Já que temos o melhor dos dois mundos. Recebemos o histórico e a auditoria. Temos gravações rápidas e eficientes e temos leituras rápidas e eficientes. É claro que nada vem de graça e, se usarmos o event sourcing com secures, obteremos apenas consistência eventual, o que, novamente, pode ou não ser bom o suficiente, dependendo do seu caso de uso.



Neste capítulo, aprenderemos sobre o padrão de arquitetura de event sourcing. Usando esse padrão, em vez de armazenar e atualizar apenas o estado atual de uma entidade, armazenamos as alterações ou fatos sobre essa entidade usando eventos. Posteriormente, falamos sobre duas maneiras de armazenar esses eventos: um banco de dados ou um agente de mensagens, sendo que cada abordagem tem suas vantagens e desvantagens. Depois disso, mencionamos um benefício colateral muito bom de maior desempenho ao usar o padrão de event sourcing para cargas de trabalho com uso intenso de gravação. E, por fim, aprenderemos sobre uma combinação avançada de event sourcing e segurança, que nos permite aproveitar os benefícios da auditoria, das gravações de alto desempenho e das leituras eficientes.



## Resumo:

## Armazenamento e Representação de Eventos

## Os eventos podem ser armazenados de duas maneiras principais:

Banco de Dados: Cada evento é registrado como uma linha separada. Em uma loja online, alterações no status de pedidos podem ser registradas com o ID do pedido, o novo status e a data/hora. Isso permite consultas detalhadas sobre o histórico de eventos e análises de padrões, como picos de vendas ou problemas operacionais.

Message Broker: Eventos são publicados para consumidores interessados. Essa abordagem é otimizada para alta escala e preservação de ordem. No entanto, realizar consultas complexas sobre fluxos de eventos em um message broker é mais desafiador.



## Benefícios Adicionais

O Event Sourcing melhora o desempenho de gravações em cenários com alta concorrência, pois cada operação é apenas um acréscimo. Por exemplo, em um sistema de estoque, gravações simultâneas de compras e devoluções não geram contenção, como ocorreria ao atualizar diretamente o saldo do estoque.



## Estratégias de Leitura e Reconstrução

Reproduzir todos os eventos desde o início pode ser ineficiente. Para mitigar isso, utilizamos:

Snapshots: Capturamos o estado atual periodicamente, como o saldo de uma conta no fim de cada mês. Assim, apenas os eventos desde o último snapshot precisam ser aplicados.

Projeções e CQRS: Separar comandos (escrita) de consultas (leitura), armazenando o estado atual em um banco de dados otimizado para leitura, como um banco em memória.

Essa combinação entre Event Sourcing e CQRS permite aproveitar auditoria detalhada, gravações rápidas e leituras eficientes, embora introduza consistência eventual, que pode ser aceitável dependendo do caso de uso.

Neste capítulo, exploraremos esses conceitos, suas vantagens e limitações, destacando como o Event Sourcing pode transformar a forma como projetamos sistemas resilientes e auditáveis.





## Testing Microservices and Event-Driven Architecture



## Pirâmide de testes para microsserviços - Introdução e desafios



Agora que falamos extensivamente sobre todos os aspectos do desenvolvimento e do design de software para microsserviços, vamos falar sobre uma parte ainda mais importante, que é levar esses microsserviços à produção. Mas antes de implantar um sistema na produção e receber o tráfego de usuários, precisamos ganhar confiança por meio de testes automatizados. Começaremos com uma rápida recapitulação de como costumávamos testar aplicativos monolíticos e, em seguida, discutiremos como aplicar os métodos que usamos para testar um monolito à arquitetura de microsserviços. E, por fim, discutiremos alguns desafios do teste de microsserviços e da arquitetura orientada por eventos. Portanto, vamos começar revisitando o processo de teste de um aplicativo monolítico.



Primeiro, quando configuramos testes para um único aplicativo, podemos agrupar esses testes em três categorias:



## Testes de unidade

## Testes de integração

## Testes funcionais ou de ponta a ponta



Isso é comumente chamado de pirâmide de testes. Na parte inferior, temos os testes de unidade. Cada teste de unidade testa uma pequena unidade lógica, como uma classe ou um módulo, de forma isolada. Os testes unitários são os mais baratos de manter porque são pequenos, fáceis de escrever e rápidos de executar por serem tão baratos. Também devemos criar o maior número desses testes em comparação com outros testes, e é por isso que eles estão localizados na base dessa pirâmide.



Por outro lado, esses testes nos dão menos confiança em relação ao nosso sistema geral porque testam apenas cada unidade isoladamente. E quando executamos o aplicativo, não temos ideia se todas essas unidades funcionarão juntas ou não.



O segundo tipo de teste são os testes de integração. Como o nome sugere, esses testes verificam se as diferentes unidades e sistemas com os quais nos integramos, como um banco de dados ou um agente de mensagens, realmente funcionam juntos. Esses testes são maiores e mais lentos, portanto, devemos ter menos deles do que os testes de unidade. No entanto, depois de executar esses testes, temos mais confiança em nosso sistema.



Por fim, temos os testes funcionais ou de ponta a ponta na parte superior. Esses testes executam todo o nosso sistema, que inclui a interface do usuário, todo o nosso aplicativo e o banco de dados e verificam se ele funciona como pretendido. Do ponto de vista do usuário final, cada um desses testes deve testar uma jornada específica do usuário ou um requisito comercial e garantir que ele corresponda à especificação. Não é de surpreender que os testes de ponta a ponta sejam os mais pesados e complexos de configurar e os mais lentos de executar. É por isso que devemos ter o menor número deles em comparação com os outros testes. Por outro lado, esses testes nos dão o mais alto grau de confiança de que nosso sistema funcionará como pretendido  na produção.







Agora, como traduzir essa pirâmide para uma arquitetura de microsserviços em que os microsserviços se comunicam entre si por meio da rede ou de um message broker e cada microsserviço tem seu próprio banco de dados? Como primeira etapa, cada equipe de microsserviço deve seguir exatamente a mesma pirâmide de testes, que inclui testes de unidade, testes de integração e testes funcionais para seu próprio microsserviço e banco de dados. Em seguida, tratamos cada microsserviço como uma pequena unidade que faz parte do sistema maior e o colocamos em uma pirâmide de testes maior. Assim como no caso dos testes unitários, testar cada microsserviço isoladamente é essencial, mas não é suficiente para aumentar a confiança de que todos esses microsserviços podem de fato conversar entre si em tempo de execução e funcionar corretamente juntos. Precisamos adicionar outra camada de testes de integração. Esses testes de integração verificam se cada par de microsserviços pode se comunicar entre si usando a API acordada e, ao mesmo tempo, simulando o restante do nosso sistema. Para completar essa pirâmide, precisamos adicionar os testes de ponta a ponta em nível de sistema no topo.



Esses testes, em teoria, devem executar todos os nossos microsserviços, bancos de dados, intermediários de mensagens e front-ends em um teste de ambiente e verifique se todos os componentes individuais funcionam juntos conforme o esperado. Agora vamos discutir os desafios dessa nova versão da pirâmide de testes para microsserviços.



O primeiro desafio é que, embora esses testes de ponta a ponta nos proporcionem o mais alto nível de confiança, eles são extremamente difíceis de configurar e manter. Também não está claro qual equipe deve ser a proprietária desse ambiente e quando uma das equipes de microsserviço interrompe sua construção. Mesmo que seja por um dia, todo o pipeline de testes será interrompido. Isso pode resultar no bloqueio de todas as equipes e na impossibilidade de fazer lançamentos na produção.



Como alternativa, os desenvolvedores podem simplesmente começar a ignorar esses testes de ponta a ponta e liberar seus microsserviços de qualquer maneira, o que torna esses testes apenas uma responsabilidade sem nenhum benefício. Também é muito caro executar o que é essencialmente um ambiente duplicado em relação ao nosso ambiente de produção já existente, mesmo que sua escala seja muito menor. Na prática, algumas empresas gastam um esforço desproporcionalmente excessivo para criar e manter esses poucos testes, enquanto outras decidem assumir o risco e simplesmente não se preocupam em investir nesses testes.



O segundo desafio dessa nova pirâmide é que até mesmo a execução de testes de integração pode ser bastante difícil e cria um ponto de forte acoplamento entre as equipes. Quando a equipe proprietária do microsserviço A, que consome a API do microsserviço B, deseja executar testes de integração, ela precisa criar, configurar e executar os dois microsserviços, enquanto a equipe A sabe como criar e executar seu próprio microsserviço. Talvez não esteja claro para eles como configurar um microsserviço B é ainda mais difícil se o microsserviço B tiver muitas dependências, como um banco de dados ou outro serviço que precise ser executado ou simulado. Mas a equipe proprietária do microsserviço B que fornece essa API também tem um problema. Esse microsserviço pode ter vários microsserviços que consomem sua API. Portanto, para garantir que as alterações feitas em sua API não danifiquem todos os consumidores de API, eles precisam criar, configurar e executar todos esses consumidores para executar seus testes. Como podemos ver, isso pode rapidamente sair do controle e desacelerar o desenvolvimento de toda a organização.





O terceiro desafio é quando usamos a arquitetura orientada por eventos para desacoplar os microsserviços. Nesse caso, temos um microsserviço que produz eventos para um message broker e, na verdade, ele nem sempre sabe quais microsserviços consomem esses eventos. Esse desacoplamento é um dos benefícios que queríamos obter com a arquitetura orientada por eventos. No entanto, agora não podemos realmente executar nenhum teste de integração com esses microsserviços. Também temos o mesmo problema quando somos uma equipe que possui um microsserviço que consome eventos de outros microsserviços. Novamente, precisamos executar esses microsserviços e um message broker apenas para testar se o nosso microsserviço é capaz de consumir esses eventos e se o formato desses eventos não foi alterado sem o nosso conhecimento.



Portanto, agora que entendemos todos esses desafios, estamos prontos para conhecer algumas soluções alternativas que as empresas usam para testar microsserviços e arquitetura orientada por eventos. Mas antes de fazermos isso, vamos resumir rapidamente o que aprendemos neste capítulo.



Neste capítulo, revisitamos a pirâmide de testes em uma arquitetura monolítica. Em seguida, aprenderemos a aplicar essa mesma pirâmide aos microsserviços. Mais tarde, discutimos alguns desafios do uso dessa abordagem tradicional, que incluíam o alto custo e a complexidade de executar um ambiente completo de ponta a ponta. O forte acoplamento entre as equipes para executar testes de integração eficazes e a complexidade e a sobrecarga dos testes de microsserviços orientados por eventos.

## Resumo:

## Revisão da Pirâmide de Testes Monolítica

Nos testes de aplicativos monolíticos, os casos geralmente se dividem em três níveis:

Testes de Unidade: Validam pequenas unidades lógicas, como classes ou funções, de forma isolada. São rápidos, fáceis de manter e formam a base da pirâmide, com o maior número de testes.

Testes de Integração: Garantem que componentes distintos, como bancos de dados ou APIs, funcionem corretamente em conjunto. São mais lentos e complexos, por isso, em menor quantidade.

Testes Funcionais (E2E): Avaliam o sistema completo, simulando cenários reais do usuário. Apesar de fornecerem maior confiança, são mais caros e difíceis de manter, sendo menos frequentes.

Essa estrutura, conhecida como pirâmide de testes, é eficiente para monolitos, mas precisa ser adaptada para a complexidade dos microsserviços.

## Adaptando a Pirâmide para Microsserviços

Em arquiteturas de microsserviços, os componentes se comunicam via rede ou message brokers, e cada serviço tem seu banco de dados. A pirâmide é expandida para incluir:

Testes de Unidade: Cada microsserviço aplica testes em suas unidades internas.

Testes de Integração Internos: Validam a integração do microsserviço com suas dependências diretas, como bancos de dados.

Testes de Integração Entre Serviços: Confirmam a interação entre microsserviços, simulando chamadas de API ou eventos.

Testes Funcionais (E2E): Avaliam o sistema completo, executando todos os microsserviços e seus componentes em um ambiente integrado.

Embora eficaz, essa abordagem traz novos desafios, especialmente para sistemas distribuídos.

## Desafios no Teste de Microsserviços

## 1. Complexidade dos Testes E2E

Os testes E2E fornecem alta confiança, mas são difíceis de configurar e manter. Há dúvidas sobre a responsabilidade pelo ambiente compartilhado e interrupções podem paralisar toda a organização. Além disso, o custo de replicar o ambiente de produção, mesmo em menor escala, é significativo.

## 2. Dificuldade em Testes de Integração

A execução de testes de integração pode criar forte acoplamento entre equipes. Por exemplo:

A equipe que consome uma API precisa executar o serviço fornecedor e suas dependências.

O fornecedor de uma API precisa garantir que alterações não afetem todos os consumidores, exigindo execução complexa e demorada de testes.

## 3. Desafios em Arquitetura Orientada por Eventos

A arquitetura orientada por eventos dificulta os testes de integração. Um serviço produtor não sabe quais consumidores processam seus eventos, inviabilizando testes diretos. Da mesma forma, consumidores precisam simular todo o ecossistema para validar seus casos, aumentando a complexidade.





## contract tests e testes de produção



No capítulo anterior, discutimos a pirâmide de testes e como aplicá-la à arquitetura de microsserviços. Também discutimos os muitos desafios de executar testes de ponta a ponta com microsserviços, o que força muitas empresas a investir esforços desproporcionalmente altos neles ou a abandoná-los completamente. Também discutimos os desafios dos testes de integração entre microsserviços, que incluíam sua complexidade e o forte acoplamento entre as equipes. Agora que identificamos todos esses desafios, vamos discutir algumas soluções alternativas, começando pelos testes de integração.



A primeira solução que pode nos ajudar com a complexidade dos testes de integração é o uso de mocking leve. Em vez de executar um microsserviço inteiro, considere o cenário em que somos uma equipe que possui o microsserviço A que consome a API do microsserviço B. Esta equipe deseja executar um teste de integração que valide o acionamento. Determinadas funcionalidades com um conjunto de parâmetros resultam em um microsserviço A e envia uma solicitação ao microsserviço B e o microsserviço A também trata corretamente a resposta do microsserviço B normalmente, para executar esse teste, teríamos que criar, configurar e executar o microsserviço B com todas as suas dependências.



Mas agora, em vez disso, simplesmente simulamos a camada de API do microsserviço B, com a qual nos integramos, e a configuramos para enviar uma resposta codificada se receber a solicitação esperada. Da mesma forma, a equipe proprietária do microsserviço B, que fornece a API para outros microsserviços, pode executar um conjunto de consumidores simulados em vez de executar microsserviços reais. Em seguida, podemos escrever testes que criam esses consumidores simulados, nos enviam solicitações e testam se o nosso microsserviço retorna as respostas esperadas.



A estratégia reduz o acoplamento entre as diferentes equipes, pois se uma equipe interromper sua construção, a outra equipe poderá continuar executando seus testes. Ele também reduz a sobrecarga de execução de instâncias reais dos outros microsserviços. No entanto, essa estratégia, por si só, tem um grande problema. O problema é que o contrato entre um consumidor de API e o provedor de API pode ficar fora de sincronia sem que essas equipes o detectem. Por exemplo, a equipe do provedor de API pode alterar a atualização da API, o consumidor simulado e os testes, e todos os testes serão aprovados com êxito. Mas a comunicação sobre essas alterações pode ser perdida ou mal compreendida pelo microsserviço A, que consome essa API. Portanto, ou eles não fazem nenhuma alteração ou fazem alterações incorretas e seus testes também serão aprovados. Quando esses dois microsserviços forem liberados para produção, eles não poderão se comunicar entre si e causar uma interrupção.



Para resolver esse problema, podemos introduzir um novo tipo de teste, chamado de teste de contrato (contract test). Os contract tests funcionam usando uma ferramenta dedicada para manter o provedor de API simulado e o consumidor de API simulado em sincronia por meio de um contrato compartilhado. Quando a equipe de consumidores da API executa seus testes, eles são executados em relação ao provedor de API simulado. Durante esse teste, eles testam se o microsserviço A envia as solicitações corretas e recebe as respostas corretas conforme o esperado. No entanto, além disso, cada solicitação que ele envia ao provedor de API simulado é registrada junto com a resposta esperada em um arquivo de contrato. Esse arquivo de contrato é então compartilhado com a equipe proprietária do microsserviço B, que fornece a API usando esse contrato. A equipe proprietária do microsserviço B repete todas as solicitações registradas para o microsserviço B real e verifica se as respostas obtidas são as mesmas registradas no contrato. E se o microsserviço B tiver muitos consumidores, ele pegará todos os seus contratos registrados, criará esses consumidores simulados e executará cada um deles em relação à implementação real da API. Dessa forma, cada equipe pode executar seus próprios testes de integração sem ter que lidar com as complexidades de criação, configuração e desenvolvimento. Executar outros microsserviços, mas as ferramentas de teste de contrato (contract test) garantem que cada equipe teste o contrato mais atualizado e correto compartilhado entre esses microsserviços.



Também podemos estender a ideia de contract tests para testes de integração entre microsserviços orientados por eventos. Vamos considerar um cenário concreto de um sistema de comércio eletrônico. Quando um usuário envia uma solicitação para comprar um produto, essa solicitação vai para o serviço de pedidos. Em seguida, o serviço Order publica um evento para o serviço de pagamento e responde ao usuário. O serviço de pagamento consome esse evento, cria o usuário e, em seguida, passa-o como outro evento para o serviço de envio. Para simplificar, vamos nos concentrar nos testes de integração entre o serviço de pagamento e o serviço de envio. Nesse caso, o contrato entre os serviços é o formato do evento que contém informações sobre o usuário, o produto, sua quantidade e assim por diante. Portanto, em vez de configurar um message broker e executar os dois microsserviços, cada equipe cria sua simulação leve desse message broker. Portanto, quando a equipe do serviço de envio testa sua própria capacidade de consumir e analisar o evento do serviço de pagamento, esse evento também é registrado em um arquivo de contrato. Esse arquivo de contrato é então compartilhado com a equipe proprietária do microsserviço que publica esse evento, que é o serviço de pagamento. Nesse caso, quando essa equipe quiser executar testes de integração entre seu serviço e o consumidor de eventos, ela acionará a função em seu serviço que deve produzir esse evento. Em seguida, o teste de contrato (contract test) verificará se o formato e o conteúdo do evento correspondem ao que foi registrado nesse contrato. E, se corresponder, o contrato entre os dois microsserviços estará em sincronia e poderemos liberá-los com confiança para a produção.



Portanto, como podemos ver, esses contract tests podem realmente simplificar a execução de testes de integração para microsserviços que se comunicam de forma síncrona e assíncrona, mas ainda nos dão alta confiança de que, quando implantamos esses microsserviços na produção, eles podem se comunicar uns com os outros, como esperamos.





Agora vamos falar sobre testes de ponta a ponta. Embora os contract tests possam ser uma ótima alternativa aos testes de integração, eles não substituem os testes de ponta a ponta. Se a configuração de testes de ponta a ponta não for viável para nossa empresa, a alternativa é testar na produção. Na verdade, há muitas maneiras de fazer isso. Um deles é o uso de uma liberação gradual usando a implantação verde-azul em combinação com o teste canário (canary test). Uma implementação blue green é uma maneira segura de liberar uma nova versão de microsserviço para a produção usando dois ambientes de produção idênticos sem nenhum tempo de inatividade durante o lançamento. O ambiente azul é um conjunto de servidores ou contêineres que executam nossa versão antiga, e o ambiente verde é um conjunto de servidores ou contêineres que executam a nova versão que queremos lançar. Depois de implementarmos a nova versão no ambiente verde, nenhum tráfego real de usuários será direcionado a ela. Essa é uma oportunidade de aumentar nossa confiança executando testes automatizados e até mesmo manuais nesses servidores sem afetar os usuários reais. Depois de executar esses testes, podemos transferir uma parte do tráfego de produção para o ambiente verde e monitorar a nova versão quanto a problemas funcionais e de desempenho.  Esse processo é chamado de teste canário (canary test).







Se detectarmos um problema, direcionamos imediatamente o tráfego de volta do ambiente verde para o ambiente azul com o mínimo de impacto sobre os usuários. Por outro lado, se nenhum problema for detectado, direcionamos todo o tráfego de produção do ambiente azul para o ambiente verde e gradualmente desativamos o ambiente azul, pois ele não é mais necessário.



Portanto, agora que temos uma alternativa para testes de integração de microsserviços que se comunicam diretamente entre si e por meio de um message broker em uma forma de contract tests, temos uma alternativa para testes de ponta a ponta na forma de testes de produção, usando a implantação blue green e o teste canário (canary test). É claro que todas essas alternativas devem ser usadas somente se a configuração de microsserviços reais no estágio de desenvolvimento para fins de teste for muito complexa ou cara.



Neste capítulo, aprenderemos a lidar com a complexidade da execução de testes de integração e testes de ponta a ponta na arquitetura de microsserviços. Primeiro, apresentamos uma abordagem simplista para testes de integração em que cada equipe simplesmente simula o outro microsserviço. Depende e vimos que, embora essa abordagem simplifique muito o teste de integração, ela não foi suficiente para impor os contratos de API entre os microsserviços. Depois disso, aprenderemos como o teste de contrato (contract test) resolve esse problema, mantendo os contratos entre o consumidor da API e o produtor da API sincronizados. Posteriormente, estendemos o conceito de teste de contrato (contract test) à arquitetura orientada por eventos, em que os microsserviços se comunicam entre si por meio de uma fila de mensagens ou de um message broker. E, por fim, oferecemos uma alternativa aos testes de ponta a ponta na forma de testes de produção usando a implantação blue green e o teste canário (canary test).



## Soluções de teste de contrato



Pact - Uma ferramenta de teste de contrato de código aberto que permite que consumidores de API e provedores de API definam e verifiquem seus contratos de API. Suporte do Pact para muitas linguagens de programação e frameworks.

Spring Cloud Contract - Um projeto guarda-chuva de código aberto para soluções de teste de contrato. Contém o projeto Spring Cloud Contract Verifier que permite o desenvolvimento de Consumer Driven Contract (CDC) de aplicativos baseados em JVM usando Groovy DSL ou YAML.

PactFlow -  Uma oferta comercial que gerencia o ciclo de vida de contratos definidos por ferramentas de teste de contratos (como Pact, Spring Contract, etc.) e fornece um fluxo de trabalho para gerenciá-los em seus pipelines de CI/CD.
Suporta todas as linguagens JVM, bem como Ruby, Golang, NodeJS / JavaScript, Python, Objective-C / Swift, .NET, PHP, C++ e Rust

## Resumo:

## Mocking Leve como Solução para Testes de Integração

Uma abordagem para reduzir a complexidade dos testes de integração é o uso de mocking leve. Imagine que a equipe responsável pelo microsserviço A consome a API do microsserviço B e precisa validar, por meio de testes, se chamadas realizadas ao microsserviço B resultam no comportamento esperado no microsserviço A. Tradicionalmente, seria necessário configurar e executar o microsserviço B, juntamente com suas dependências, o que pode ser oneroso.

Com o mocking leve, a equipe de A simula a camada de API de B, configurando-a para retornar respostas pré-definidas com base nas requisições esperadas. Da mesma forma, a equipe de B pode simular consumidores para validar como as requisições enviadas por eles são tratadas. Essa estratégia reduz o acoplamento entre as equipes e simplifica os testes, eliminando a necessidade de executar microsserviços reais.

Contudo, essa abordagem apresenta um problema: o contrato entre consumidor e provedor de API pode sair de sincronia. Alterações na API podem não ser refletidas adequadamente nos testes simulados, resultando em falhas na comunicação em produção.

## Testes de Contrato (Contract Tests)

Os contract tests solucionam esse problema ao sincronizar consumidores e provedores de API por meio de um contrato compartilhado. Durante os testes, a equipe consumidora registra as requisições e respostas em um arquivo de contrato. Esse contrato é então compartilhado com a equipe do provedor, que o utiliza para validar a API real em relação às requisições registradas.

Se o microsserviço B possuir múltiplos consumidores, todos os contratos registrados são verificados para garantir que mudanças na API não impactem os consumidores. Dessa forma, cada equipe pode testar seus serviços isoladamente, enquanto o contrato garante a consistência entre os microsserviços.

## Testes de Contrato em Arquiteturas Orientadas por Eventos

Os contract tests também são aplicáveis a microsserviços que utilizam arquitetura orientada por eventos. Em um sistema de comércio eletrônico, por exemplo, o serviço de pedidos publica eventos para o serviço de pagamento, que por sua vez os encaminha ao serviço de envio. O contrato, nesse caso, é o formato do evento.

A equipe consumidora (serviço de envio) registra os eventos em um contrato durante seus testes. Esse contrato é então utilizado pela equipe do produtor (serviço de pagamento) para validar que os eventos gerados estão em conformidade com o esperado. Esse processo assegura a sincronização entre os serviços, mesmo em arquiteturas assíncronas.

## Testes em Produção

Embora os contract tests sejam uma alternativa eficaz aos testes de integração, eles não substituem os testes de ponta a ponta. Para empresas onde configurar esses testes é inviável, testes em produção podem ser uma solução.

Uma estratégia comum é o uso de deployments azul-verde (blue-green) combinados com testes canários (canary testing). Nessa abordagem, dois ambientes de produção idênticos são utilizados:

O ambiente azul executa a versão antiga do serviço.

O ambiente verde implementa a nova versão.

Inicialmente, nenhum tráfego real é direcionado ao ambiente verde, permitindo a execução de testes automatizados e manuais. Gradualmente, uma parcela do tráfego de produção é redirecionada ao ambiente verde (teste canário). Se problemas forem detectados, o tráfego é revertido ao ambiente azul com impacto mínimo. Caso contrário, o tráfego é completamente migrado para o ambiente verde.

## Conclusão

Neste capítulo, exploramos alternativas para superar os desafios dos testes de integração e de ponta a ponta em microsserviços:

Mocking leve: Reduz complexidade, mas não garante a sincronização de contratos.

Testes de contrato: Garantem consistência entre consumidores e provedores, tanto em comunicações síncronas quanto assíncronas.

Testes em produção: Utilizando blue-green deployments e testes canários como alternativa aos testes de ponta a ponta.

Essas soluções oferecem flexibilidade e confiabilidade, permitindo que equipes gerenciem a complexidade e os custos dos testes em arquiteturas de microsserviços.





## Observabilidade na Arquitetura de Microsserviços



## Introdução aos três pilares da observabilidade em microsserviços



Como engenheiros de software profissionais, todos sabemos que, por melhor que seja o teste do nosso código, bugs, falhas e problemas de desempenho sempre ocorrerão. Esses problemas são particularmente difíceis de solucionar quando temos um sistema distribuído de alta escala composto por dezenas ou até centenas de microsserviços. Nesta seção, falaremos sobre os tópicos importantes de observabilidade e monitoramento em uma arquitetura de microsserviços. Neste capítulo, começaremos aprendendo o que significa observabilidade e como ela é diferente de monitoramento. Em seguida, falaremos sobre por que a observabilidade é tão importante para a arquitetura de microsserviços. E, mais tarde, apresentaremos os três pilares da observabilidade, que discutiremos mais detalhadamente nas palestras seguintes.



Então, o que é observabilidade e qual é a diferença entre ela e o monitoramento? Aparentemente, monitoramento e observabilidade são conceitos muito semelhantes.



Ambas fornecem ferramentas que coletam dados e nos dão insights sobre nosso sistema em produção e nos permitem detectar problemas quando eles ocorrem. No entanto, há uma diferença sutil. O monitoramento é o processo de coleta, análise e exibição de um conjunto predefinido de métricas e, ao anexar alertas a essas métricas predefinidas, podemos descobrir quando algo dá errado. No entanto, as ferramentas de monitoramento e os painéis, por si só, geralmente só nos informam que algo está errado, mas não são suficientes para nos dizer o que está errado e como corrigir o problema.



Por outro lado, a observabilidade nos permite depurar ativamente, procurar padrões, acompanhar as entradas e saídas de nossos microsserviços e obter insights sobre o comportamento de nosso sistema. Isso nos permite acompanhar o fluxo de solicitações, transações ou eventos individuais em todo o sistema, descobrir e isolar gargalos de desempenho e, por fim, apontar a origem do problema, em vez de apenas nos informar que o problema existe.



Embora o monitoramento seja muito importante para qualquer tipo de sistema, a observabilidade é fundamental principalmente para a arquitetura de microsserviços. Se tivermos algum problema em um aplicativo monolítico, geralmente é relativamente simples depurá-lo ou criar um perfil, pois tudo acontece dentro dos limites de um único aplicativo. Na pior das hipóteses, sempre podemos acessar uma instância do nosso aplicativo monolítico e inspecionar seus logs ou instrumentos e ter uma ideia de qual parte do código está causando os problemas de desempenho ou está lançando a exceção. Por outro lado, na arquitetura de microsserviços, uma única solicitação do usuário pode envolver vários microsserviços e bancos de dados. Eles podem até mesmo se comunicar uns com os outros de forma assíncrona por meio de um message broker. Agora, se ocorrer um problema em algum ponto da transação, pode ser muito difícil descobrir em qual serviço ele ocorreu. Além disso, todos esses serviços são executados como um grupo de instâncias em computadores diferentes, o que amplia ainda mais o desafio. E, como se isso não bastasse, estatisticamente, a maioria dos problemas na arquitetura de microsserviços ocorre, na verdade, nos limites da API desses microsserviços e não no próprio código dos microsserviços.



Portanto, é absolutamente essencial ter insights sobre o fluxo e o conteúdo dos dados que entram e saem de cada microsserviço e rastrear o caminho das solicitações entre os microsserviços. Normalmente, ter apenas um tipo de sinal é insuficiente para depurar um problema nos microsserviços e na arquitetura orientada por eventos. Portanto, quando falamos de observabilidade, normalmente nos referimos a três tipos de sinais que são comumente chamados de três pilares da observabilidade.



Esses pilares são as métricas de registro distribuído (distributed logging) e os registros de rastreamento distribuído, que são arquivos anexados apenas que registram eventos individuais que ocorrem em um processo de aplicativo, instância do banco de dados do contêiner ou servidor. Esses eventos geralmente são representados como sequências de dados de forma estruturada ou semiestruturada. Além disso, esses eventos são acompanhados de metadados, como o registro de data e hora do evento, a solicitação que o acionou, a classe de método ou o aplicativo em que o evento ocorreu e assim por diante.



As métricas são pontos de dados amostrados regularmente, representados como valores numéricos, como contadores, distribuições ou medidores. Os exemplos incluem contadores do número de solicitações por minuto ou erros por hora, distribuições de latências ou medidores que representam o uso atual da CPU ou da memória, cache, taxa de acerto e assim por diante.



O terceiro pilar é o rastreamento. Os rastros representam o caminho que uma determinada solicitação percorre em vários microsserviços e o tempo que cada microsserviço leva para processar essa solicitação. Os rastreamentos podem incluir informações adicionais, como cabeçalhos de solicitação, códigos de status de resposta e assim por diante. Portanto, quando recebemos um alerta sobre um problema ou o detectamos manualmente usando nossos painéis de monitoramento, podemos usar todas as três formas de sinais para depurar ainda mais o problema usando uma combinação desses sinais. Podemos rastrear solicitações individuais, isolar o problema em um determinado microsserviço ou API e reduzi-lo a um método individual ou até mesmo a uma linha de código que causa esse bug ou gargalo de desempenho. Usando esses sinais, também podemos obter informações suficientes sobre como resolver esse problema, o que pode envolver uma reversão, um hotfix ou alterações na infraestrutura, como adicionar mais instâncias de serviço, desviar o tráfego para outra região ou data center e assim por diante. Portanto, agora que temos uma boa introdução e motivação para a observabilidade em microsserviços e aprendemos os três pilares da observabilidade, vamos nos aprofundar em cada um desses tipos de sinais, começando com o registro distribuído (distributed logging).







## Resumo:

## Observabilidade vs. Monitoramento

Embora monitoramento e observabilidade pareçam semelhantes, há uma diferença importante:

Monitoramento é o processo de coletar, analisar e exibir métricas predefinidas. Com alertas configurados, ele permite identificar que algo está errado, mas não necessariamente explica a causa ou como resolver o problema.

Observabilidade, por sua vez, oferece a capacidade de explorar ativamente o sistema, rastrear padrões, analisar fluxos de dados e identificar a origem dos problemas.

Enquanto o monitoramento informa o que está errado, a observabilidade permite entender por que algo está errado e encontrar soluções.

## A Relevância da Observabilidade em Microsserviços

Em aplicações monolíticas, depurar ou criar perfis de execução é relativamente simples, já que todo o código e os logs estão contidos em uma única instância. No entanto, em arquiteturas de microsserviços, uma única solicitação pode atravessar múltiplos serviços, bancos de dados e até mesmo interações assíncronas via message brokers.

## Problemas são ainda mais desafiadores porque:

Microsserviços frequentemente rodam em várias instâncias distribuídas.

A maioria dos problemas ocorre nos limites das APIs, e não no código interno.

A comunicação assíncrona dificulta rastrear a origem dos erros.

Por isso, é essencial ter ferramentas que capturem o fluxo de dados e rastreiem solicitações entre os serviços, garantindo uma visão clara do comportamento do sistema.

## Os Três Pilares da Observabilidade

A observabilidade se baseia em três sinais principais, conhecidos como os "três pilares da observabilidade":

## Logs

Registros de eventos individuais que ocorrem em processos de aplicativos, bancos de dados ou servidores.

Apresentam informações estruturadas ou semiestruturadas, enriquecidas com metadados como timestamps, IDs de solicitação e detalhes do ambiente.

Exemplo: um log que registra uma exceção ou uma falha em uma transação.

## Métricas

Dados amostrados regularmente, representados como valores numéricos, como contadores, distribuições ou medidores.

Exemplos: número de requisições por minuto, taxa de erros, latência média, uso de CPU/memória.

Permitem identificar tendências e anomalias no desempenho do sistema.

## Rastreios (Traces)

Representam o caminho percorrido por uma solicitação através de vários microsserviços.

Incluem detalhes sobre o tempo de processamento em cada serviço, cabeçalhos de requisição, códigos de status e outros metadados.

Facilitam a identificação de gargalos e pontos de falha no fluxo de solicitações.

## Como os Pilares Trabalham em Conjunto

Quando um problema é identificado por meio de monitoramento (alerta ou painel), os três pilares fornecem as informações necessárias para depuração:

Logs ajudam a identificar eventos relacionados ao problema.

Métricas mostram o impacto e a escala do problema.

Rastreios isolam o ponto exato da falha, possibilitando encontrar a causa raiz em um método ou linha de código específica.

Esses sinais também auxiliam na tomada de decisão para resolver problemas, seja com uma reversão, hotfix, ajustes na infraestrutura (como redirecionamento de tráfego ou escalabilidade horizontal), entre outras estratégias.

## Conclusão

A observabilidade é essencial para o sucesso de sistemas baseados em microsserviços. Ela vai além do monitoramento tradicional, oferecendo uma visão detalhada do comportamento do sistema. Agora que entendemos os fundamentos e os três pilares da observabilidade, vamos explorar cada um deles, começando com os logs distribuídos.





## Registro Distribuído (Distributed Logging)



No capítulo anterior, tivemos a introdução e a motivação para a observabilidade em microsserviços e na arquitetura orientada por eventos. Também aprendemos sobre os três pilares da observabilidade, que incluíam métricas de registro distribuído (distributed logging) e rastreamento distribuído. Usando esses três tipos de sinais, podemos obter insights profundos sobre nosso sistema, depurar problemas de forma eficaz e encontrar a origem do problema ou o gargalo de desempenho. Então, agora vamos falar mais detalhadamente sobre o primeiro tipo de sinal, que é o registro distribuído (distributed logging). Primeiro, faremos uma rápida recapitulação do que queremos dizer com registro em log e, em seguida, falaremos sobre algumas práticas recomendadas importantes para o registro em log distribuído na arquitetura de microsserviços. Então, vamos começar com um rápido lembrete do que é o registro em log.



O registro em log é uma das maneiras mais simples de os desenvolvedores fornecerem informações sobre o estado atual de um aplicativo. Uma linha de registro pode representar um evento do aplicativo, como o recebimento de uma nova solicitação ou uma ação, como a execução de uma consulta ao banco de dados ou o início de uma operação de processamento complexa. É também uma forma de registrar exceções e erros em um método acompanhado pelo conjunto de parâmetros que levaram a esse problema. Essas informações podem ser valiosas para depurar e corrigir o problema e adicionar testes suficientes para evitar esses bugs no futuro. No entanto, na arquitetura de microsserviços, podemos ter milhares de instâncias de diferentes microsserviços produzindo coletivamente milhões de linhas de registro por dia. Portanto, quando temos um problema, não é prático pesquisar e inspecionar esses arquivos de registro um a um. Portanto, a primeira prática recomendada importante para dar sentido a toda essa quantidade útil, mas muito grande, de dados é coletá-los em um sistema de registro centralizado e altamente dimensionável. O sistema precisa analisar e indexar esses registros para que possam ser facilmente pesquisados por padrões ou texto e agrupados ou filtrados por atributos como host, microsserviço, período de tempo ou região para facilitar a pesquisa. Também é uma boa prática seguir uma estrutura ou um esquema predefinido e a mesma terminologia em diferentes eventos dentro de um microsserviço e em microsserviços separados. As linhas de registro devem ser fáceis de ler por humanos, mas também facilmente legíveis por máquinas, para que possam ser analisadas, agrupadas e analisadas com eficiência. Isso pode ser extremamente importante quando nos deparamos com um problema sensível ao tempo que afeta os usuários e precisamos chegar rapidamente à raiz do problema. Alguns exemplos de estruturas de log incluem o log Fmt, que estrutura os logs como pares de valores-chave, Json e XML.



A próxima prática recomendada é atribuir um nível de registro ou gravidade a cada linha de registro, dependendo da estrutura ou do sistema que usamos. Há diferentes níveis de registro e diferentes números de níveis de registro, mas os mais comuns são trace, debug information, warning, error and fatal.



Isso acrescenta uma dimensão adicional aos nossos registros, que podem ser divididos e filtrados, o que ajuda a reduzir o ruído e a fadiga dos alertas.



Por exemplo, exceções e erros que afetam o usuário precisam ser registrados como erro e fatal, respectivamente. Dessa forma, se formos um engenheiro de plantão e recebermos um alerta no meio da noite de que algo está dando errado, poderemos pesquisar os registros e filtrar apenas por erro e fatal, descobrir o que exatamente aconteceu e tomar as medidas corretas. Também podemos ter ferramentas automatizadas que pesquisam e agrupam periodicamente os eventos de acordo com esses níveis de gravidade. Então, essas ferramentas podem nos alertar ou criar um tíquete e atribuí-lo automaticamente para que alguém trabalhe nele.



Da mesma forma, os eventos que indicam possíveis problemas, como alto tempo de processamento de solicitações de saída ou recebimento de solicitações contendo valores inesperados, devem ser registrados no nível de aviso. Dessa forma, podemos filtrar esse nível de registro e, possivelmente, evitar problemas futuros abordando esses eventos. Finalmente, se formos um desenvolvedor investigando um problema muito complexo e precisarmos acompanhar todos os eventos que aconteceram em uma instância específica do aplicativo, poderemos examinar as informações em todos os níveis de registro, o que inclui os detalhes mais refinados registrados nos níveis de depuração e rastreamento.



A próxima prática recomendada para o registro em log é usar um ID exclusivo, geralmente chamado de ID de correlação, para cada solicitação ou transação de usuário e adicionar esse ID a cada linha de registro correspondente a um evento ou etapa e ao processamento dessa solicitação ou transação. Como cada instância de microsserviço provavelmente está processando várias solicitações de usuários simultaneamente. Isso ajuda a pesquisar e filtrar apenas os eventos relacionados à solicitação em questão. Ele também pode nos ajudar a ver a sequência de eventos de uma determinada solicitação em vários microsserviços.



A próxima prática recomendada é fornecer o máximo possível de informações contextuais para cada linha de registro. Por exemplo, se registrarmos um erro ou uma exceção, queremos adicionar o rastreamento de pilha para depurar e entender como chegamos a essa linha de código. Mas também queremos incluir os parâmetros que levaram a esse erro. Se tivermos uma consulta ao banco de dados que levou muito tempo para ser concluída, registrar a consulta exata e o conteúdo da solicitação que a acionou pode nos ajudar a entender como esse problema ocorreu e quais medidas podemos tomar para atenuá-lo. Alguns pontos de dados comuns que queremos incluir em quase todas as linhas de registro incluem o nome do serviço que emitiu o evento de registro, o nome do host em que o evento ocorreu, o ID do usuário ou algum outro identificador que possa adicionar mais contexto a quem iniciou a operação e, é claro, o carimbo de data/hora de quando o evento ocorreu. Com relação a isso, também temos duas considerações importantes a ter em mente. Primeiro, devemos registrar apenas as informações essenciais para a depuração porque, em um sistema de grande escala, o armazenamento e o processamento podem ser muito caros. A segunda consideração é que nunca devemos registrar informações confidenciais ou de identificação pessoal, como nomes de usuário, senhas, números de previdência social, e-mails, números de cartão de crédito e assim por diante. Embora esses dados possam ser úteis na solução de problemas. Isso representa um enorme risco legal para a empresa no caso de uma violação de segurança. Isso também adiciona muita complexidade em relação à segurança e à retenção de dados, à conformidade e, em geral, é simplesmente antiético. Ninguém quer que um engenheiro aleatório que esteja solucionando um problema não relacionado na produção tenha acesso às nossas informações pessoais, especialmente se não precisar delas para corrigir o problema.



## Resumo:

## O Que é Registro em Log?

O registro em log é uma das formas mais simples de capturar o estado de um aplicativo. Cada linha de log representa um evento ou ação, como o recebimento de uma solicitação, a execução de uma consulta ao banco de dados ou o início de um processamento complexo. Logs também registram erros, exceções e os parâmetros envolvidos, ajudando na identificação de problemas e na prevenção de falhas futuras por meio de testes adicionais.

Em sistemas baseados em microsserviços, milhares de instâncias podem gerar milhões de linhas de log diariamente, tornando inviável analisá-las manualmente. Para gerenciar esse volume, os logs devem ser centralizados e organizados de forma que possam ser indexados e pesquisados eficientemente.



## Práticas Recomendadas para Registro Distribuído

## 1. Centralização dos Logs

Utilize um sistema centralizado e escalável para coletar, indexar e analisar logs. Isso permite:

Pesquisar padrões ou texto rapidamente.

Filtrar logs por atributos como microsserviço, host, período ou região.

## 2. Formato Padronizado e Estruturado

Adote um esquema predefinido para garantir que os logs sejam legíveis por humanos e máquinas. Exemplos de formatos incluem JSON, XML ou logfmt, que estruturam os dados como pares chave-valor.

## 3. Níveis de Log

## Atribua níveis de severidade a cada entrada de log, como:

Trace: Eventos extremamente detalhados, usados em depuração avançada.

Debug: Informações úteis para desenvolvimento, mas não críticas em produção.

Info: Eventos normais do sistema.

Warning: Possíveis problemas que merecem atenção.

Error: Falhas que afetam usuários.

Fatal: Erros graves que interrompem a operação.

Essa classificação facilita a filtragem e priorização, reduzindo o "ruído" e permitindo que problemas críticos sejam tratados rapidamente.

## 4. IDs de Correlação

Inclua um identificador exclusivo para cada solicitação ou transação em todas as linhas de log relacionadas. Isso possibilita:

Rastrear eventos específicos em microsserviços.

Visualizar o fluxo completo de uma transação, incluindo interações assíncronas.

## 5. Contexto Rico nos Logs

## Cada linha de log deve incluir informações úteis para depuração, como:

Nome do serviço e host que geraram o log.

IDs de usuários ou identificadores relevantes.

Carimbo de data/hora do evento.

Dados detalhados, como consultas SQL, parâmetros de entrada e rastreamentos de pilha em caso de erros.

## 6. Minimização e Privacidade dos Dados

Registre apenas o essencial: Dados irrelevantes podem aumentar custos de armazenamento e processamento.

Proteja informações sensíveis: Nunca registre dados como senhas, números de cartão de crédito ou informações de identificação pessoal (PII). Isso reduz riscos legais e garante conformidade com regulamentações de segurança e privacidade.



## Benefícios do Registro Distribuído

O registro distribuído permite diagnosticar problemas complexos em sistemas distribuídos com eficiência. Quando bem implementado, ele fornece:

Rastreamento detalhado de erros em tempo real.

Insights rápidos sobre o comportamento do sistema.

Suporte para automação de alertas e abertura de tíquetes com base em logs críticos.

Ao seguir essas práticas recomendadas, é possível otimizar a observabilidade e garantir que problemas sejam resolvidos com agilidade e segurança.







## Metrics

Neste capítulo, continuaremos a discutir os três pilares da observabilidade. E agora vamos falar sobre o segundo pilar, que são as métricas. Bem, primeiro, faça uma rápida introdução às métricas e por que precisamos delas. Em seguida, ilustraremos o problema de coletar muitas métricas que não são necessárias. E, por fim, aprenderemos os cinco tipos de sinais nos quais devemos nos concentrar para obter o máximo de observabilidade e o mínimo de complexidade.



Então, vamos começar a discussão sobre métricas. As métricas são sinais mensuráveis ou responsáveis do software que nos ajudam a monitorar a integridade e o desempenho do sistema. Normalmente, as métricas são amostradas regularmente, de modo que podemos ver uma progressão contínua que nos ajuda a monitorar nosso sistema e detectar anomalias quando elas ocorrem. E eles geralmente vêm em valores numéricos. Assim, podemos quantificá-los facilmente e definir alertas com base em seus valores diretos ou derivados, pois são apenas números.



De todos os três pilares da observabilidade, eles são os mais fáceis de coletar, visualizar e organizar em painéis. Por exemplo, um painel pode nos mostrar todos os sinais vitais de um determinado microsserviço ou pode comparar cada métrica com seu valor histórico de antes do lançamento ou de uma alteração significativa no sistema. Esses painéis de produção são uma ferramenta essencial para nós quando um problema de produção precisa de nossa atenção. Em vez de ter que pesquisar e ler centenas de linhas de registro, podemos examinar um ou talvez dois painéis e ter uma ideia do que está acontecendo. No entanto, como uma equipe que possui um microsserviço, é uma boa pergunta, devemos nos perguntar quais sinais devemos medir, coletar e monitorar, e por que não deveríamos simplesmente coletar todos eles?



Portanto, a primeira coisa importante a entender é que o número de sinais diferentes que podemos coletar é muito grande no nível dos recursos. Podemos medir muitos sinais que podem ou não ser úteis em diferentes situações, mas, além disso, podemos instrumentar nosso aplicativo e medir qualquer coisa, desde o número de solicitações que recebemos por minuto até o número de vezes que uma determinada parte crítica da lógica é executada. No entanto, coletar tudo o que podemos medir é um grande antipadrão. Em primeiro lugar, coletar e armazenar tantos sinais de cada servidor ou contêiner pode se tornar muito caro, especialmente quando estamos falando de um sistema de grande escala com dezenas ou até centenas de microsserviços. Mas mesmo que possamos arcar com o custo e lidar com o armazenamento de todas essas métricas, temos outro problema, que é a sobrecarga de informações. Digamos que recebamos uma página no meio da noite informando que nosso site não está carregando ou está muito lento para a maioria dos usuários. Agora, considerando todas as métricas que estamos coletando, qual painel devemos analisar? E mesmo que saibamos qual painel devemos examinar, o número de gráficos em cada painel não caberá na tela. Portanto, é muito difícil encontrar as anomalias. E mesmo se notarmos uma mudança em alguma métrica, será muito difícil entender qual é o sintoma e qual é a causa. Portanto, em vez disso, devemos ser inteligentes quanto às métricas que coletamos.



Felizmente, podemos aproveitar décadas de experiência de empresas que executam grandes sistemas distribuídos e microsserviços em produção e nos concentrar em cinco tipos de sinais que nos darão o máximo de informações e o mínimo de ruído. Essas cinco categorias são baseadas em duas fontes de conhecimento.

## The Five (Golden) Types of Signals:

## Traffic

## Errors

## Latency

## Saturation

## Utilization

O primeiro é o Google Searches for Gold and Signals, que se concentra nas métricas voltadas para o usuário, e o segundo é o método de uso de Brendan Gregg, que se concentra mais nos recursos do sistema. Assim, combinando esses dois recursos, temos cinco categorias de sinais, que são erros de tráfego, saturação de latência e utilização.



O tráfego é a quantidade de demanda que está sendo colocada em nosso sistema por unidade de tempo. Por exemplo, podemos medir o número de solicitações Http por segundo ou minuto para um microsserviço que recebe tráfego Http. Também podemos medir o número de consultas ou transações por segundo ou por minuto para um banco de dados e para um agente de mensagens. Podemos medir o número de eventos que ele recebe e o número de eventos que ele entrega aos consumidores. Agora, em alguns casos em que uma única solicitação a um microsserviço resulta em muitas solicitações de saída, também vale a pena medir o número de solicitações de saída e de entrada separadamente. E isso porque as conexões abertas com outros serviços consomem recursos do sistema e podem afetar diretamente o desempenho do microsserviço.



A próxima categoria de métricas são os erros. Quando medimos os erros, estamos interessados na taxa de erro e no tipo de erro que estamos obtendo, se possível, a taxa de erro pode ser um ótimo sinal para definir um alerta, pois se a taxa de erro aumentar repentinamente, é provável que os usuários já tenham sido afetados. Agora, no caso de um aumento no número de exceções em nosso aplicativo, talvez não possamos mostrar o tipo de erro como um valor numérico, portanto, adiamos essas informações para o registro. No entanto, se começarmos a receber um código de status de resposta Http diferente de 200 de um serviço do qual dependemos, poderemos usar isso como uma métrica que será muito útil na solução de problemas de produção. Além disso, em sistemas sensíveis à latência, podemos até contar as respostas bem-sucedidas como erros se elas excederem algum limite de latência que definimos antecipadamente para um microsserviço orientado por eventos. Também podemos medir a taxa de eventos que ele não consegue processar e o motivo da falha, se for possível classificar em um agente de mensagens, podemos medir os sinais de erro, como o número de eventos que não foram entregues aos clientes. E, no lado do banco de dados, podemos medir o número de transações abortadas, falhas de disco e assim por diante.



O próximo tipo de sinal é a latência. Latência é o tempo que um serviço leva para processar uma solicitação. Embora essa métrica pareça bastante simples, há alguns aspectos a serem considerados para medi-la corretamente. A primeira consideração importante é não olhar apenas para a latência média, mas sempre considerar a distribuição completa da latência. Por exemplo, vamos supor que nosso microsserviço receba cerca de 1.000 solicitações por minuto. 95% dessas solicitações são processadas em 50 milissegundos e 5% delas levam 5.000 milissegundos para serem processadas. Portanto, nossa latência média por minuto é de cerca de 300 milissegundos, o que é muito bom para um sistema voltado para o usuário. No entanto, isso esconde completamente o fato de que 5% dos nossos usuários precisam esperar cinco segundos para que o site inteiro seja carregado. Então, se temos um milhão de usuários por dia visitando nosso site, 50.000 deles têm uma experiência de usuário tão ruim que provavelmente mudarão para o nosso concorrente e nunca mais voltarão.



Portanto, se em vez de analisar a latência média, analisarmos o 95º percentil da latência por minuto, veremos que uma parte significativa de nossas solicitações leva um tempo excessivo para ser concluída, o que provavelmente indica um gargalo de desempenho em nosso sistema. A segunda consideração importante é separar a latência das operações bem-sucedidas das operações com falha. Se misturarmos as solicitações bem-sucedidas e as que falharam, poderemos obter os dados errados. Por exemplo, se falharmos rapidamente quando não conseguirmos processar uma solicitação, poderemos artificialmente fazer com que nossa latência total pareça melhor do que é. Da mesma forma, se demorarmos muito para responder a um erro, talvez não tenhamos conhecimento dele. Se esses erros ocorrem raramente e as solicitações bem-sucedidas demoram muito para serem processadas. No entanto, se coletarmos e monitorarmos a latência das solicitações bem-sucedidas e das solicitações com falha separadamente, poderemos ter uma boa visão do que nossos clientes experimentam em ambos os cenários.



Agora vamos falar sobre o quarto tipo de sinal, que é a saturação. Medidas de saturação, quão sobrecarregado ou cheio está um serviço ou um determinado recurso. Essa métrica é muito importante para qualquer tipo de sistema que tenha uma fila, seja uma fila externa, como um message broker, ou uma fila interna em nosso microsserviço ou CPU. Quando temos muitas coisas armazenadas em uma fila, isso pode indicar que nosso sistema não consegue acompanhar a demanda atual. Por exemplo, se o tópico em um agente de mensagens que armazena pedidos de compra de usuários continuar crescendo, isso provavelmente indica que temos algum problema de escalabilidade em um dos serviços que consomem esses eventos. Outro exemplo é se a fila de rede de solicitações que vão para um banco de dados continuar crescendo, o que pode indicar que nosso dispositivo de armazenamento não é suficientemente rápido e que precisamos atualizar nosso hardware ou, como alternativa, se for um banco de dados na memória, talvez seja necessário fragmentá-lo e distribuir os dados em várias instâncias do banco de dados. Por fim, se algum trabalho dentro de uma instância de microsserviço continuar crescendo, isso pode indicar que alguma parte da nossa lógica está muito lenta e que essa instância de microsserviço poderá falhar em breve com uma exceção de falta de memória. Por fim, ter visibilidade da saturação também pode explicar por que nossos usuários de repente têm uma latência mais longa ou por que as solicitações de outros serviços estão atingindo o tempo limite.



O último tipo de sinal é a utilização. A utilização é usada para medir a ocupação de um determinado recurso em um período de tempo. Isso normalmente se aplica a recursos com capacidade limitada, como CPU, memória, espaço em disco e assim por diante. É importante ressaltar que, na maioria dos casos, veremos a degradação do desempenho antes de atingirmos 100% de utilização dos recursos. Portanto, é importante definir alertas antes de atingirmos esse nível crítico. Por exemplo, se percebermos que a utilização da CPU em nossas instâncias de microsserviço está crescendo e se aproximando de 80%, precisaremos expandir e adicionar mais instâncias de serviço. Caso contrário, quando ultrapassarmos o limite de 80% de utilização da CPU, poderemos começar a ter latência mais alta e outros problemas. Da mesma forma, se percebermos que nosso banco de dados está perto de ficar sem armazenamento, precisaremos adicionar mais instâncias de banco de dados para acompanhar a quantidade crescente de dados. Também é importante ressaltar que queremos medir a utilização com maior granularidade e não apenas uma média de vários minutos. Caso contrário, perderemos os curtos períodos de alta utilização que podem ser atribuídos a gargalos de desempenho ou outras ineficiências em nosso processamento.



Agora, para concluir, quero salientar que esses cinco tipos de sinais não são necessariamente os únicos que precisamos coletar. Portanto, dependendo do negócio, lógica e as especificidades do nosso sistema ou microsserviço, podemos coletar métricas adicionais que podem aumentar ainda mais a nossa observabilidade. No entanto, esses cinco tipos de sinais são os mais comuns que se aplicam a qualquer sistema e nos proporcionam o maior valor ao rastreá-los.



## Resumo:

## O que são métricas?

Métricas são sinais mensuráveis que refletem o estado de saúde e desempenho de um sistema. Elas são coletadas periodicamente, permitindo a análise contínua e a detecção de anomalias em tempo real. Por serem valores numéricos, as métricas podem ser facilmente quantificadas e utilizadas para definir alertas baseados em tendências ou valores específicos.

Entre os pilares da observabilidade, as métricas são as mais fáceis de coletar, visualizar e organizar em painéis. Esses painéis permitem obter uma visão consolidada de indicadores importantes de um microsserviço, possibilitando comparações com valores históricos e fornecendo uma referência imediata em casos de problemas de produção. No entanto, é fundamental decidir quais sinais medir e monitorar, evitando a coleta indiscriminada de métricas.



## Os problemas da coleta excessiva

A quantidade de métricas que podemos coletar em um sistema é imensa, desde informações básicas sobre recursos até detalhes específicos da lógica de negócio. Embora pareça tentador coletar tudo o que for possível, essa abordagem é um grande antipadrão.

Primeiro, a coleta e o armazenamento de métricas em larga escala podem gerar custos elevados, especialmente em sistemas distribuídos com centenas de microsserviços. Além disso, o excesso de informações dificulta a análise. Em uma situação crítica, como uma falha de produção, é improvável que os engenheiros consigam identificar rapidamente as métricas relevantes em meio a um volume excessivo de dados. Isso pode levar a diagnósticos confusos e atrasados.

Portanto, a abordagem mais eficaz é priorizar a coleta de métricas que realmente agreguem valor. Para isso, podemos nos basear em boas práticas amplamente reconhecidas, que identificam cinco tipos principais de sinais para monitoramento eficiente: tráfego, erros, latência, saturação e utilização.



## Os cinco tipos principais de sinais



## 1. Tráfego

O tráfego mede a demanda colocada no sistema por unidade de tempo, como o número de solicitações HTTP por segundo em um microsserviço, consultas em um banco de dados ou eventos em um agente de mensagens.

Também é útil diferenciar o tráfego de entrada e de saída, especialmente quando solicitações para outros serviços podem impactar diretamente os recursos do sistema e seu desempenho geral.

## 2. Erros

A taxa de erro mede falhas no sistema e ajuda a identificar problemas críticos rapidamente. Isso inclui códigos de status HTTP diferentes de 200, exceções no aplicativo, transações abortadas ou eventos não entregues em sistemas de mensagens.

Alertas baseados na taxa de erro permitem ações rápidas antes que os problemas afetem significativamente os usuários. É importante classificar os tipos de erros, quando possível, para facilitar a análise e priorização.

## 3. Latência

A latência é o tempo necessário para processar uma solicitação. Ao medir latência, é crucial considerar não apenas a média, mas também percentis (como o 95º ou 99º), que revelam o impacto em grupos de usuários específicos.

Além disso, a separação entre latência de solicitações bem-sucedidas e com falhas oferece uma visão mais precisa sobre a experiência do usuário e a eficiência do sistema.

## 4. Saturação

A saturação mede o quanto um recurso ou serviço está sobrecarregado. Por exemplo, filas de mensagens que crescem continuamente podem indicar gargalos de escalabilidade. Da mesma forma, filas de solicitações acumuladas no banco de dados ou na CPU podem sinalizar limitações de hardware ou necessidade de otimizações no software.

Monitorar a saturação ajuda a identificar problemas antes que afetem a experiência do usuário ou causem falhas críticas no sistema.

## 5. Utilização

A utilização reflete o uso de recursos limitados, como CPU, memória ou armazenamento. É fundamental configurar alertas antes que o uso atinja níveis críticos, pois a degradação do desempenho frequentemente ocorre antes de 100% de utilização.

Granularidade na coleta é essencial para capturar picos momentâneos que podem indicar gargalos ou ineficiências.



## Considerações finais

Embora esses cinco tipos de sinais sejam os mais comuns e úteis para a maioria dos sistemas, métricas adicionais podem ser necessárias dependendo das particularidades do negócio ou do sistema. No entanto, focar nesses sinais proporciona uma base sólida para maximizar a observabilidade, garantindo uma análise eficiente e uma resposta rápida a problemas de produção.





## Distributed Tracing



Agora, finalmente chegamos ao terceiro pilar da Observabilidade. Rastreamento distribuído com métricas e registro distribuído. Você pode estar se perguntando por que precisamos de um terceiro método para a observabilidade. Portanto, começaremos discutindo o que é o rastreamento distribuído e por que precisamos dele. Em seguida, discutiremos algumas terminologias e o que é realmente necessário para habilitar o rastreamento distribuído para microsserviços. E, por fim, discutiremos alguns desafios do uso do rastreamento distribuído em microsserviços e na arquitetura orientada por eventos.



Então, vamos começar com alguma motivação para o rastreamento distribuído. Para ilustrar por que precisamos de outra solução, vamos considerar um cenário real de uma transação ordenada em um sistema de comércio eletrônico com microsserviços e arquitetura orientada por eventos. Quando um usuário faz um pedido de compra de um de nossos produtos e essa solicitação vai para o gateway da API. Primeiro, o API Gateway se comunica com o serviço de autenticação para garantir que o usuário seja realmente quem diz ser e esteja autorizado a fazer a compra. Depois disso, o gateway de API envia a solicitação HTTP para uma das instâncias de serviço solicitadas por meio de um balanceador de carga. O serviço de pedidos registra o pedido em seu banco de dados, emite um evento para um tópico em um message broker e responde ao usuário. Depois disso, temos uma longa cadeia de eventos e solicitações que passam por vários microsserviços, serviços de terceiros e tópicos do message broker. E quando toda a transação é concluída, o serviço de notificação envia uma notificação por push e uma confirmação por e-mail para o usuário. Esse e-mail contém o recibo de pagamento e o número de referência do pedido, além de um URL no qual é possível rastrear o pedido.



Agora vamos imaginar que, de repente, alguns usuários comecem a reclamar que nunca receberam a confirmação por e-mail de seus pedidos e outros usuários comecem a reclamar que recebem a confirmação por e-mail. Mas muitas horas ou até um dia depois de fazer o pedido. Com tantos microsserviços envolvidos na troca de solicitações e mensagens assíncronas, o problema pode estar em qualquer lugar. Então, por onde começamos a investigação? Começamos a examinar os painéis de métricas de cada microsserviço nesse processo? Ou começamos a ler milhares de entradas de registro de cada microsserviço e agente de mensagens para encontrar algo que se destaque? Para tornar as coisas ainda mais difíceis, cada microsserviço é executado como um grupo de instâncias em computadores diferentes, atrás de um balanceador de carga ou de um message broker. E cada message broker em si é distribuído e cada banco de dados também é distribuído. E, além disso, como parte do processo, também chamamos APIs de terceiros das quais não temos nenhuma visibilidade. Mas essa não é a história completa. Em um sistema do mundo real, podemos ter centenas de microsserviços em que cada microsserviço desempenha algum papel no processamento de um fluxo de solicitação ou de uma transação.



Portanto, em uma arquitetura complexa e em constante evolução, é quase impossível para qualquer ser humano lembrar quais microsserviços estão envolvidos no processamento de um determinado tipo de solicitação ou em que ordem. Portanto, é aqui que entra o rastreamento distribuído.



O rastreamento distribuído é um método de rastreamento de solicitações à medida que elas fluem, o sistema inteiro começa no dispositivo do cliente e passa por nossos serviços de back-end e bancos de dados. À medida que a solicitação está sendo rastreada, coletamos informações críticas de desempenho sobre o tempo em que cada parte do sistema está processando a solicitação. Isso permite que os engenheiros visualizem todo o fluxo e compreendam todos os componentes envolvidos no processamento da solicitação e o tempo que cada componente levou para fazer seu trabalho. Isso é extremamente valioso para a solução de bugs ou erros que levam a um comportamento incorreto ou a gargalos de desempenho. Normalmente, o rastreamento distribuído não é suficiente para nos dizer o que exatamente está acontecendo, mas é suficiente para restringir nossa pesquisa a um componente específico ou a um problema de comunicação entre dois componentes.



Depois de sabermos onde o problema está acontecendo, podemos usar os outros pilares da observabilidade, que são os registros e as métricas, para depurar ainda mais o problema. Agora que entendemos o que é o rastreamento distribuído e por que precisamos dele, vamos nos aprofundar um pouco mais em como ele funciona.



Quando a solicitação inicial está sendo feita, geramos uma ID de rastreamento exclusiva e a colocamos em um objeto chamado contexto de rastreamento. Esse objeto de contexto de rastreamento contém dados importantes sobre todo o rastreamento à medida que a solicitação flui pelos serviços. Esse contexto é propagado normalmente por meio de cabeçalhos HTTP ou cabeçalhos de mensagens dentro de eventos. Mas apenas passar o contexto de rastreamento de serviço para serviço não é suficiente para que as instâncias do aplicativo coletem os dados de rastreamento. Precisamos instrumentá-los usando uma biblioteca de instrumentação de rastreamento ou SDK. Essas bibliotecas de rastreamento são fornecidas em diferentes linguagens de programação, portanto, mesmo se tivermos um sistema poliglota, ainda poderemos obter um rastreamento completo. Agora, assim que a instância de serviço recebe o contexto de rastreamento, ela coleta os dados necessários e propaga o contexto para o próximo serviço. Assim, no final da transação, cada instância de serviço envolvida tem suas próprias medições e dados que podem ser agregados posteriormente pela ID de rastreamento para visualizar todas as partes de uma transação e quanto tempo cada parte da transação levou. O rastreamento é dividido em unidades lógicas de trabalho que são chamadas de períodos. Esses intervalos de rastreamento podem ser de granulação grossa, como o processamento de uma solicitação por um serviço ou uma consulta por um banco de dados ou podem ser criados manualmente pelos desenvolvedores usando a biblioteca de instrumentação. Assim, diferentes unidades de trabalho em um serviço podem ser visualizadas e medidas separadamente. Dessa forma, se uma parte lógica parecer mais lenta do que o normal, poderemos investigá-la mais a fundo como um possível gargalo de desempenho. E se um intervalo esperado estiver faltando, talvez tenhamos um bug que precise ser depurado para aumentar ainda mais a granularidade. Podemos conectar partes relacionadas do trabalho organizando os intervalos em uma hierarquia com um relacionamento pai-filho. Assim, por exemplo, se depois de inspecionar o rastreamento, percebermos que um determinado serviço está lento para processar uma solicitação, poderemos expandir esse intervalo e ver seus filhos e os intervalos de seus filhos. Nela, podemos ver que uma das consultas ao banco de dados estava surpreendentemente lenta, o que agora podemos investigar procurando por mensagens de registro específicas nesse serviço.



Agora vamos falar sobre o outro aspecto do rastreamento distribuído, que é como os dados são coletados dos serviços e agregados a essas exibições visuais. Há muitas soluções e fornecedores com diferentes arquiteturas e implementações, mas a abordagem geral é a seguinte. Depois que os dados de rastreamento são coletados em cada instância de serviço, eles são extraídos por um agente que é executado como um processo separado no mesmo host de cada instância de serviço. Em seguida, esses agentes enviam os dados de rastreamento para uma fila central ou tópico em um message broker. Em seguida, todos os dados de rastreamento provenientes de vários serviços são analisados, agregados, indexados e armazenados em um banco de dados por um processador de Big Data. Posteriormente, um desenvolvedor pode consultar e visualizar esses dados usando uma UI de rastreamento no navegador. Agora, como seria de se esperar, com todos esses benefícios do rastreamento distribuído, ele também vem com uma quantidade razoável de desafios dos quais é importante estar ciente. O primeiro desafio, que já mencionamos, é o fato de que precisamos instrumentar manualmente nosso código para coletar dados que possam ser usados para rastreamento distribuído. Na maioria dos casos, não é um grande esforço, mas exige que dependamos e carreguemos uma determinada biblioteca. Aprenda a usá-lo corretamente e, às vezes, adicione manualmente essa instrumentação quando necessário. Caso contrário, se não fizermos esse trabalho manual quando realmente precisarmos investigar o problema de produção, nossos tempos de vida útil poderão ser menores. Muito amplos, sem granularidade ou dados importantes ou, em casos extremos, se usarmos a biblioteca de instrumentação incorretamente, nossos rastreamentos poderão ser interrompidos e, portanto, inúteis.



O segundo desafio é o custo. Em primeiro lugar, precisamos executar um agente em cada host de microsserviço que consome sua própria CPU e memória. Em seguida, os dados coletados devem ser enviados pela rede, o que requer largura de banda adicional. Em seguida, precisamos executar um pipeline de big data com sua própria infraestrutura para processar esses registros de rastreamento provenientes de diferentes serviços. Esse pipeline de big data, é claro, vem com seu próprio custo de manutenção, mas, de longe, o maior desafio é o custo de armazenar esses traços em um banco de dados e retê-los pelo menos por algumas semanas. Para que os desenvolvedores possam encontrá-los caso precisem depurar um problema. Se pensarmos em alguns milhões de solicitações por dia, em que cada solicitação flui por algumas dezenas de microsserviços, o volume de dados que precisamos armazenar pode ser muito alto. Portanto, para manter os custos de armazenamento e de rede sob controle, a maioria das empresas usa amostragem no lado do cliente, o que, às vezes, significa que podemos obter um rastreamento de mil ou talvez até 10.000 solicitações. Isso reduz nossos custos de armazenamento, mas com uma taxa de amostragem tão alta, às vezes é difícil encontrar um rastreamento que possa reproduzir um problema específico que estamos tentando depurar. Mas, além disso, também temos outro problema, que é o tamanho dos rastros e a quantidade de informações contidas em cada um deles. As implantações típicas de microsserviços e de arquitetura orientada por eventos geralmente envolvem tantos componentes que um único rastreamento pode ser tão grande que é difícil para um ser humano examiná-lo, quanto mais usá-lo. Em minha experiência pessoal, alguns dos traços que vi em produção eram tão grandes que a interface do usuário de rastreamento não conseguia nem carregá-los, portanto, era impossível sequer dar uma olhada neles. E muitas empresas estão enfrentando problemas semelhantes. Mas, apesar de todos esses desafios, o rastreamento distribuído é uma ferramenta de depuração muito poderosa e essencial para microsserviços e arquitetura orientada por eventos, e muitas vezes é atribuído a ele o restabelecimento da confiança entre os desenvolvedores de que, se ocorrerem problemas na produção, eles terão as ferramentas para solucioná-los e encontrar a causa raiz.



## Soluções de Rastreamento Distribuído

## Estruturas de Instrumentação de Rastreamento Distribuído

OpenTelemetry - OpenTelemetry é uma coleção de APIs, SDKs e ferramentas para instrumentar, coletar e exportar métricas, logs e traces. É de código aberto e está disponível em muitas linguagens de programação , como C++ , #/.NET , Erlang/Elixir , Go , Java , JavaScript , PHP , Python , Ruby , Rust e Swift . OpenTelemetry também é uma especificação que descreve os requisitos e expectativas entre linguagens para todas as implementações do OpenTelemetry.



## Backends de rastreamento distribuído

Jaeger - Plataforma de rastreamento distribuída de código aberto que é nativa da nuvem, infinitamente escalável e 100% gratuita. Ela permite o monitoramento de fluxos de trabalho distribuídos, rastreando as causas raiz de gargalos de desempenho e analisando dependências de serviço.
Use OpenTelemetry para instrumentação.

Zipkin - Outro sistema de rastreamento distribuído de código aberto. Seus dados servidos à UI são armazenados na memória ou persistentemente dentro do Apache Cassandra ou Elasticsearch. Originalmente desenvolvido no Twitter em 2010 e baseado nos artigos Dapper do Google.
Suporta uma variedade de estruturas de instrumentação oficiais e criadas pela comunidade .

Uptrace - Uptrace é uma plataforma de observabilidade baseada em OpenTelemetry que ajuda você a monitorar, entender e otimizar sistemas distribuídos.
É uma solução comercial baseada em nuvem que oferece suporte a uma variedade de recursos, como monitoramento de desempenho de aplicativos, coleta e visualização de métricas, injeção e análise de logs e muito mais.



## Resumo:



## Motivação para o Rastreamento Distribuído

Considere um sistema de e-commerce baseado em microsserviços. Quando um cliente realiza um pedido, a solicitação passa por uma série de etapas: o gateway de API verifica autenticação, encaminha ao serviço de pedidos, que registra a transação, publica um evento em um broker e retorna ao cliente. Outros serviços, como pagamento e notificações, entram em ação, resultando no envio de e-mails e push notifications ao cliente. Em sistemas complexos, como esse, onde há centenas de microsserviços interagindo, problemas como atrasos ou falhas podem surgir em qualquer etapa.

Quando clientes reclamam de confirmações de pedido atrasadas ou ausentes, identificar a origem do problema em meio a centenas de serviços distribuídos é desafiador. Painéis de métricas e logs podem ajudar, mas frequentemente são insuficientes para fornecer uma visão clara e completa. É nesse contexto que o rastreamento distribuído se torna indispensável.



## O que é o Rastreamento Distribuído

O rastreamento distribuído permite rastrear solicitações em todo o sistema, desde o cliente até os serviços de backend e bancos de dados. Ele coleta dados de desempenho, como tempos de processamento de cada componente, criando uma visão completa do fluxo da solicitação. Isso facilita a identificação de gargalos, falhas de comunicação e comportamentos inesperados.

Embora ele não forneça respostas definitivas, restringe a investigação a componentes ou interações específicas. Após identificar o ponto problemático, logs e métricas podem ser utilizados para depurar em maior detalhe.



## Funcionamento do Rastreamento Distribuído

Criação e Propagação do Contexto de Rastreamento:
Cada solicitação gera uma ID de rastreamento única, armazenada em um contexto propagado via cabeçalhos HTTP ou mensagens. Para coletar dados, os serviços precisam ser instrumentados com bibliotecas ou SDKs compatíveis, que capturam e encaminham informações durante o fluxo.

Agregação de Dados:
Os dados coletados por cada serviço são enviados para um agente local, que os transfere para uma fila central. Um pipeline de processamento agrega e indexa os dados, permitindo sua visualização em interfaces específicas.

Estruturação dos Dados:
O rastreamento é dividido em "spans" (intervalos de trabalho), que representam atividades específicas. Esses spans podem ser hierárquicos, permitindo análises detalhadas de cada subprocesso envolvido na transação.



## Desafios do Rastreamento Distribuído

Instrumentação Manual:
A instrumentação exige esforço para integrar bibliotecas, configurá-las corretamente e, em alguns casos, adicionar spans manualmente. Erros nessa etapa podem comprometer a eficácia do rastreamento.

## Custo Operacional:
O rastreamento consome recursos significativos:

Agentes em cada host aumentam o uso de CPU e memória.

Dados precisam ser transmitidos e armazenados, gerando custos de largura de banda e infraestrutura.

A retenção de dados para análise prolongada exige armazenamento considerável, especialmente em sistemas com milhões de solicitações diárias.

Amostragem e Granularidade:
Para reduzir custos, a amostragem limita o volume de dados coletados, mas pode dificultar a análise de problemas específicos. Além disso, rastreamentos complexos podem gerar dados tão extensos que se tornam difíceis de interpretar.



## Conclusão

Apesar dos desafios, o rastreamento distribuído é uma ferramenta essencial em arquiteturas baseadas em microsserviços e eventos. Ele restabelece a confiança dos desenvolvedores ao fornecer visibilidade sobre sistemas complexos e suporte para identificar causas raiz de problemas em produção. Com uma implementação cuidadosa e ferramentas adequadas, é possível aproveitar ao máximo seus benefícios.







## Implantação de microsserviços e arquitetura orientada a eventos em produção





Implantação de microsserviços - Máquina virtual em nuvem, hosts dedicados e instâncias



Agora que sabemos como desenvolver, arquitetar, testar e solucionar problemas de microsserviços em produção, há apenas uma etapa importante que precisamos abordar: como implantar e executar microsserviços em produção. Portanto, iniciaremos a discussão abordando algumas opções de infraestrutura para a execução de microsserviços, com foco principal no ambiente de nuvem.



A primeira e mais comum maneira de implementar microsserviços no ambiente de nuvem é usar máquinas virtuais na nuvem. Como lembrete rápido, uma máquina virtual é um ambiente isolado, executado sobre um computador físico real. Essa máquina virtual funciona como um computador virtual com seu próprio sistema operacional e recursos virtuais, como CPU, memória, interface de rede e armazenamento. Esses recursos virtuais são alocados, gerenciados e mapeados para recursos reais no hardware físico por outra camada de software chamada hipervisor. Ao usar máquinas virtuais, o provedor de nuvem pode dividir cada servidor físico em várias VMs, e a quantidade de recursos alocados a cada VM depende de como a configuramos e de quanto pagamos por isso. Agora, cada VM pode executar uma instância diferente do mesmo microsserviço, uma instância separada de um microsserviço diferente ou até mesmo uma instância diferente de um microsserviço pertencente a um cliente de provedor de nuvem diferente. Essa propriedade é chamada de multitenancy.



Multitenancy (ou multitenência) é um modelo de arquitetura de software em que uma única instância de um sistema, aplicação ou recurso atende a múltiplos usuários ou "tenants" (inquilinos), garantindo que cada um deles tenha uma experiência isolada e segura. Esse conceito é amplamente utilizado em ambientes de cloud computing e virtual machines.



## Multitenancy em Cloud Computing:

Na nuvem, multitenancy permite que provedores de serviços (como AWS, Azure ou Google Cloud) utilizem a mesma infraestrutura física para atender diferentes clientes. Os recursos são compartilhados, mas cada tenant tem isolamento lógico para proteger dados, configurações e desempenho.

Exemplo: Um banco de dados multi-tenant pode armazenar os dados de vários clientes em uma única instância, mas garantir que cada cliente acesse apenas os seus dados, utilizando mecanismos como separação por namespace ou tabelas segregadas.



## Multitenancy em Virtual Machines:

Em ambientes de máquinas virtuais (VMs), multitenancy refere-se a diferentes clientes ou cargas de trabalho compartilhando a mesma infraestrutura física (host físico), enquanto as VMs fornecem isolamento para cada tenant.

Exemplo: Em um servidor físico, várias VMs podem ser atribuídas a diferentes clientes. Cada VM opera de forma independente, com seu próprio sistema operacional, aplicativos e dados, mas compartilha recursos como CPU, memória e armazenamento com outras VMs.



Por padrão, quando alugamos ou reservamos VMs na nuvem, não temos controle sobre quem mais está executando suas VMs no mesmo host, o que permite que o provedor de nuvem divida todos os seus servidores de forma muito eficiente, utilizando totalmente seu hardware. E isso, por sua vez, permite que eles nos ofereçam preços competitivos, o que torna as VMs de nuvem uma opção muito atraente para a execução de microsserviços. Portanto, a principal vantagem de usar máquinas virtuais na nuvem para executar microsserviços é o preço acessível e flexível. O modelo de preço típico para VMs de nuvem é o pagamento por uso, o que significa que pagamos apenas pelas VMs de nuvem que estamos alugando durante o período em que as alugamos. E a taxa para cada VM depende da memória da CPU e dos recursos de largura de banda da rede que solicitamos.



Agora, uma das desvantagens dessa implementação são os riscos de segurança devido à multitenancy. Teoricamente, quando executamos duas VMs no mesmo servidor, essas duas VMs ficam completamente isoladas uma da outra. Portanto, se essas duas VMs estiverem executando duas instâncias de banco de dados, por exemplo, e cada instância pertencer a uma organização completamente diferente, uma violação de segurança em uma das VMs não deverá representar um risco para a outra VM. No entanto, este é o mundo real. O hipervisor é um software que foi escrito por seres humanos, e toda a segurança e as configurações são gerenciadas e atualizadas também por seres humanos.



Portanto, na prática, é possível que um hacker obtenha acesso a uma VM que foi mal protegida pelos engenheiros de outra organização. E como o fornecedor da nuvem alocou nossa VM para ser executada no mesmo host, esse hacker pode conseguir invadir nosso sistema e roubar nossos dados. É claro que os fornecedores de nuvem e as empresas proprietárias do hipervisor fazem grandes esforços para evitar que isso aconteça. Portanto, a probabilidade de isso realmente acontecer é muito pequena. Entretanto, devido a problemas de conformidade em determinados setores, talvez não possamos tolerar nem mesmo esse pequeno risco.



Exemplos de setores que não podem se dar ao luxo de executar algumas partes de seus serviços em ambientes multitenant de nuvem incluem serviços bancários, de saúde e governamentais ou relacionados à segurança nacional. A segunda desvantagem da execução de microsserviços em ambientes Multitenants é o desempenho potencialmente inferior devido a um problema chamado vizinhança ruidosa (noisy neighborhood).

Simplesmente, no caso anterior, teoricamente, o hipervisor deve ser capaz de isolar e alocar completamente cada recurso de hardware para cada VM, conforme configurado com antecedência. Entretanto, na prática, nem todos os recursos podem ser alocados com precisão. Por exemplo, se o host tiver 16 núcleos de CPU, o hipervisor poderá facilmente dividir esses 16 núcleos igualmente. Portanto, cada VM recebe oito núcleos dedicados. No entanto, a largura de banda de rede de uma placa de rede ou o acesso a um barramento interno que transfere dados e para um dispositivo de armazenamento não podem ser facilmente racionados de forma precisa, e muitos outros recursos físicos dentro do computador não podem ser divididos porque, afinal, trata-se de um servidor físico. Além disso, o próprio hipervisor pode consumir um pouco de CPU e memória para seu próprio uso. Portanto, embora não haja muitos dados que sugiram que a execução de uma carga de trabalho muito intensa em uma VM possa afetar significativamente o desempenho da outra VM.



Na teoria e na prática, esse impacto ainda existe. Portanto, para serviços muito sensíveis à latência, como sistemas de negociação de alta frequência, jogos ou transmissões de vídeo, as implementações Multitenant com VMs na nuvem não são a melhor opção. Isso nos leva à próxima opção de implementação de nuvem, que é a de locatário único (sole tenant). Instâncias ou hosts dedicados. Nessa implementação, podemos pedir ao provedor de nuvem que execute nossas VMs em servidores dedicados à conta que pertence à nossa organização. Isso significa que os únicos locatários que terão no mesmo host são instâncias do nosso microsserviço. Outros microsserviços ou bancos de dados pertencentes somente à nossa organização. Portanto, se estivermos em um setor que não nos permite compartilhar a infraestrutura com outras empresas, essa é uma alternativa excelente, mas obviamente um pouco mais cara. O motivo óbvio pelo qual os fornecedores de nuvem cobram mais caro por essas implementações é que eles não podem alocar seu hardware de forma tão eficiente quanto as implementações Multitenant. Além disso, alguns provedores de nuvem permitem até mesmo alugar ou reservar um host inteiro somente para a nossa organização.  Isso nos dá acesso direto aos recursos de hardware do host, o que pode eliminar completamente o efeito de vizinho barulhento e reduzir a sobrecarga da virtualização pelo hipervisor. Obviamente, a principal desvantagem desse tipo de ponto de implantação é que ele é muito, muito mais caro do que as VMs de nuvem Multitenant.



Portanto, para concluir, a implementação de VM Multitenant nos oferece o melhor preço, mas não a melhor segurança nem o melhor desempenho. Se precisarmos de mais segurança, podemos alugar instâncias dedicadas de um único locatário, que são um pouco mais caras, mas garantem que somente as VMs da nossa organização possam ser executadas no mesmo hardware físico. E se também precisarmos do melhor desempenho e quisermos eliminar a possibilidade de um vizinho barulhento, podemos alugar hosts dedicados, que também é a opção mais cara.



## Serviço de Nuvem de Máquina Virtual Multitenant



Instâncias do Amazon Elastic Compute Cloud (EC2) - Fornece capacidade de computação escalável sob demanda usando "servidores virtuais".
Oferece diferentes tipos de instâncias otimizadas para diferentes cargas de trabalho, como uso geral, memória, computação, armazenamento e muito mais.

GCP Compute Engine - Oferece máquinas virtuais seguras e personalizáveis ​​em execução na infraestrutura do Google.
Você pode escolher entre uma variedade de máquinas virtuais para diferentes arquiteturas (x86, ARM, etc.) e cargas de trabalho, como "Scale Out", uso geral, memória ultra-alta, uso intensivo de computação, máquinas otimizadas para aceleradores e muito mais.

Microsoft Azure Virtual Machines - Permite criar máquinas virtuais (VMs) Linux e Windows em segundos. Inclui várias séries de máquinas virtuais para teste/desenvolvimento, VMs econômicas expansíveis, computação de uso geral, otimizadas para aplicativos na memória, máquinas virtuais otimizadas para computação, máquinas virtuais otimizadas para memória e armazenamento, máquinas virtuais de computação de alto desempenho, máquinas virtuais otimizadas para armazenamento, máquinas virtuais habilitadas para GPU e muito mais.

Hosts dedicados e serviços de nuvem de máquina virtual de locatário único (sole tenant)



Instâncias EC2 dedicadas da AWS - Instâncias EC2 dedicadas são instâncias EC2 regulares executadas em hardware dedicado a um único cliente com uma conta AWS.
Instâncias EC2 dedicadas que pertencem a diferentes contas da AWS são fisicamente isoladas em nível de hardware.
No entanto, as Instâncias Dedicadas do EC2 podem compartilhar hardware com outras instâncias da mesma conta da AWS que não são Instâncias Dedicadas.

Hosts Dedicados Amazon EC2 - Um Host Dedicado Amazon EC2 é um servidor físico totalmente dedicado para seu uso, para que você possa ajudar a atender aos requisitos de conformidade corporativa. Você pode encontrar os preços dos Hosts Dedicados aqui .

Nó de locatário único (sole tenant) do GCP : um nó de locatário único (sole tenant) oferece acesso exclusivo a um servidor físico do Compute Engine dedicado a hospedar apenas as VMs do seu projeto.
Dentro de um nó de locatário único (sole tenant), você pode provisionar várias VMs em tipos de máquina. Como alternativa, você pode atender aos requisitos de segurança ou conformidade com cargas de trabalho que exigem isolamento físico de outras cargas de trabalho ou VMs, não compartilhando o nó com nenhum outro projeto.

Hosts Dedicados do Microsoft Azure - O Host Dedicado do Azure oferece servidores físicos projetados para hospedar uma ou mais máquinas virtuais do Azure. Esses servidores são dedicados exclusivamente à sua organização e suas cargas de trabalho, garantindo que a capacidade não seja compartilhada com nenhum outro cliente.
Esse nível de isolamento no nível do host serve para atender aos requisitos de conformidade de forma eficaz.



## Resumo:



## Máquinas Virtuais na Nuvem

Uma das formas mais comuns de implantar microsserviços na nuvem é por meio de máquinas virtuais (VMs). Uma VM é um ambiente isolado que opera sobre hardware físico real, funcionando como um computador virtual com sistema operacional e recursos alocados (CPU, memória, rede e armazenamento). Essa alocação é gerenciada por um hipervisor, que divide os recursos do hardware físico entre várias VMs.

As VMs permitem executar instâncias de diferentes microsserviços ou múltiplas instâncias de um mesmo serviço. Esse modelo utiliza o conceito de multitenancy, onde uma única infraestrutura física é compartilhada por diversos usuários ou aplicações, mas com isolamento lógico entre eles.



## Vantagens das VMs Multitenant na Nuvem

Custo-benefício: O modelo de cobrança geralmente segue o formato pay-as-you-go, onde se paga apenas pelos recursos utilizados.

Flexibilidade: É possível ajustar os recursos alocados a cada VM conforme a necessidade.

Eficiência: O compartilhamento de hardware reduz custos operacionais para os provedores e clientes.



## Desvantagens das VMs Multitenant

Riscos de Segurança: Apesar do isolamento fornecido pelo hipervisor, vulnerabilidades no software ou configurações incorretas podem permitir ataques, como violações de dados entre tenants.

Desempenho Variável: O problema de "vizinho barulhento" (noisy neighbor) pode ocorrer quando o uso intensivo de recursos por uma VM afeta o desempenho de outras no mesmo host.

Esses fatores tornam as VMs Multitenant uma escolha economicamente vantajosa para muitos casos, mas podem ser inadequadas para setores sensíveis, como financeiro, saúde e governamental.



## Instâncias ou Hosts Dedicados

Para cenários que exigem maior segurança e desempenho, os provedores de nuvem oferecem opções de locatário único (single tenant).



## Instâncias Dedicadas

As instâncias dedicadas garantem que apenas as VMs da mesma organização compartilhem o hardware físico, reduzindo riscos de segurança e impactos de vizinhos barulhentos. Este modelo é mais caro do que o Multitenant devido à alocação menos eficiente do hardware pelo provedor.



## Hosts Dedicados

Uma alternativa ainda mais isolada é o aluguel de hosts dedicados inteiros, onde o cliente possui controle direto sobre todos os recursos físicos do servidor. Essa abordagem elimina completamente o problema do vizinho barulhento e reduz a sobrecarga do hipervisor, oferecendo o melhor desempenho. No entanto, é a opção mais cara disponível.



## Considerações Finais

A escolha entre VMs Multitenant, instâncias dedicadas e hosts dedicados depende de requisitos específicos de custo, segurança e desempenho:

VMs Multitenant: Melhor custo-benefício, mas com limitações em segurança e desempenho.

Instâncias Dedicadas: Balanceiam segurança e custo, adequadas para setores com requisitos moderados de conformidade.

Hosts Dedicados: Oferecem isolamento total e desempenho máximo, sendo ideais para aplicações sensíveis, mas com alto custo associado.

Essa flexibilidade permite ajustar a infraestrutura à medida das necessidades, maximizando a eficiência da execução de microsserviços em ambientes de produção.







Implantação sem servidor para microsserviços usando função como serviço (function as a service - FaaS)



No capítulo anterior, abordamos algumas opções de infraestrutura para implantação e execução de microsserviços. Neste capítulo, continuaremos essa discussão e falaremos sobre outro tipo de implantação que é mais orientada por eventos do que as mencionadas na palestra anterior. Essa implementação é chamada de função como serviço (function as a service - FaaS). Primeiro, discutiremos o problema que esse tipo de implantação resolve para nós. E, por fim, concluiremos discutindo suas vantagens e desvantagens para que possamos usá-lo corretamente na produção.



Para ilustrar o problema que estamos tentando resolver, vamos analisar dois cenários da vida real. Vamos considerar um caso de uso em que estamos administrando uma empresa no setor de entretenimento, com foco principal em streaming de vídeo sob demanda, em que os usuários podem alugar ou comprar filmes e programas. No entanto, como uma oferta adicional, também fazemos parcerias com diferentes locais de apresentação para ajudá-los a vender ingressos para seus eventos ao vivo. Portanto, temos um microsserviço dedicado para essa finalidade, que lida com solicitações de reserva de ingressos somente para eventos ao vivo. No entanto, esses eventos ao vivo acontecem apenas ocasionalmente, no máximo uma vez por mês. E quando abrimos a reserva, a maioria das solicitações chega dentro de 30 minutos a uma hora. Durante esse período, vendemos 99% de nossos ingressos e ficamos com apenas alguns ingressos baratos que não são tão bons e alguns ingressos muito bons, mas que são muito caros. Os ingressos restantes podem ser vendidos em algum momento entre o lançamento inicial e a data do evento, mas o tráfego não será muito significativo.



Agora, se observarmos o padrão de tráfego para esse microsserviço, veremos que ele não está recebendo nenhum tráfego na maior parte do tempo. No entanto, se o implementarmos em uma VM na nuvem ou até mesmo em um host dedicado, estaremos pagando pelo aluguel desse hardware durante todo esse tempo de inatividade. Ao mesmo tempo, quando abrimos a reserva de ingressos para o novo evento ao vivo, temos um pico de tráfego muito alto. Portanto, também precisamos configurar e pagar por um balanceador de carga e manter políticas de dimensionamento automático para esse microsserviço, o que aumenta ainda mais os custos de infraestrutura para a execução do serviço.



Agora vamos considerar outro cenário. Digamos que somos uma empresa de publicidade digital. Um de nossos microsserviços permite que nossos clientes executem um relatório mensal ou trimestral que fornece insights sobre o alcance e o retorno sobre o investimento de sua publicidade. Esse relatório pode ser acionado diretamente por um administrador que trabalha para a empresa de publicidade ou por um cron job executado uma vez por mês ou uma vez por trimestre e que aciona o relatório para eles automaticamente. Mesmo com 1.000 clientes, receberemos apenas cerca de 1.000 solicitações ou eventos desse tipo por mês ou trimestre. Portanto, executar esse microsserviço todo esse tempo apenas para os eventos que ocorrem tão raramente não é muito econômico.



Mas, além dos custos de infraestrutura para executar esse microsserviço, há também um grande custo de desenvolvimento para mantê-lo. Se formos uma equipe proprietária de um microsserviço desse tipo, além da lógica de negócios, também precisaremos manter uma grande quantidade de código padrão que lida com solicitações Http ou eventos de outra fonte que aciona essa lógica. E também precisamos manter scripts para criar pacotes e implementar nosso binário de microsserviço com todas as suas dependências em um servidor de nuvem. Portanto, temos que investir todo esse esforço apenas para lidar com um tráfego muito pequeno ou com eventos que ocorrem muito raramente. Portanto, é aqui que entra a oferta sem servidor chamada função como serviço (function as a service - FaaS). A função como serviço (function as a service - FaaS) é uma oferta de nuvem que nos permite arquitetar nosso sistema em um modelo totalmente orientado por eventos, não apenas da perspectiva do software, mas também da perspectiva da infraestrutura. Como parte dessa oferta, precisamos fornecer ao fornecedor de nuvem apenas duas coisas: o tipo de solicitações ou eventos que queremos tratar e a lógica que queremos executar quando esse evento for acionado. É isso aí, somente quando esse evento for acionado, o provedor de nuvem receberá nosso código. Empacote-o, implemente-o em um hardware físico e execute-o.



Em resposta a essa solicitação ou evento. Além disso, se o nosso tráfego tiver um padrão sazonal, no qual podemos receber muitas solicitações em um período muito curto, nesse caso, o provedor de nuvem também cuidará da escalabilidade horizontal para permitir que lidemos com esse pico de tráfego sem a necessidade de manter políticas de escalonamento automático ou configurar um balanceador de carga. Agora, o modelo de preços para essa oferta baseia-se no número de solicitações que nosso microsserviço recebe, bem como no tempo e na memória necessários para tratar cada solicitação executando nossa lógica. No entanto, enquanto essa solicitação ou evento não ocorrer, não pagaremos nada. Portanto, o benefício claro dessa oferta para microsserviços que lidam com eventos que ocorrem muito raramente é que podemos economizar muito dinheiro em infraestrutura para cargas de trabalho sazonais com picos de tráfego raros, mas muito altos.



O provedor de nuvem também cuida de toda a sobrecarga operacional do dimensionamento desse serviço. E o último benefício para esses dois tipos de cargas de trabalho é que isso nos permite economizar muitos custos e despesas gerais de desenvolvimento, pois o provedor de nuvem se encarrega de criar, empacotar e implantar nosso microsserviço para nós. É claro que, assim como tudo na engenharia de software e, principalmente, na arquitetura de software, sempre há uma compensação. Portanto, a principal desvantagem da implementação sem servidor é que, se nosso padrão de tráfego mudar, os custos de infraestrutura poderão aumentar significativamente. Por exemplo, se começarmos com um microsserviço que lida com tráfego muito sazonal ou baixo, mas, com o tempo, começarmos a receber cada vez mais solicitações, nosso código será executado com cada vez mais frequência. Além disso, à medida que nossa lógica de negócios se torna mais complexa a cada vez que recebemos uma solicitação ou tratamento de evento, ela exigirá muito mais tempo e memória. Portanto, como resultado, será mais caro para nós usar essa oferta do que implantá-la em uma VM na nuvem ou até mesmo em um host dedicado.



A segunda desvantagem é que o desempenho de uma implantação sem servidor é muito menos previsível do que implantar nossa lógica de negócios como parte de um microsserviço que controlamos totalmente. Portanto, as implementações sem servidor, como a função como serviço (function as a service - FaaS), não são a melhor opção para cargas de trabalho sensíveis à latência. E, por fim, esse também é o tipo de implementação menos seguro, porque não apenas nosso código é executado em um ambiente multilocatário, mas também expomos completamente nosso código-fonte ao provedor de nuvem.



Agora vamos comparar esse tipo de implantação com o que já aprendemos até agora. Se usarmos a função como um serviço para as cargas de trabalho corretas. Essa pode ser a maneira mais econômica de implementar nossos microsserviços. Mas se for usado incorretamente ou não para a carga de trabalho correta, também pode ser a opção mais cara. E quando se trata de segurança e desempenho, essa também é a opção menos ideal de todos os tipos de implementação.





Implantação sem servidor para microsserviços usando função como serviço - Soluções

## Serviços Web da Amazon (AWS)

AWS Lambda - Um serviço de computação sem servidor e orientado a eventos que permite executar código para praticamente qualquer tipo de aplicativo ou serviço de back-end sem a necessidade de configurar ou supervisionar servidores.
Você pode envolver a execução do seu código dentro de um Lambda por meio de mais de 200 serviços da AWS e vários aplicativos de software como serviço (SaaS).
Você é cobrado somente pelos recursos que consome.



## Plataforma de nuvem do Google (GCP)

Cloud Functions - Permite executar seu código na nuvem sem a necessidade de lidar com servidores ou contêineres. Ao utilizar a oferta escalável de Functions as a Service (FaaS) do GCP, você paga apenas pelo que usa, seguindo um modelo de pagamento conforme o uso.



## Microsoft Azure

Azure Functions - Um serviço de nuvem sob demanda que fornece a infraestrutura e os recursos mais recentes necessários para operar seus aplicativos. Permite que você se concentre totalmente no código enquanto o Azure Functions gerencia os aspectos restantes.





## Resumo:



## Cenários Reais: Identificando os Problemas

Empresa de Streaming e Eventos:
Imagine uma plataforma de streaming que também vende ingressos para eventos ao vivo. A reserva de ingressos ocorre raramente, com picos intensos de tráfego concentrados em poucas horas após a abertura de vendas. Fora desses períodos, o microsserviço responsável permanece inativo, mas ainda gera custos de infraestrutura quando hospedado em VMs ou hosts dedicados. Além disso, lidar com balanceadores de carga e escalonamento automático para atender a picos demanda esforço adicional e aumenta os custos.

Empresa de Publicidade:
Um microsserviço gera relatórios mensais ou trimestrais sob demanda ou via jobs agendados. Com poucos eventos por mês, mantê-lo ativo continuamente é ineficiente em termos de custos e desenvolvimento, já que exige scripts de empacotamento, implantação e manutenção de código de infraestrutura além da lógica de negócios.



## O Papel do FaaS

Função como Serviço (FaaS) é uma oferta de nuvem que permite arquitetar sistemas totalmente orientados por eventos, tanto em software quanto em infraestrutura. Basta fornecer dois elementos ao provedor de nuvem:

O evento ou solicitação a ser tratado.

A lógica a ser executada em resposta.

## Quando o evento ocorre, o provedor:

Recebe o código.

Empacota, implanta e executa-o em hardware físico.

Garante escalabilidade automática para lidar com picos de tráfego.

Modelo de Cobrança:
O custo é baseado no número de solicitações, no tempo de execução e nos recursos (CPU/memória) consumidos. Sem eventos, não há cobrança, tornando o FaaS ideal para cargas de trabalho sazonais ou de tráfego intermitente.



## Vantagens do FaaS

## Redução de Custos de Infraestrutura:

Paga-se apenas pelo uso real do serviço.

Ideal para cargas sazonais com picos intensos e períodos de inatividade.

## Escalabilidade Automática:

O provedor de nuvem gerencia o escalonamento horizontal durante picos de tráfego sem necessidade de balanceadores de carga ou políticas adicionais.

## Redução de Sobrecarga de Desenvolvimento:

O provedor gerencia empacotamento, implantação e manutenção da infraestrutura, permitindo que as equipes foquem na lógica de negócios.



## Desvantagens do FaaS

## Custos Crescentes com Mudança no Padrão de Tráfego:

Se o tráfego deixar de ser sazonal e aumentar significativamente, ou se a lógica se tornar mais complexa, os custos podem superar os de VMs ou hosts dedicados.

## Desempenho Menos Previsível:

O tempo de resposta pode variar, especialmente devido ao "cold start" (inicialização de instâncias). Isso torna o FaaS menos adequado para cargas sensíveis à latência.

## Riscos de Segurança:

O código é executado em um ambiente multilocatário. Além disso, é necessário expor o código-fonte ao provedor de nuvem, o que pode ser um ponto crítico para algumas organizações.



## Considerações Finais

O FaaS é uma solução eficiente para microsserviços que lidam com eventos raros ou tráfego sazonal, oferecendo redução significativa de custos e simplicidade operacional. No entanto, ele apresenta limitações em termos de segurança, desempenho e previsibilidade de custos para padrões de tráfego intensos ou complexos.

Utilizado corretamente, o FaaS pode ser a abordagem mais econômica para microsserviços baseados em eventos. Por outro lado, sua aplicação inadequada pode torná-lo a opção mais cara e menos eficiente.



## Contêineres para microsserviços em desenvolvimento, testes e produção



Neste capítulo, falaremos sobre contêineres para desenvolvimento, teste e implantação de microsserviços na produção. Esse tipo de implantação é uma das formas mais populares e mais populares de empacotar e fornecer microsserviços para produção. E veremos o motivo em breve. Mas, primeiro, vamos ter uma visão geral rápida do problema que estamos tentando resolver usando contêineres. Em seguida, falaremos sobre os benefícios dos contêineres para microsserviços em relação à implantação em máquinas virtuais. E, por fim, falaremos sobre os desafios de executar microsserviços na produção usando contêineres.



Portanto, vamos começar descrevendo o problema que estamos tentando resolver, começando pelo ambiente de desenvolvimento. Um problema comum que as empresas têm é a falta de paridade entre o ambiente de desenvolvimento e o ambiente de produção. Por exemplo, imagine que você é um desenvolvedor em uma equipe que possui um microsserviço. Você configura todo o ambiente de desenvolvimento para esse microsserviço localmente com uma versão de banco de dados autônomo local. Você também instalou todas as dependências desse microsserviço específico para o seu sistema operacional. No entanto, o banco de dados distribuído de produção é configurado de forma diferente do banco de dados autônomo local na memória, e o sistema operacional em produção também não é o mesmo do nosso laptop de desenvolvimento. Portanto, todos os locais dos arquivos de configuração e as versões das dependências são totalmente diferentes. Assim, quando terminamos de desenvolver nosso recurso em nossa máquina e o testamos localmente, tudo funcionou bem.



Mas quando o implementamos na produção. As coisas quebram ou não funcionam como esperado. Uma solução é desenvolver e testar nosso microsserviço em uma máquina virtual semelhante à de produção em nosso computador de desenvolvimento, o que resolve o problema de paridade entre o desenvolvimento e a produção, mas introduz um novo problema. Nosso sistema operacional host precisa executar outra camada de software chamada de hipervisor. O hipervisor é executado como qualquer outro programa em nosso sistema operacional host, mas executa internamente outro sistema operacional inteiro com seu próprio kernel. Esse kernel gerencia todos os processos de aplicativos do sistema operacional convidado, o sistema de arquivos, a segurança, a rede, a memória e muitos outros componentes. E também usa drivers de dispositivo para interagir com o hardware virtual que é emulado pelo hipervisor.



Portanto, como podemos ver, temos muita sobrecarga desnecessária apenas para executar uma única instância de microsserviço. Agora, se quisermos executar e testar a integração de alguns microsserviços, precisaremos executar várias máquinas virtuais, cada uma com sua própria cópia de um sistema operacional e seu próprio kernel. Isso cria tanta sobrecarga que tudo será extremamente lento e ineficiente, o que dificulta muito o desenvolvimento e os testes. Portanto, os contêineres resolvem esse problema isolando apenas o que queremos isolar e compartilhando todo o resto. Quando empacotamos nossos microsserviços em contêineres, cada imagem de contêiner inclui nosso binário de microsserviço, o comando para executá-lo e todas as dependências necessárias, em total isolamento de qualquer outro microsserviço. Quando executamos uma ou várias instâncias dessa imagem, cada contêiner tem seu próprio sistema de arquivos isolado, interface de rede e tempo de execução. No entanto, os drivers do kernel do sistema operacional e tudo o mais que não precisamos isolar são compartilhados entre todos os contêineres. Portanto, a sobrecarga de executar algumas dezenas de contêineres em nossa máquina é mínima, o que a torna perfeita para desenvolver e testar microsserviços.



Agora, os benefícios dos contêineres não terminam no estágio de desenvolvimento e teste local. Podemos executar esses contêineres em nosso pipeline de integração contínua, que pode executar um sistema operacional completamente diferente e usar um hardware completamente diferente dos nossos computadores de desenvolvimento. Mas tudo isso não importa porque as imagens de contêineres são completamente desacopladas. Do sistema operacional e do hardware, para que possamos criá-los uma vez e executá-los em qualquer hardware e sistema operacional que ofereça suporte a contêineres e tempo de execução de contêineres.



Agora, como nesta seção estamos nos concentrando na implantação de microsserviços na produção, podemos ir ainda mais longe. Quando analisamos nossa abordagem anterior usando VMs de nuvem, cada instância de microsserviço foi implantada em sua própria VM e programada pelo fornecedor da nuvem para ser executada em um de seus servidores. Essa abordagem teve muitas vantagens que já mencionamos nas palestras anteriores. No entanto, ele também tem algumas grandes desvantagens que são muito semelhantes às que já discutimos no contexto de um ambiente de desenvolvimento. Se duas instâncias de microsserviço forem executadas no mesmo servidor de nuvem, por exemplo, cada VM executará uma instância totalmente separada do mesmo sistema operacional. Essa duplicação significa que perdemos recursos valiosos de memória, CPU e armazenamento para o sistema operacional e também para a implementação e a inicialização. Cada VM pode levar minutos até que estejamos prontos para aceitar o tráfego. Mas, além disso, temos outro problema, que é o bloqueio do fornecedor de nuvem e a falta de portabilidade. O problema é que, quando criamos uma imagem de VM para um microsserviço, o formato dessa imagem pode ser específico do fornecedor da nuvem e a configuração que descreve o tipo de VM que queremos alugar também é específica do fornecedor da nuvem. Portanto, se recebermos uma oferta atraente de outro fornecedor de nuvem e quisermos migrar completamente, teremos que trabalhar muito para criar essas novas imagens e um problema ainda maior é quando temos um ambiente de várias nuvens, quando executamos alguns serviços em um provedor de nuvem e outra parte em outro provedor de nuvem, ou em um ambiente de nuvem híbrida, em que uma parte pode ser executada em um fornecedor de nuvem pública e outra em nosso ambiente de nuvem privada para fins de maior segurança ou desempenho.



Para essas situações, será um pesadelo gerenciar VMs na nuvem em diferentes ambientes. Portanto, tudo isso também pode ser resolvido com o uso de contêineres. Mais uma vez, tudo o que precisamos fazer é criar essas imagens de contêiner uma vez e depois implantá-las em VMs de nuvem genéricas ou até mesmo diretamente em hosts dedicados. Em qualquer ambiente, o único requisito é instalar o tempo de execução do contêiner, que é o software que executa esses contêineres, e estamos prontos para começar. Portanto, para resumir os benefícios de executar microsserviços dentro de contêineres na produção, temos melhor portabilidade entre ambientes, porque podemos criar uma imagem de microsserviço uma vez e usá-la no desenvolvimento, na preparação de controle de qualidade e na produção em qualquer hardware ou sistema operacional do provedor de nuvem. Também temos um tempo de inicialização mais rápido porque os contêineres geralmente levam apenas alguns milissegundos para serem implantados e executados. E também podemos economizar muito dinheiro em infraestrutura porque a utilização do hardware é muito melhor quando usamos contêineres.



Portanto, em vez de alugar várias VMs menores, nas quais perdemos parte da CPU e da memória para o sistema operacional, podemos alugar VMs maiores ou até mesmo hosts dedicados. Quando implantamos os contêineres de diferentes microsserviços em uma única VM ou host, podemos utilizar melhor o hardware porque eles compartilham o mesmo kernel do sistema operacional. E, em muitos casos, isso significa que podemos executar mais instâncias de microsserviço com a mesma quantidade de hardware do que quando usamos VMs de nuvem. No entanto, ao contrário do ambiente de desenvolvimento e da integração contínua, agora temos outro problema a resolver antes de podermos aproveitar ao máximo os contêineres na produção. O problema agora é que temos duas camadas de abstrações que precisam ser coladas. Por um lado, temos a abstração da infraestrutura de nuvem, que inclui a nuvem, as VMs ou os hosts, que precisamos alugar e dimensionar automaticamente com base no tráfego ou na carga do nosso sistema. E também temos outros serviços gerenciados em nuvem, como Bancos de dados, message brokers, registro distribuído e assim por diante.



Por outro lado, temos a obstrução dos contêineres, em que temos dezenas de imagens de contêineres que representam diferentes microsserviços. Cada imagem de microsserviço precisa ser implementada como um grupo de instâncias de contêineres nessa infraestrutura. Em seguida, precisamos de uma maneira de descobrir e conectar todos esses contêineres de microsserviços entre si e aos serviços gerenciados por meio da rede. Também precisamos gerenciar a escalabilidade e a disponibilidade de cada grupo de contêineres para que possamos adicionar mais instâncias se o tráfego aumentar e remover instâncias quando o tráfego diminuir. Além disso, precisamos substituir automaticamente os contêineres que falharem e uma maneira de atualizar todos os contêineres do mesmo microsserviço. Quando uma nova versão de um microsserviço é lançada. Fazer tudo isso manualmente para centenas ou até milhares de instâncias de contêineres potencialmente em execução em diferentes regiões de nuvem ou até mesmo em diferentes provedores de nuvem é uma tarefa impossível. Portanto, no próximo capítulo, aprenderemos sobre a solução para esse problema, que é a introdução de outra camada chamada orquestração de contêineres (container orchestration).



## Resumo:

## O Problema: Paridade de Ambientes

Um dos maiores desafios no desenvolvimento de microsserviços é garantir consistência entre os ambientes de desenvolvimento, teste e produção. Imagine que você está desenvolvendo um microsserviço em sua máquina local, configurando um banco de dados autônomo local e instalando dependências específicas. No entanto, a produção utiliza um banco de dados distribuído com configurações diferentes e um sistema operacional distinto. Isso frequentemente resulta em falhas quando o código funciona localmente, mas quebra ao ser implantado em produção.

Usar máquinas virtuais pode resolver a falta de paridade, criando um ambiente similar ao de produção. Contudo, essa abordagem introduz uma sobrecarga significativa: cada VM executa um sistema operacional completo, consumindo recursos desnecessários de memória, CPU e armazenamento. Esse custo se agrava ao executar múltiplas VMs, tornando o desenvolvimento e os testes lentos e ineficientes.



## A Solução: Contêineres

Os contêineres solucionam esse problema ao isolar apenas o necessário. Eles encapsulam o binário do microsserviço, suas dependências e configurações em uma única imagem. Ao contrário das VMs, os contêineres compartilham o kernel do sistema operacional host, reduzindo a sobrecarga. Isso permite executar múltiplos contêineres com impacto mínimo no desempenho, ideal para desenvolvimento e testes locais.

Além disso, os contêineres garantem portabilidade. Uma imagem criada no ambiente de desenvolvimento pode ser executada em qualquer sistema operacional ou hardware compatível com o runtime de contêineres, como Docker. Isso elimina problemas de compatibilidade ao mover aplicações entre ambientes, incluindo pipelines de integração contínua, ambientes de controle de qualidade e produção.



## Benefícios em Produção

## Em produção, os contêineres oferecem várias vantagens:

Portabilidade: Imagens de contêiner são independentes do fornecedor de nuvem ou ambiente de execução, garantindo flexibilidade para ambientes híbridos ou multi-nuvem.

Tempo de Inicialização Rápido: Contêineres levam milissegundos para iniciar, enquanto VMs podem levar minutos.

Melhor Utilização de Hardware: Contêineres compartilham o mesmo kernel, permitindo executar mais instâncias de microsserviços em menos recursos, reduzindo custos de infraestrutura.

Por exemplo, em vez de alugar múltiplas VMs pequenas, é possível utilizar uma única VM maior ou um host dedicado, alocando contêineres de diferentes microsserviços para maximizar o uso de recursos.



## Desafios na Produção

## Apesar dos benefícios, a produção traz novos desafios:

Gerenciamento de Escalabilidade e Disponibilidade: É necessário ajustar o número de instâncias de contêineres com base no tráfego, substituir automaticamente contêineres com falhas e implementar novas versões sem interrupções.

Conexão e Descoberta de Serviços: Garantir que contêineres de microsserviços se conectem entre si e a serviços gerenciados (como bancos de dados ou filas de mensagens) de maneira eficiente e segura.

Operação em Ambientes Diversificados: Gerenciar contêineres em diferentes regiões de nuvem ou provedores de maneira coesa.

Realizar essas tarefas manualmente em escala seria inviável. Por isso, é necessária uma camada adicional de abstração para gerenciar contêineres em produção: a orquestração de contêineres.

No próximo capítulo, exploraremos como as ferramentas de orquestração de contêineres, como Kubernetes, resolvem esses desafios, permitindo gerenciar implantações complexas de forma eficiente.







## Orquestração de contêineres e Kubernetes para arquitetura de microsserviços



No capítulo anterior, aprenderemos os benefícios da implantação de microsserviços dentro de contêineres na produção. Alguns dos benefícios que mencionamos incluem paridade total entre testes de desenvolvimento e produção, portabilidade de ambiente entre diferentes ambientes de nuvem e melhor utilização de hardware, o que nos permitiu reiniciar os microsserviços mais rapidamente e reduzir os custos de infraestrutura. No entanto, encontramos um grande desafio na implantação, configuração e gerenciamento de milhares de contêineres, executando centenas de microsserviços, possivelmente até em diferentes provedores de nuvem. Portanto, nesta palestra, falaremos sobre a solução para esse problema, que é a orquestração de contêineres. Primeiro, falaremos sobre o que é orquestração de contêineres e, mais tarde, nos aprofundaremos em uma arquitetura bem representativa de um orquestrador de contêineres.



Então, em primeiro lugar, o que é um orquestrador de contêineres? Um orquestrador de contêineres é uma ferramenta que gerencia todo o ciclo de vida de todos os contêineres de microsserviços em nosso sistema. É como um sistema operacional. No entanto, para a arquitetura de microsserviços implantada como contêineres, as responsabilidades de um orquestrador de contêineres incluem a automação da implantação de novos microsserviços ou novas versões de microsserviços como contêineres, gerenciando a alocação de recursos entre os contêineres existentes para garantir que cada contêiner obtenha a quantidade certa de memória e armazenamento da CPU para funcionar corretamente. Monitoramento da integridade dos contêineres com autocorreção, o que permite a implantação automática de novos contêineres para manter um número saudável de instâncias de cada microsserviço. Em seguida, temos o empacotamento automático de contêineres, o que significa programar os contêineres de forma eficiente para proporcionar a utilização ideal do hardware existente. Em seguida, temos o balanceamento de carga entre os contêineres do mesmo microsserviço, dimensionando os serviços para fora ou para dentro, adicionando ou removendo contêineres com base no tráfego e na utilização de recursos. E, por fim, gerenciar a descoberta e a conectividade de rede entre serviços, contêineres e o mundo externo.



Agora, para ilustrar como funciona uma ferramenta de orquestração de contêineres, usarei a arquitetura do Kubernetes, que é uma das ferramentas de orquestração de contêineres mais populares do setor, mas não a única. No entanto, como este não é um curso intensivo de DevOps sobre Kubernetes ou qualquer outra tecnologia específica, vou poupá-lo de todos os detalhes complexos e desnecessários para que não percamos a visão geral.



Um cluster típico de orquestração de contêineres terá um plano de controle implantado em pelo menos uma máquina. Chamaremos essa máquina de nó controlador. As VMs ou servidores restantes que executam nossos contêineres de microsserviço são chamados de nós de trabalho. O nó controlador executa todos os processos que orquestram e gerenciam nosso cluster. Por exemplo, teremos um processo de API que recebe comandos nossos para adicionar um novo microsserviço, atualizar uma versão ou configuração de microsserviço existente e assim por diante. Todas as informações sobre a configuração do cluster e o estado atual são armazenadas por outro processo, que é um banco de dados de armazenamento de valores-chave. Agora, se precisarmos adicionar outro contêiner de um microsserviço específico, teremos outro processo que monitora os recursos do nó de trabalho e decide onde agendar esse novo contêiner. Em seguida, temos outro processo que monitora a integridade de nossos nós de trabalho ou as alterações de estado nesses nós. Por exemplo, se um dos nós ficar indisponível, ele detectará isso e garantirá que o processo do agendador reprogramará esses contêineres de microsserviço para os outros nós de trabalho. Outro processo que temos gerencia toda a lógica específica do provedor de nuvem, como a exclusão de nós de trabalho que não respondem pelo provedor de nuvem, a adição de nuvem, o gerenciamento de balanceadores de carga, o roteamento para nossos contêineres e assim por diante. Agora, além dos processos em execução no plano de controle, cada nó de trabalho também executa um conjunto de agentes para gerenciar os contêineres em execução. Apenas nesse sentido. Isso inclui o tempo de execução do contêiner, que é o mecanismo de software que executa os contêineres em cada host. Em seguida, temos o agente que monitora e realmente inicia os contêineres de microsserviço quando recebe o comando apropriado do plano de controle. E também temos outro processo que atua como proxy. Esse proxy mantém um conjunto de regras de rede para rotear solicitações de rede entre contêineres de diferentes microsserviços e equilibra a carga nos contêineres do mesmo microsserviço. Além disso, às vezes precisamos executar cada instância do nosso microsserviço com um processo sidecar. Esse processo secundário pode ser um agente de registro ou monitoramento ou um cache na memória. No entanto, normalmente, colocar mais de um processo em um único contêiner não é uma boa prática.



Portanto, o Kubernetes nos permite agrupar vários contêineres em outra unidade lógica, que é chamada de pod. Portanto, esse pod é a menor unidade de tempo de execução que o Kubernetes gerenciará para nós, mesmo que esse pod contenha apenas um único contêiner de microsserviço.



Por fim, a descrição de toda a arquitetura dos microsserviços, sua configuração com imagens de contêineres que eles usam e a quantidade de memória e armazenamento da CPU de que precisam é descrita de forma declarativa e legível. Essa configuração também contém todas as informações sobre os serviços aos quais os nossos microsserviços se conectam fora do cluster de contêineres. Isso inclui funções de nuvem, bancos de dados, armazenamentos de objetos, message brokers e assim por diante. Essa configuração é armazenada, mantida e atualizada em um sistema de controle de versão, como qualquer outro código. Quando uma alteração for feita nessa configuração, ela será enviada ao servidor da API do Control Planes, que aciona as atualizações relevantes no cluster.



Agora, em uma arquitetura típica de microsserviços, teremos centenas desses nós de trabalho executando milhares de contêineres pertencentes a diferentes microsserviços. Portanto, para aumentar a disponibilidade e acompanhar tudo o que acontece no cluster, normalmente também temos várias réplicas dos nós controladores dentro do plano de controle. E, para aumentar ainda mais a disponibilidade, podemos ter vários clusters com configurações iguais ou diferentes em execução em diferentes regiões de nuvem ou até mesmo em provedores de nuvem, e podemos rotear o tráfego para cada região usando um balanceador de carga global. Esse roteamento pode ser baseado em critérios como a proximidade física do usuário, a carga ou a integridade de cada cluster e assim por diante.



Como podemos ver, essa arquitetura de orquestração de contêineres pode ser bastante complexa de configurar e gerenciar. Isso requer o conhecimento dos engenheiros de DevOps ou de confiabilidade do site e também requer recursos dedicados apenas para fins de orquestração, como essas instâncias de controlador. No entanto, como já aprendemos no início do curso, todo esse investimento compensa porque seu custo é amortizado em todas as equipes e microsserviços que gerenciamos. Portanto, se nossa decisão de migrar para microsserviços foi correta, os benefícios de executar microsserviços como contêineres gerenciados pelo orquestrador de contêineres superarão o custo e a complexidade.







## Resumo:

## O que é Orquestração de Contêineres?

A orquestração de contêineres é o processo automatizado de gerenciar todo o ciclo de vida dos contêineres em um sistema de microsserviços. Assim como um sistema operacional gerencia processos em um único computador, um orquestrador gerencia contêineres em um ambiente distribuído. Suas principais responsabilidades incluem:

Automação de implantações: Implantar novos microsserviços ou atualizar versões existentes de forma consistente.

Alocação de recursos: Garantir que cada contêiner tenha acesso adequado a memória, CPU e armazenamento.

Monitoramento e autocorreção: Detectar falhas e substituir automaticamente contêineres problemáticos.

Empacotamento eficiente: Maximizar a utilização de hardware alocando contêineres de forma otimizada.

Balanceamento de carga: Distribuir tráfego entre instâncias de contêineres para evitar sobrecarga.

Descoberta de serviços e conectividade: Gerenciar a comunicação entre contêineres e serviços externos.



## Arquitetura do Kubernetes

Para exemplificar, analisaremos a arquitetura do Kubernetes. Embora existam outras ferramentas de orquestração, o Kubernetes é amplamente adotado devido à sua flexibilidade e capacidade de gerenciar ambientes complexos. A seguir, apresentamos uma visão geral simplificada para manter o foco no funcionamento essencial.



## Estrutura do Cluster

## Um cluster Kubernetes é composto por:

Plano de Controle: Gerencia a lógica central do cluster. Ele é executado em um ou mais nós controladores e é responsável por:

API Server: Recebe comandos e coordena mudanças no cluster.

Etcd: Armazena de forma confiável o estado e a configuração do cluster.

Scheduler: Decide em quais nós de trabalho os novos contêineres devem ser executados.

Controller Manager: Garante que o estado atual do cluster corresponda à configuração desejada.

## Nós de Trabalho: Executam os contêineres de microsserviços. Cada nó contém:

Runtime de Contêiner: Software responsável por executar contêineres (ex.: Docker, containerd).

Kubelet: Gerencia contêineres no nó e comunica-se com o plano de controle.

Kube-proxy: Configura regras de rede para permitir comunicação entre contêineres e balancear a carga.



## Conceitos Fundamentais

No Kubernetes, os contêineres são agrupados em pods, que são a menor unidade gerenciável no sistema. Um pod pode conter um ou mais contêineres, geralmente utilizados para executar processos relacionados (ex.: um microsserviço e um agente de monitoramento).

Toda a configuração do cluster e dos serviços é feita de forma declarativa, utilizando arquivos YAML ou JSON. Esses arquivos especificam detalhes como imagens de contêineres, requisitos de recursos e dependências externas (ex.: bancos de dados ou filas de mensagens). Quando uma alteração é feita, ela é aplicada pelo plano de controle de forma incremental e automática.

## Alta Disponibilidade e Escalabilidade

## Para sistemas em larga escala, clusters Kubernetes podem incluir:

Nós controladores redundantes para evitar pontos únicos de falha.

Múltiplos clusters distribuídos em diferentes regiões ou provedores de nuvem, gerenciados por balanceadores de carga globais para roteamento inteligente de tráfego.

Essa abordagem garante resiliência e disponibilidade mesmo em cenários de falhas regionais ou de hardware.



## Benefícios e Complexidade

Embora a orquestração de contêineres introduza complexidade operacional, ela traz benefícios que justificam o investimento, especialmente em arquiteturas de microsserviços. O Kubernetes simplifica tarefas críticas, como escalabilidade, monitoramento e alta disponibilidade, amortizando custos ao longo de múltiplas equipes e serviços.

No próximo capítulo, exploraremos como otimizar o uso do Kubernetes em cenários avançados, incluindo estratégias para deployment contínuo e integração com ferramentas de observabilidade.































