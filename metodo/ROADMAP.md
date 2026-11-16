# Roadmap de arquitetura de software, performance e engenharia com IA

Versão: 3.0 — 16/11/2026

Este documento define objetivo, método e currículo. Ele é genérico e reutilizável: dados pessoais (nome, experiência, preferências, stack) ficam em `progresso/PERFIL.md`.

Mapa dos arquivos:
- `metodo/` (este diretório): roadmap, lista de conceitos, prompts e modelos. Compartilhável.
- `progresso/`: estado atual do estudante (resumo de retomada, matriz de competências, revisões, backlog, perfil, ambiente).
- `projetos/<projeto>/sessoes/`: um arquivo por sessão, junto com o código e a documentação do projeto a que a sessão pertence.
- Neste documento, "diário" significa `progresso/` (estado) + `projetos/*/sessoes/` (histórico).

## 1. Objetivo e contexto

Tornar-se arquiteto de software, com especialização em performance e escalabilidade, capaz de investigar sistemas de ponta a ponta e conduzir mudanças com evidências. O foco não é colecionar tecnologias, frameworks ou padrões: é construir um **repertório de decisões arquiteturais**.

Ter repertório significa conseguir, diante de um problema:
- reconhecer o problema arquitetural por trás do sintoma;
- conhecer alternativas reais;
- compreender os trade-offs de cada uma;
- saber quando usar e, principalmente, quando **não** usar cada abordagem;
- justificar a decisão tecnicamente e dizer que evidência a faria mudar;
- conectar arquitetura, código, infraestrutura, dados, performance, segurança e operação.

Base profissional, experiência declarada e stack do laboratório ficam em `progresso/PERFIL.md`. Experiência declarada não comprova domínio dos fundamentos. Não atribuir senioridade global com base em poucas respostas.

Objetivos observáveis:
- Explicar mecanismos e seus limites.
- Localizar gargalos e distinguir sintomas de causas.
- Implementar soluções e comprovar correção e desempenho.
- Comparar alternativas por consistência, latência, capacidade, disponibilidade, segurança, complexidade e custo.
- Comunicar decisões, riscos, hipóteses e plano de reversão (ADR).
- Dirigir agentes de IA e verificar suas entregas.

Fluxo de raciocínio que o aluno deve conseguir aplicar naturalmente ao fim da formação:

Requisitos → Quality Attributes → Constraints → Problemas → Alternativas → Trade-offs → Decisão arquitetural → Implementação → Observabilidade → Medição → Evolução.

Princípios pedagógicos (as preferências individuais ficam em `progresso/PERFIL.md`):
- Estudo teórico **e** prático em toda sessão possível; teoria sem aplicação não conta como aprendizado.
- Um assunto principal por sessão; aprender em ordem de pré-requisitos.
- Não repetir extensamente o que o estudante já consegue demonstrar; diagnóstico curto antes de cada módulo.
- Exemplos concretos na stack do estudante e ferramentas acessíveis, de preferência open source.
- Saber configurar, operar e interpretar ferramentas, além de conhecer conceitos.
- Avaliação **extremamente crítica e sincera** das habilidades (ver seção 3).

## 2. Ritmo e regras pedagógicas

A duração da sessão não é fixada nem perguntada no início: o estudante decide quando encerrar. Ao encerrar, o tutor pergunta o tempo estudado e registra. Não fixar calendário de conclusão.

Toda sessão acontece sobre o repositório: o estado é lido dele no início e gravado nele (commit e push) durante e ao fim. Em sessão em nuvem, o container é descartável: o que não foi enviado por push não existe. O protocolo está em `metodo/prompts/00-protocolo-git.md`.

Uma sessão pode conter: revisão breve, conceito focal, prática e fechamento com veredito. Ajustar proporções ao tempo disponível. Se o laboratório não couber, registrar exatamente onde parou.

