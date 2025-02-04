# Guia de Uso dos Frameworks Wenger

Este documento tem como objetivo fornecer recomendações para arquitetos de solução sobre quando utilizar cada um dos frameworks Wenger na empresa, garantindo a melhor escolha conforme os requisitos do projeto.

## **1. Wenger Backend**
- **Baseado em**: Spring Boot
- **Descrição**: Framework indicado para o desenvolvimento de microsserviços e aplicações RESTful.
- **Cenários de Uso**:
  - Construção de APIs REST para exposição de funcionalidades da aplicação.
  - Implementação de lógica de negócio centralizada.
  - Aplicações que exigem escalabilidade e manutenção facilitada.
  - Integração com bancos de dados relacionais e NoSQL.
- **Não indicado para**:
  - Processamento assíncrono em larga escala.
  - Orquestração de processos complexos.

## **2. Wenger Integration**
- **Baseado em**: Spring Boot + Apache Camel
- **Descrição**: Framework especializado na integração de sistemas heterogêneos através de rotas e mensagens.
- **Cenários de Uso**:
  - Implementação de ETLs e transformação de dados entre diferentes sistemas.
  - Comunicação entre microsserviços utilizando mensageria (Kafka, RabbitMQ, etc.).
  - Integração entre sistemas legados e novas aplicações.
  - Conectividade com APIs de terceiros e serviços externos.
- **Não indicado para**:
  - Desenvolvimento de microsserviços autônomos.
  - Aplicações que necessitam apenas de persistência de dados e lógica de negócio.

## **3. Wenger Process**
- **Baseado em**: Spring Boot + Camunda
- **Descrição**: Framework voltado para orquestração e automação de processos de negócio utilizando BPMN.
- **Cenários de Uso**:
  - Implementação de workflows de negócio complexos.
  - Gerenciamento de estados e regras de processos de longa duração.
  - Necessidade de visibilidade e rastreabilidade das execuções de processos.
  - Automação de tarefas humanas e automatizadas dentro de um fluxo definido.
- **Não indicado para**:
  - Aplicações simples sem necessidade de controle de estados.
  - Serviços com lógica de negócio autônoma que não requerem orquestração de processos.

## **4. Wenger Batch**
- **Baseado em**: Spring Batch
- **Descrição**: Framework especializado em processamento de dados em lote.
- **Cenários de Uso**:
  - Execução de cargas de dados em batch (ETL, migração de dados, etc.).
  - Processamento de grandes volumes de dados com controle transacional.
  - Execução de tarefas agendadas com garantia de consistência.
  - Processos que exigem monitoramento e recuperação em caso de falha.
- **Não indicado para**:
  - Sistemas com interação em tempo real.
  - Processos que exigem resposta rápida e baixa latência.

## **5. Wenger Atomic**
- **Baseado em**: Quarkus
- **Descrição**: Framework otimizado para execução nativa e aplicações cloud-native de alto desempenho.
- **Cenários de Uso**:
  - Desenvolvimento de microsserviços leves e altamente performáticos.
  - Aplicações com necessidade de inicialização ultrarrápida e baixo consumo de memória.
  - Execução em ambientes serverless e containers com tempo de resposta reduzido.
  - Integração com Kubernetes e arquiteturas reativas.
- **Não indicado para**:
  - Aplicações que exigem um ecossistema Java tradicional e consolidado.
  - Projetos que dependem fortemente de bibliotecas específicas do Spring.

## **Conclusão**
A escolha do framework Wenger adequado depende dos requisitos específicos da solução. O seguinte resumo pode ser utilizado para auxiliar na decisão:

| Framework         | Melhor para...                                      | Evitar quando...                            |
|------------------|------------------------------------------------|---------------------------------|
| **Wenger Backend** | APIs REST, lógica de negócio | Necessário integração complexa ou orquestração |
| **Wenger Integration** | Integração entre sistemas | Aplicação exige apenas persistência e regras |
| **Wenger Process** | Orquestração de processos BPMN | Processos simples e sem necessidade de estados |
| **Wenger Batch** | Processamento em lote | Aplicações com necessidade de tempo real |
| **Wenger Atomic** | Microsserviços leves e performáticos, cloud-native | Projetos que exigem um ecossistema Spring tradicional |

Para garantir a melhor decisão, recomenda-se a consulta à equipe de arquitetura para avaliar cenários específicos e alinhamento com as necessidades do negócio.
