# Principais Conceitos de Arquitetura de Software para Construção de Repertório

## Objetivo

Para evoluir para **Software Architect**, arquitetura não deve ser tratada apenas como uma lista de frameworks, padrões ou tecnologias.

O principal objetivo é construir um **repertório de decisões arquiteturais**:

- reconhecer problemas arquiteturais;
- conhecer alternativas;
- compreender trade-offs;
- saber quando usar cada abordagem;
- saber quando **não** usar uma determinada solução;
- conseguir justificar decisões tecnicamente;
- conectar arquitetura, código, infraestrutura, dados, performance e operação.

---

# 1. Fundamentos de Arquitetura

É a base para conseguir discutir qualquer sistema.

## Conceitos

- Requisitos funcionais × não funcionais
- Quality Attributes:
  - Performance
  - Escalabilidade
  - Disponibilidade
  - Confiabilidade
  - Segurança
  - Manutenibilidade
  - Observabilidade
  - Testabilidade
  - Portabilidade
- Trade-offs arquiteturais
- Constraints
- Decisões arquiteturais
- Architecture Decision Records (ADR)
- SOLID
- Coesão × acoplamento
- Separation of Concerns
- Information Hiding
- Dependency Inversion
- Evolução arquitetural

## Perguntas que precisam fazer parte do repertório

> Se eu aumentar disponibilidade, o que estou sacrificando?

> Essa decisão reduz acoplamento ou apenas desloca o acoplamento?

> Esse componente realmente precisa ser distribuído?

---

# 2. Design de Sistemas

Aqui começa o repertório de **System Design**.

## Conceitos

- Monólito
- Monólito modular
- Modularização
- Microservices
- SOA
- Serverless
- Event-driven architecture
- APIs
- Comunicação síncrona × assíncrona
- Request/Response
- Publish/Subscribe
- Message Queue
- Event Streaming
- Batch
- CDC
- Webhooks

## Conceito fundamental

É importante saber não apenas **quando usar microservices**, mas principalmente:

> **Quando NÃO usar microservices.**

Esse é um conhecimento arquitetural importante porque arquitetura deve partir do problema e dos requisitos, não da tecnologia.

---

# 3. Arquitetura de Código

É onde arquitetura se conecta diretamente com desenvolvimento.

## Conceitos

- Layered Architecture
- Clean Architecture
- Hexagonal Architecture
- Onion Architecture
- Ports & Adapters
- Dependency Rule
- Domain-Driven Design (DDD)
- Bounded Context
- Aggregate
- Entity
- Value Object
- Domain Service
- Application Service
- Domain Events
- Anti-Corruption Layer

## Organização do código

- Package by Layer × Package by Feature
- Vertical Slice
- Modularização interna
- Arquitetura evolutiva

## Direção recomendada

Uma base especialmente importante:

> **Monólito modular + DDD + arquitetura hexagonal/clean**

Essa combinação cria uma base sólida antes de avançar para sistemas distribuídos.

---

# 4. Dados e Persistência

Um arquiteto precisa entender muito mais do que ORM/JPA.

## Bancos relacionais

- Modelagem relacional
- Normalização
- Índices
- Query Planning
- Joins
- Locks
- Isolation Levels
- Transactions
- ACID
- MVCC
- Deadlocks
- Replicação
- Sharding
- Partitioning

## NoSQL

- Key-Value
- Document
- Column Family
- Graph
- Consistência × disponibilidade
- CAP
- Eventual Consistency

## Estratégias

- Cache
- Redis
- Cache Aside
- Read Through
- Write Through
- CQRS
- Materialized View
- Database per Service
- Shared Database
- Outbox
- Inbox
- CDC

## Pergunta fundamental

> **Onde está a fonte da verdade e como os dados ficam consistentes?**

---

# 5. Sistemas Distribuídos

Um dos blocos mais importantes para arquitetura moderna.

## Conceitos

- CAP Theorem
- PACELC
- Consistência forte × eventual
- Idempotência
- Retry
- Timeout
- Backoff
- Circuit Breaker
- Bulkhead
- Rate Limiting
- Load Balancing
- Service Discovery
- Distributed Lock
- Leader Election
- Replicação
- Particionamento
- Ordenação de eventos
- At-least-once
- At-most-once
- Exactly-once
- Deduplicação
- Distributed Transactions
- Saga
- Two-Phase Commit
- Eventual Consistency