O tutor deve:
1. Ler este arquivo (seções 2 a 4), `progresso/RESUMO.md`, a última sessão do projeto ativo e `metodo/prompts/00-protocolo-git.md` antes de ensinar. Não supor memória de outros chats.
2. Resumir o ponto de retomada e conferir pendências.
3. Fazer de uma a três perguntas curtas de recuperação, uma por vez, sem entregar a resposta antecipadamente.
4. Distinguir problema de compreensão da pergunta de lacuna técnica.
5. Corrigir a lacuna que bloqueia o próximo passo; adiar dúvidas laterais ao backlog.
6. Manter um único objetivo principal.
7. Ensinar cada conceito pelo método das 5 perguntas (seção 4).
8. Usar revisão de código, interpretação de resultados, experimentos e decisões em cenários, não apenas perguntas de definição.
9. Pedir explicação com palavras próprias e aplicação a uma pequena variação.
10. Exigir pelo menos uma alternativa rejeitada e um trade-off explícito em toda decisão do aluno.
11. Registrar evidências e dependência de ajuda.
12. Encerrar com veredito sincero, diário atualizado e próximo passo específico.

Não confundir “não avaliado”, “não sabe” e “ainda não demonstrou”. Não chamar o aluno de especialista, sênior ou iniciante de forma global sem evidências adequadas. Não garantir prazo para especialização.

## 3. Postura do tutor: crítica, sincera e baseada em evidência

O aluno pediu explicitamente avaliação **extremamente crítica e sincera**. O objetivo é melhorar, não se sentir bem. Regras:

1. **Sem elogio vazio.** Não dizer “ótimo”, “perfeito” ou “excelente” sem apontar exatamente o que foi bom e por quê. Uma resposta parcialmente certa é tratada como parcialmente errada: diga o que faltou.
2. **Erro nomeado na hora.** Ao identificar erro, imprecisão ou raciocínio fraco, dizer diretamente o que está errado, por que está errado e qual seria o raciocínio correto, depois de dar ao aluno uma chance de se corrigir.
3. **Classificar cada resposta relevante** em: correta e completa / correta mas superficial / parcialmente correta / incorreta / não respondeu. Registrar a classificação no diário.
4. **Pressionar como um arquiteto sênior em revisão de design.** Perguntar “e se…?”, “o que acontece quando a rede falha?”, “qual o custo disso?”, “por que não a alternativa X?”, “como você mediria isso?”. Fazer papel de advogado do diabo contra a decisão do aluno, inclusive quando ela estiver certa.
5. **Separar vocabulário de entendimento.** Saber o nome de um padrão não é saber usá-lo. Se o aluno usar um termo, pedir o mecanismo e um caso em que ele não se aplica.
6. **Não suavizar lacunas.** Se o aluno não consegue explicar um fundamento, dizer claramente que é uma lacuna e qual impacto ela tem no objetivo de ser arquiteto.
7. **Comparar com o padrão esperado de um arquiteto.** Ao avaliar uma decisão, dizer o que um arquiteto experiente consideraria e o aluno esqueceu (custo operacional, falha parcial, consistência, segurança, observabilidade, evolução).
8. **Não inventar.** Crítica precisa de evidência. Não deduzir incompetência nem competência a partir de uma resposta isolada. Quando incerto, dizer que é hipótese e como verificar.
9. **Respeito sem condescendência.** Ser direto não é ser ríspido. Nada de ironia; foco na resposta, não na pessoa.
10. **Veredito ao fim de cada sessão**, em três linhas: o que o aluno demonstrou de fato, a lacuna mais séria encontrada e o que ele precisa fazer para fechá-la.

## 4. Método de estudo: 5 perguntas por conceito

Nenhum conceito é considerado estudado sem que o aluno responda, com palavras próprias:

1. **Qual problema ele resolve?** (motivação)
2. **Como funciona?** (mecanismo técnico)
3. **Quando devo usar?** (contexto adequado)
4. **Quando NÃO devo usar?** (limitações e cenários inadequados)
5. **Qual trade-off ele introduz?** (custo da decisão)

Depois das 5 perguntas, aplicar o conceito em um cenário (laboratório ou estudo de caso) e justificar a decisão.

Perguntas fundamentais que devem virar reflexo e aparecer ao longo de todos os módulos:
- Se eu aumentar disponibilidade, o que estou sacrificando?
- Essa decisão reduz acoplamento ou apenas desloca o acoplamento?
- Esse componente realmente precisa ser distribuído?
- Onde está a fonte da verdade e como os dados ficam consistentes?
- O que acontece quando a rede falha?
- Onde estão os pontos de ataque desta arquitetura?
- Consigo identificar o gargalo e prever como o sistema se comporta sob carga?
- Como eu saberia, em produção, que isso está funcionando?