## Pergunta fundamental

> **O que acontece quando a rede falha?**

Um arquiteto precisa naturalmente considerar falhas de rede, indisponibilidade parcial, duplicidade, atrasos e inconsistência.

---

# 6. Mensageria e Eventos

Especialmente importante para arquiteturas distribuídas.

## Conceitos

- Queue
- Topic
- Consumer
- Producer
- Consumer Group
- Partition
- Offset
- Ordering
- Delivery Semantics
- Retry
- DLQ/DLT
- Poison Message
- Backpressure
- Event-Driven Architecture
- Event Sourcing
- Outbox Pattern
- Inbox Pattern
- Transactional Messaging

## Repertório essencial

Não basta saber que:

> RabbitMQ existe.

ou:

> Kafka existe.

É necessário entender:

> **Qual problema estou tentando resolver?**

E saber diferenciar:

> **RabbitMQ ≠ Kafka**

não apenas tecnicamente, mas principalmente arquiteturalmente.

---

# 7. Performance e Escalabilidade

Esse deve ser um dos pilares para quem pretende atuar com arquitetura focada em performance e escala.

## Performance

- Latência
- Throughput
- Concurrency
- Parallelism
- CPU-bound
- I/O-bound
- Memory-bound
- Garbage Collection
- JVM
- Threading
- Virtual Threads
- Connection Pool
- Database Bottleneck
- N+1
- Caching

## Escalabilidade

- Vertical Scaling
- Horizontal Scaling
- Stateless Application
- Load Balancing
- Sharding
- Replication
- Partitioning
- Autoscaling

## Conceitos matemáticos e de capacidade

- Little's Law
- Amdahl's Law
- Tail Latency
- Backpressure
- Queueing Theory

## Objetivo

Sair de:

> "Se ficar lento, coloco mais máquinas."

Para:

> "Consigo identificar o gargalo e entender como o sistema vai se comportar sob carga."

---

# 8. Infraestrutura e Cloud

Não é necessário virar especialista em DevOps, mas um arquiteto precisa entender infraestrutura suficientemente para tomar decisões arquiteturais.

## Conceitos

- Linux
- Networking
- DNS
- HTTP/HTTPS
- TCP/IP
- TLS
- Load Balancer
- Reverse Proxy
- CDN
- Containers
- Docker
- Kubernetes
- Service Mesh
- CI/CD
- Infrastructure as Code
- Cloud
- Availability Zones
- Regions
- Autoscaling
- Object Storage
- VPC
- Firewall
- Secrets
- IAM

## Visão arquitetural

É importante conseguir enxergar o sistema como:

```text
Aplicação
    ↓
Rede
    ↓
Infraestrutura
    ↓
Cloud
```

e entender como as decisões de uma camada impactam as outras.

---

# 9. Segurança Arquitetural

Segurança arquitetural vai muito além de conhecer OAuth.

## Conceitos

- Authentication
- Authorization
- OAuth2
- OpenID Connect
- JWT
- Session
- RBAC
- ABAC
- Least Privilege
- Secrets Management
- Encryption
- TLS
- Encryption at Rest
- Encryption in Transit
- Threat Modeling
- OWASP
- Rate Limiting
- API Security
- Audit
- Zero Trust

## Pergunta fundamental

> **Onde estão os pontos de ataque dessa arquitetura?**

---

# 10. Observabilidade e Operação

Um arquiteto precisa projetar sistemas **operáveis**, não apenas sistemas que compilam.

## Conceitos

- Logs
- Metrics
- Traces
- Distributed Tracing
- Correlation ID
- OpenTelemetry
- Prometheus
- Grafana
- ELK
- Alerting
- SLI
- SLO
- SLA
- Error Budget
- Health Check
- Readiness
- Liveness
- Incident Management
- Chaos Engineering

## Conceito central

```text
Logs + Metrics + Traces
            ↓
      Observabilidade
            ↓
     Comportamento real
          do sistema
```

---

# 11. A Camada Mais Importante: Architectural Trade-offs

O maior repertório de um arquiteto não é decorar tecnologias.

É entender **trade-offs**.

## Exemplos