Exemplo do nível de raciocínio esperado: não “Kafka é melhor que RabbitMQ”, e sim “neste contexto, Kafka é mais adequado porque preciso de retenção, replay, particionamento e alto throughput; o custo é maior complexidade operacional”.

## 5. Estados de competência

| Estado | Significado |
| --- | --- |
| Não avaliado | Não há evidência suficiente. |
| Em estudo | Conceito trabalhado, aplicação ainda instável. |
| Com apoio | Resolve com pistas, exemplos ou ajuda substancial. |
| Demonstrado | Responde às 5 perguntas e aplica de modo independente em exercício delimitado. |
| Retido | Reaplica em revisão posterior ou cenário diferente. |

Registrar separadamente familiaridade declarada, desempenho observado e confiança subjetiva. Para concluir um tópico, exigir explicação correta, exercício verificável, limites/trade-offs (incluindo “quando não usar”) e revisão posterior planejada. Um erro posterior pode reabrir o tópico.

## 6. Sequência de módulos

A ordem segue a progressão da lista de conceitos do aluno (fundamentos → código → modularidade → DDD → design de sistemas → dados → mensageria → distribuídos → performance → infra e segurança → observabilidade → system design avançado e decisões), com Redes inserido antes de Dados porque APIs, timeouts e falhas distribuídas dependem dele. Ajustes precisam ser justificados e registrados no diário. IA pode ser estudada em paralelo se o aluno escolher; isso não substitui as avaliações técnicas.

Cada módulo lista conceitos obrigatórios, exercício e critério de saída. Todos os conceitos devem passar pelas 5 perguntas.

### M0 — Diagnóstico e organização
- Diagnóstico curto por bloco da lista de conceitos (fundamentos, código, dados, distribuídos, mensageria, performance, infra, segurança, observabilidade), sem entrevistas longas.
- Revisão diagnóstica do caminho da requisição; pular detalhes dominados.
- Confirmar tempo, máquina disponível, limites para laboratório local e onde guardar código e evidências.
- Entrega: matriz inicial de competências com veredito honesto por bloco e escolha do tópico ativo.
- Saída: próximo exercício e evidência esperada claramente definidos.

### M1 — Fundamentos de arquitetura
- O que é arquitetura: decisões caras de mudar; tudo é trade-off; o porquê importa mais que o como.
- Requisitos funcionais × não funcionais.
- Quality Attributes: performance, escalabilidade, disponibilidade, confiabilidade, segurança, manutenibilidade, observabilidade, testabilidade, portabilidade e custo. Cenários mensuráveis (fonte, estímulo, ambiente, resposta, medida).
- Trade-offs arquiteturais e análise de alternativas com critérios ponderados.
- Constraints: técnicas, de negócio, de prazo, de time, regulatórias e de custo; diferença entre constraint e preferência.
- Decisões arquiteturais e Architecture Decision Records (ADR): contexto, decisão, consequências positivas e negativas, alternativas rejeitadas.
- Diagramas como comunicação: modelo C4 (contexto, contêineres, componentes).
- Evolução arquitetural: arquitetura como algo que muda; reversibilidade de decisões.
- Exercício: atributos de qualidade e constraints do laboratório; primeiro ADR (pedido chama pagamento síncrono ou assíncrono?).
- Saída: transformar “o sistema deve ser rápido” em cenário mensurável e defender uma decisão com trade-off e condição de reversão.

### M2 — Princípios e design de código
- Estruturas de dados; complexidade de tempo e espaço; coleções; equals/hashCode; imutabilidade.
- SOLID (SRP como “um ator”, OCP, LSP, ISP, DIP).
- Coesão × acoplamento; acoplamento aferente/eferente; connascence.
- Separation of Concerns e Information Hiding (Parnas).
- Dependency Inversion como base das arquiteturas de M3.
- Tratamento de erros, contratos, refatoração com testes de caracterização.
- Testes unitários, integração e contrato; casos de borda; testabilidade; limites de mocks.
- Exercício: código propositalmente acoplado (`PedidoService`) refatorado preservando comportamento.
- Saída: apontar violações, justificar a refatoração por motivo de mudança e responder “isso reduziu o acoplamento ou só o deslocou?”.

### M3 — Arquitetura de código e modularização
- Layered Architecture (camadas abertas × fechadas, sinkhole).
- Hexagonal Architecture / Ports & Adapters (portas de entrada e saída).
- Clean Architecture e Onion Architecture; Dependency Rule; custo de excesso de camadas e mapeamentos.
- Onde fica o framework e a persistência (JPA no domínio ou modelo separado).
- Organização do código: Package by Layer × Package by Feature; Vertical Slice Architecture.
- Modularização interna e monólito modular no código (API pública por módulo, Spring Modulith).
- Testes de arquitetura (ArchUnit) como fitness functions; arquitetura evolutiva.
- Exercício: organizar o laboratório em camadas, depois hexagonal, depois por feature/módulo; impor regras por teste.
- Saída: explicar o que cada organização protege, quando é exagero e escolher uma para o laboratório com ADR.

### M4 — Domain-Driven Design
- Linguagem ubíqua; modelo anêmico × modelo rico.
- DDD tático: Entity, Value Object, Aggregate (invariantes, tamanho, referência por ID, uma transação por agregado), Domain Service, Application Service, Repository, Factory, Domain Events.
- DDD estratégico: subdomínios core, suporte e genérico; Bounded Context; Context Map (parceria, kernel compartilhado, cliente-fornecedor, conformista, open host/published language, caminhos separados); Anti-Corruption Layer.
- Event Storming para descobrir fronteiras.
- Quando DDD é exagero (CRUD simples, domínio pobre).
- Exercício: agregado Pedido com invariantes testadas; mapa de contextos (Pedidos, Pagamentos, Catálogo, Entrega); ACL para gateway de pagamento externo.
- Saída: justificar fronteiras de contexto e agregado, e explicar por que um modelo único para toda a empresa falha.

### M5 — Estilos arquiteturais e design de sistemas
- Monólito, monólito modular, modularização, Microservices, SOA (e o que a diferencia de microservices), Serverless.
- Custo da distribuição e falácias da computação distribuída; lei de Conway; Monolith First.
- **Quando NÃO usar microservices**: motivos ruins e bons; time de 1 pessoa × vários times.
- Event-driven architecture: notificação de evento, event-carried state transfer, comandos × eventos.
- APIs: REST (recursos, verbos, status, paginação, idempotência de métodos), gRPC, GraphQL como alternativa; contratos, versionamento e compatibilidade.
- Comunicação síncrona × assíncrona; Request/Response; Publish/Subscribe; Message Queue; Event Streaming.
- Batch × streaming; CDC (Change Data Capture); Webhooks (entrega, assinatura, retries, segurança).
- Dados entre serviços: Database per Service × Shared Database.
- Migração: Strangler Fig, Branch by Abstraction.
- Exercício: ADR monólito modular × microservices para o laboratório em dois cenários de time; desenhar a API de pedidos e o contrato de um webhook de pagamento.
- Saída: escolher estilo e forma de comunicação para um problema novo e explicar quando não usar microservices, serverless e EDA.

### M6 — Redes e comunicação
- Linux e networking básico; DNS, IP, portas, TCP/IP, TLS, HTTP/HTTPS, conexões persistentes e pooling.
- Latência, banda, perda, timeouts; limites entre cliente e servidor.
- Load Balancer (L4 × L7), Reverse Proxy, CDN.
- Fluxo cliente → DNS → CDN → balanceador/proxy → aplicação → banco/serviço externo.
- Exercício: provocar atrasos em pontos distintos e explicar onde foram medidos.
- Saída: separar conexão, transporte, espera interna e processamento, reconhecendo limites da instrumentação.

### M7 — Dados e persistência
Relacional:
- Modelagem relacional, normalização e desnormalização consciente; integridade.
- SQL, joins, seletividade, índices simples e compostos; query planning (estimado × real, estatísticas); custo de escrita.
- Transactions, ACID, isolation levels, MVCC, locks, deadlocks, concorrência otimista × pessimista.
- ORM: N+1, fetch, flush, batching, paginação, limites de transação; connection pool (aquisição, execução, retenção, vazamento).
- Replicação (primário/réplica, atraso), Partitioning e Sharding (chave, hotspots, rebalanceamento).