| Problema | Alternativas |
|---|---|
| Alta carga | Cache / Escala horizontal / Otimização |
| Comunicação entre serviços | REST / gRPC / Messaging |
| Consistência | Strong / Eventual |
| Escalabilidade | Vertical / Horizontal |
| Processamento | Síncrono / Assíncrono |
| Arquitetura | Monólito / Modular / Microservices |
| Dados | SQL / NoSQL |
| Mensageria | RabbitMQ / Kafka |
| Cache | Local / Redis |
| Transação distribuída | Saga / 2PC / Eventual Consistency |
| Deploy | VM / Docker / Kubernetes / Serverless |

## Exemplo de raciocínio arquitetural

O conhecimento arquitetural não é:

> "Kafka é melhor que RabbitMQ."

É:

> "Neste contexto, Kafka é mais adequado porque preciso de retenção, replay, particionamento e alto throughput. O custo é maior complexidade operacional."

**Isso é repertório arquitetural.**

---

# 12. Roadmap de Construção do Repertório

Uma progressão possível:

```text
                 FUNDAMENTOS
                      │
                      ▼
          PRINCÍPIOS + DESIGN DE CÓDIGO
                      │
                      ▼
          ARQUITETURA MODULAR
                      │
                      ▼
          DDD + BOUNDED CONTEXT
                      │
                      ▼
       DESIGN DE SISTEMAS / APIs
                      │
                      ▼
       BANCO + TRANSAÇÕES + CACHE
                      │
                      ▼
        MENSAGERIA + EVENTOS
                      │
                      ▼
        SISTEMAS DISTRIBUÍDOS
                      │
                      ▼
       PERFORMANCE + ESCALABILIDADE
                      │
             ┌────────┴────────┐
             ▼                 ▼
       INFRA / CLOUD       SEGURANÇA
             │                 │
             └────────┬────────┘
                      ▼
              OBSERVABILIDADE
                      │
                      ▼
           SYSTEM DESIGN AVANÇADO
                      │
                      ▼
          DECISÕES ARQUITETURAIS
                      │
                      ▼
                 ARQUITETO
```

---

# 13. Método de Estudo para Construir Repertório

Não estudar arquitetura apenas lendo conceitos.

Para cada conceito, responder **5 perguntas**:

### 1. Qual problema ele resolve?

Entender a motivação.

### 2. Como funciona?

Conhecer o mecanismo técnico.

### 3. Quando devo usar?

Identificar o contexto adequado.

### 4. Quando NÃO devo usar?

Conhecer limitações e cenários inadequados.

### 5. Qual trade-off ele introduz?

Entender o custo da decisão.

---

# 14. Aplicação Prática

Depois de estudar um conceito, aplicar em um caso real.

Por exemplo:

> "Tenho um sistema de pagamentos com processamento assíncrono, alto volume e necessidade de não duplicar pagamentos."

A análise arquitetural pode envolver:

```text
Kafka
  ↓
Idempotência
  ↓
Transação
  ↓
Outbox
  ↓
Retry
  ↓
DLT
  ↓
Observabilidade
  ↓
Banco de Dados
  ↓
Concorrência
  ↓
Escalabilidade
  ↓
Consistência
```

O objetivo não é simplesmente implementar todos esses componentes.

O objetivo é conseguir **justificar cada decisão**:

- Por que Kafka?
- Por que processamento assíncrono?
- Onde está a transação?
- Como garantir idempotência?
- O que acontece se o consumidor falhar?
- Como evitar processamento duplicado?
- O que acontece quando o banco fica indisponível?
- Como controlar retry?
- Quando uma mensagem vai para DLT?
- Como medir o comportamento?
- Como escalar os consumidores?
- Qual consistência é necessária?

Esse tipo de exercício transforma uma lista de conceitos em **repertório arquitetural real**.

---

# 15. Resultado Esperado

Ao desenvolver esse repertório, o objetivo é conseguir olhar para um problema e naturalmente pensar em:

```text
Requisitos
    ↓
Quality Attributes
    ↓
Constraints
    ↓
Problemas
    ↓
Alternativas
    ↓
Trade-offs
    ↓
Decisão Arquitetural
    ↓
Implementação
    ↓
Observabilidade
    ↓
Medição
    ↓
Evolução
```

O arquiteto não é necessariamente quem conhece mais tecnologias.

É quem consegue **tomar boas decisões técnicas diante de restrições reais**, explicar os motivos dessas decisões e antecipar suas consequências.