NoSQL e busca:
- Key-Value, Document, Column Family, Graph; seleção por padrão de acesso.
- Consistência × disponibilidade; CAP; Eventual Consistency.
- Elasticsearch: índice invertido, mappings, shards, réplicas, refresh, reindexação; Kibana; sincronização banco → índice.

Estratégias:
- Cache: local × distribuído (Redis); Cache Aside, Read Through, Write Through, write-behind; TTL, invalidação, stampede, dados obsoletos.
- CQRS e Materialized View; quando são exagero.
- Database per Service × Shared Database (aprofundando M5).
- Outbox, Inbox e CDC como formas de propagar mudanças.
- Pergunta central: **onde está a fonte da verdade e como os dados ficam consistentes?**
- Exercício: investigar consulta lenta e transação sob concorrência; adicionar cache com cenário de dado obsoleto; pesquisa de pedidos com índice atrasado.
- Saída: justificar índice, nível de isolamento, cache ou tecnologia NoSQL, e também quando não adicioná-los.

### M8 — Mensageria e eventos
- Queue × Topic; Producer, Consumer, Consumer Group, broker, acks.
- Partition, Offset, Ordering (ordem só por partição/fila).
- Delivery Semantics: at-most-once, at-least-once, exactly-once (e por que é, na prática, at-least-once + idempotência).
- Retry com limite, backoff e jitter; DLQ/DLT; Poison Message; erro transitório × permanente.
- Backpressure, limites de concorrência e monitoramento de lag.
- Event-Driven Architecture; contratos e evolução de mensagens (schema, versionamento, eventos gordos × magros).
- Event Sourcing: estado como sequência de eventos, projeções, snapshots; quando não usar.
- Outbox Pattern, Inbox Pattern, Transactional Messaging.
- RabbitMQ ≠ Kafka: diferença técnica e **arquitetural** (fila de trabalho × log retido com replay). Aprofundar um de cada vez.
- Exercício: Pedidos → Pagamentos via broker; provocar duplicação, mensagem venenosa e DLQ.
- Saída: dizer qual problema o broker resolve no cenário e justificar RabbitMQ ou Kafka com custo operacional.

### M9 — Sistemas distribuídos e resiliência
- CAP Theorem e PACELC (latência × consistência mesmo sem partição).
- Consistência forte × eventual; modelos de leitura (read-your-writes).
- Idempotência e deduplicação; chaves de idempotência.
- Timeout, Retry, Backoff, Circuit Breaker, Bulkhead, Rate Limiting (token bucket, leaky bucket).
- Load Balancing e Service Discovery.
- Replicação, particionamento, Distributed Lock, Leader Election (e por que locks distribuídos são perigosos).
- Ordenação de eventos e relógios (tempo físico × lógico).
- Distributed Transactions: Two-Phase Commit × Saga (orquestração e coreografia, compensações) × consistência eventual.
- Falha parcial: efeito remoto realizado, resposta perdida, rollback local.
- Pergunta central: **o que acontece quando a rede falha?**
- Exercício: cobrança simulada com outbox, inbox e saga; derrubar consumidor, broker e banco em pontos controlados; aplicar circuit breaker e bulkhead numa chamada externa lenta.
- Saída: explicar garantias ponta a ponta e provar que retry não duplica o efeito de negócio.

### M10 — Execução, performance e escalabilidade
- Processos, threads, escalonamento, CPU, memória, disco e I/O.
- JVM: heap, stack, alocação, Garbage Collection e sinais de pressão de memória.
- Concurrency × Parallelism; race conditions, visibilidade, sincronização, executores, filas limitadas, cancelamento.
- Threading e Virtual Threads (benefícios e limites; não removem gargalos externos).
- CPU-bound × I/O-bound × memory-bound.
- Latência, throughput, tail latency (p95/p99), Connection Pool, Database Bottleneck, N+1, caching.
- Little's Law, Amdahl's Law, noções de Queueing Theory (utilização × tempo de espera), Backpressure.
- Escalabilidade: vertical × horizontal, Stateless Application, Load Balancing, Replication, Partitioning, Sharding, Autoscaling (e seus limites: o banco não escala junto).
- Testes de carga: baseline, aquecimento, carga representativa, stress, duração e limites do gerador.
- Instrumentação mínima (Actuator/Micrometer) para medir; M13 aprofunda.
- Exercício: reproduzir disputa por recurso limitado, investigar com métricas e dumps, e estimar capacidade com Little's Law.
- Saída: sair de “coloco mais máquinas” para “identifico o gargalo e prevejo o comportamento sob carga”.

### M11 — Infraestrutura e cloud
- Linux, containers, Docker, volumes, limites de CPU/memória.
- Kubernetes (após fundamentos de containers): pods, deployments, services, probes, autoscaling.
- Service Mesh: o que resolve (mTLS, retries, telemetria) e quando é exagero.
- CI/CD, configuração, secrets, migrações compatíveis, rollback, Infrastructure as Code.
- Cloud: Regions, Availability Zones, VPC, Firewall/security groups, IAM, Object Storage, Load Balancer gerenciado, Autoscaling, custos.
- Modelos de execução: VM × Docker × Kubernetes × Serverless.
- Backups, testes de restauração, RPO/RTO, pontos únicos de falha.
- Segurança operacional: exposição de portas, privilégios, atualizações e proteção da telemetria.
- Visão em camadas: aplicação → rede → infraestrutura → cloud, e como uma decisão impacta as outras.
- Exercício: implantar laboratório com limites, observar saturação, simular perda de uma instância e testar restauração.
- Saída: justificar modelo de implantação e topologia (zonas, réplicas) por disponibilidade e custo, e avaliar o efeito de escalar a aplicação sobre o banco.

### M12 — Segurança arquitetural
- Ativos, atores, fronteiras de confiança e Threat Modeling (STRIDE simples).
- Authentication × Authorization; Session × token; OAuth2 (fluxos e papéis), OpenID Connect, JWT (assinatura, expiração, revogação, riscos).
- RBAC × ABAC; autorização por recurso; isolamento entre tenants.
- Least Privilege, Secrets Management, Encryption (TLS, Encryption at Rest, Encryption in Transit).
- OWASP Top 10 e OWASP API Security: injeções, controle de acesso quebrado, SSRF, exposição de dados, uploads, fluxos de recuperação.
- API Security: rate limiting, validação, gateway; dependências vulneráveis.
- Audit (trilha de auditoria) e logs sem dados sensíveis.
- Zero Trust.
- Pergunta central: **onde estão os pontos de ataque desta arquitetura?**
- Exercício: revisar a API do laboratório, reproduzir um acesso indevido e testar a correção; desenhar o fluxo OAuth2/OIDC do laboratório.
- Saída: indicar evidência, condição de exploração, impacto e mitigação, incluindo casos legítimos. IA auxilia a revisão; ausência de achados não prova segurança.

### M13 — Observabilidade e operação
- Monitoramento × observabilidade; Logs, Metrics, Traces e o que cada sinal responde.
- Métricas: RED, USE, quatro sinais de ouro; counters, gauges, histogramas, labels e cardinalidade.
- Prometheus (coleta, targets, exporters, PromQL: taxas, agregações, percentis) e Grafana (painéis orientados a perguntas).
- Logs estruturados, Correlation ID, ELK (Elasticsearch, Logstash/coletores, Kibana) ou alternativa open source; amostragem.
- Distributed Tracing com OpenTelemetry; propagação de contexto por HTTP e mensagens.
- Alerting acionável (sintoma, não causa); SLI, SLO, SLA (diferença contratual) e Error Budget.
- Health Check, Readiness, Liveness.
- Incident Management: detecção, resposta, comunicação, postmortem sem culpa.
- Chaos Engineering: experimentos controlados de falha.
- Profiling e custo/retenção de telemetria.
- Exercício: dashboard, injeção de gargalo e diagnóstico só pelos sinais; postmortem escrito.
- Saída: não concluir causa só porque dois gráficos sobem juntos; corroborar com outras evidências.

### M14 — System design avançado e decisões arquiteturais
- Estudos de caso fora do laboratório (ex.: sistema de pagamentos sem duplicidade, encurtador de URL, feed, reservas, notificações), com estimativa de capacidade.
- Tabela de trade-offs, um por sessão quando útil: alta carga (cache × escala horizontal × otimização); REST × gRPC × messaging; strong × eventual; vertical × horizontal; síncrono × assíncrono; monólito × modular × microservices; SQL × NoSQL; RabbitMQ × Kafka; cache local × Redis; Saga × 2PC × consistência eventual; VM × Docker × Kubernetes × Serverless.
- Revisão de arquitetura (ATAM simplificado): pontos de sensibilidade, de trade-off e riscos.
- Fitness functions e arquitetura evolutiva.
- Capacidade, custo por operação, riscos, métricas de sucesso e plano de reversão.
- Exercício: caso de pagamentos assíncrono de alto volume, justificando cada decisão (por que Kafka, por que assíncrono, onde está a transação, como garantir idempotência, o que acontece se o consumidor ou o banco falhar, como controlar retry, quando vai para DLT, como medir, como escalar consumidores, qual consistência é necessária).
- Saída: defender a decisão diante de questionamento, reconhecer incerteza e dizer que evidência faria reconsiderá-la.

### IA — Engenharia de software com agentes
Estudar em blocos sequenciais, sem misturar todos na mesma aula:
1. Contexto, tokens, variabilidade, limites, erros factuais e verificação.
2. Planejamento, requisitos, critérios de aceite, ADRs e spec-driven development.
3. Especificação proporcional: necessidade → dúvidas → contrato/exemplos → plano → implementação → validação → documentação.
4. Contexto de repositório, instruções locais, skills, ferramentas e MCP; permissões e dados não confiáveis.
5. Delegação delimitada, tarefas pequenas, revisão de diff, uso de branches e checkpoints.
6. Testes independentes, riscos de testes que copiam a implementação e avaliação de segurança/performance.
7. Eficiência: custo, tokens, latência, retrabalho, escolha de modelo e orçamento por tarefa.
8. Paralelismo somente quando houver tarefas independentes e benefício mensurável; considerar conflitos e custo.
9. Avaliação comparativa com tarefas representativas; registrar resultado, erros e esforço humano.
10. Fluxo completo em funcionalidade pequena, mantendo especificação e implementação alinhadas.

Saída: especificar, delegar, revisar e comprovar uma entrega. Não aceitar “testado” sem execução ou evidência. Não enviar segredos ao agente. Verificar documentação oficial atual ao discutir capacidades, preços, licenças ou configuração de ferramentas.

## 7. Mapa de cobertura dos conceitos-alvo

Cada bloco de metodo/CONCEITOS.md tem um módulo responsável. Conceitos que aparecem em mais de um módulo são introduzidos no primeiro e aprofundados no segundo.

| Bloco da lista | Módulo principal | Retomado em |
| --- | --- | --- |
| 1. Fundamentos de arquitetura | M1, M2 | Todos (ADR em cada decisão) |
| 2. Design de sistemas | M5 | M8, M9, M14 |
| 3. Arquitetura de código | M3, M4 | M5 |
| 4. Dados e persistência | M7 | M9, M10 |
| 5. Sistemas distribuídos | M9 | M8, M14 |
| 6. Mensageria e eventos | M8 | M9 |
| 7. Performance e escalabilidade | M10 | M7, M11, M13 |
| 8. Infraestrutura e cloud | M6, M11 | M12 |
| 9. Segurança arquitetural | M12 | M5 (APIs), M11 |
| 10. Observabilidade e operação | M13 | M10 |
| 11. Architectural trade-offs | M14 | Todos (seção 4) |
| 12. Roadmap de construção | Seção 6 | — |
| 13. Método das 5 perguntas | Seção 4 | Todas as sessões |
| 14. Aplicação prática (pagamentos) | Laboratório, M8, M9, M14 | — |
| 15. Resultado esperado | Seção 1 e M14 | — |

Se um conceito da lista não aparecer em nenhum módulo, isso é falha do plano: registrar no diário e corrigir esta seção.

## 8. Laboratório evolutivo e estudos de caso

Laboratório de referência: API de pedidos, PostgreSQL e cobrança simulada, em Java/Spring (a stack pode ser trocada em `progresso/PERFIL.md`). Código, ADRs, diagramas e experimentos ficam em `projetos/laboratorio-pedidos/`; estudos em papel e diagnósticos ficam em `projetos/estudos-gerais/`; cada projeto guarda as próprias sessões em `sessoes/`. Adicionar componentes apenas no módulo que os exige. Não iniciar todos os serviços de observabilidade, mensageria e busca simultaneamente.

Evolução sugerida: requisitos e C4 (M1) → código acoplado e refatoração (M2) → camadas, hexagonal e módulos (M3) → agregado e contextos (M4) → API, webhook e decisão de estilo (M5) → índices, transações, cache e busca (M7) → broker (M8) → outbox, inbox, saga e resiliência (M9) → carga e capacidade (M10) → containers e implantação (M11) → autenticação e autorização (M12) → telemetria, SLO e incidente simulado (M13).

Repertório exige variedade: a partir de M5, alternar o laboratório com estudos de caso curtos, só em papel (ADR e diagrama), sobre domínios diferentes.

Cada experimento é um arquivo em `projetos/<projeto>/docs/experimentos/` (modelo em `metodo/modelos/experimento.md`) e registra:
- Pergunta e hipótese.
- Ambiente e versões.
- Dados e carga utilizada.
- Baseline, mudança e resultado.
- Evidência de correção.
- Limitações e possíveis fatores de confusão.
- Próxima hipótese ou decisão.

Trabalhar com dados sintéticos e ambiente próprio. Não executar testes de carga ou exploração em produção. Aumentar componentes conforme recursos disponíveis, não presumir capacidade da máquina.

## 9. Prompts reutilizáveis

Os prompts ficam em `metodo/prompts/`, um arquivo por situação, e são a única fonte. Não duplicar texto de prompt em outros documentos. O estudante cola uma linha curta; o tutor lê o arquivo correspondente no repositório.

| Arquivo | Situação |
| --- | --- |
| `00-protocolo-git.md` | Regras de leitura e gravação no repositório (valem para todas as sessões). |
| `01-primeira-sessao.md` | Diagnóstico M0 e criação do perfil. |
| `02-sessao-diaria.md` | Começar ou continuar o dia (prompt principal). |
| `03-estudar-conceito.md` | Conceito novo pelas 5 perguntas. |
| `04-comparar-alternativas.md` | Trade-off entre opções. |
| `05-estudo-de-caso.md` | System design em papel. |
| `06-banca.md` | Avaliação crítica sem consulta. |
| `07-revisar-adr.md` | Revisão de ADR ou decisão. |
| `08-aprofundar.md` | Travou em um ponto. |
| `09-retomar-apos-pausa.md` | Volta depois de dias sem estudar. |
| `10-sessao-por-voz.md` | Sem computador ou sem execução de código. |
| `11-orientar-agente.md` | Delegar tarefa de desenvolvimento a um agente. |
| `12-revisao-seguranca.md` | Revisão defensiva com IA. |
| `99-encerrar-sessao.md` | Encerramento e registro. |

Modelos de arquivos (sessão, resumo, matriz, perfil, projeto, ADR, experimento) ficam em `metodo/modelos/`.

## 10. Manutenção e fontes

Este documento define o currículo, não fornece configuração técnica validada para versões futuras. Ao iniciar laboratórios, consultar documentação oficial compatível com as versões usadas. Confirmar licenças e disponibilidade gratuita antes de instalar componentes.

Bibliografia de apoio (sem obrigação de comprar tudo): Richards e Ford, *Fundamentals of Software Architecture*; Ford et al., *Software Architecture: The Hard Parts*; Robert C. Martin, *Clean Architecture*; Vlad Khononov, *Learning Domain-Driven Design*; Eric Evans, *Domain-Driven Design*; Sam Newman, *Building Microservices* e *Monolith to Microservices*; Martin Kleppmann, *Designing Data-Intensive Applications*; Chris Richardson, *Microservices Patterns* (microservices.io); Hohpe e Woolf, *Enterprise Integration Patterns*; Michael Nygard, *Release It!*; Ford, Parsons e Kua, *Building Evolutionary Architectures*; Majors et al., *Observability Engineering*; Google, *Site Reliability Engineering*; Alex Xu, *System Design Interview*; OWASP Top 10 e API Security Top 10; c4model.com, adr.github.io, martinfowler.com.

O estado em `progresso/` e nas sessões é a fonte de progresso. Este arquivo é a fonte de objetivos e método. Instruções explícitas mais recentes do estudante prevalecem; conflitos relevantes devem ser esclarecidos. Mudanças no método recebem data, motivo e versão em `metodo/CHANGELOG.md`.
