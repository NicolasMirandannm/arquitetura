# Matriz de competências

Estados: Não avaliado / Em estudo / Com apoio / Demonstrado / Retido. Registrar separadamente familiaridade declarada, desempenho observado e confiança subjetiva. Mudar o estado só com evidência nova (link para a sessão).

As linhas de S000 vêm do diário original (24/10/2026); as demais foram criadas em 15/11/2026 para cobrir os blocos da lista de conceitos. Nenhuma tem evidência de laboratório.

| Área | Módulo | Evidência | Estado | Próxima verificação |
| --- | --- | --- | --- | --- |
| Investigação de performance | M10, M13 | Propôs usar observabilidade/tracing, examinar consultas, volume, concorrência e índices antes de escalar. | Evidência oral parcial; prática não avaliada | Interpretar métricas/traces em cenário concreto. |
| Pools e concorrência | M7, M10 | Sugeriu relação entre conexões e threads; declarou não conseguir aprofundar. | Em estudo | Distinguir aquisição, execução e retenção com exemplo. |
| Transações e chamada externa | M7, M9 | Reconheceu possível timeout e rollback local. | Evidência oral parcial | Investigar bloqueios e falha parcial. |
| Idempotência | M8, M9 | Pergunta de cobrança duplicada apresentada, sem resposta técnica avaliada. | Não avaliado | Diagnóstico quando chegar a distribuídos. |
| Desenvolvimento e testes | M2 | Experiência profissional declarada; sem exercício nesta conversa. | Não avaliado | Revisão curta de código e escolha de estrutura de dados. |
| JVM e sistemas operacionais | M10 | Nenhuma avaliação específica. | Não avaliado | Avaliação de entrada do módulo. |
| Redes e infraestrutura | M6, M11 | Familiaridade declarada com parte do fluxo; não demonstrada nesta sessão. | Não avaliado | Diagnóstico curto, sem presumir iniciante. |
| SQL, ORM e índices | M7 | Citou índices como hipótese; sem plano de execução analisado. | Não avaliado em profundidade | Interpretar consulta e plano. |
| Prometheus/Grafana e tracing | M13 | Interesse em configurar, consultar, gerar dashboards e interpretar sinais. | Não avaliado | Coleta e dashboard no módulo próprio. |
| Mensageria | M8 | Sem diagnóstico completo nesta conversa. | Não avaliado | Garantias e falhas em exercício. |
| NoSQL/Elasticsearch/Kibana | M7 | Interesse em busca, índices e decisões de armazenamento. | Não avaliado | Avaliação do módulo. |
| Segurança | M12 | Solicitou reconhecer riscos e orientar IA. | Não avaliado | Revisão de fluxo de autorização. |
| Engenharia com IA | IA | Solicitou spec-driven, agentes, eficiência e limites. | Não avaliado | Especificar e revisar uma tarefa pequena. |
| Fundamentos de arquitetura (requisitos, quality attributes, constraints, trade-offs, ADR) | M1 | Nenhuma. | Não avaliado | Escrever cenário mensurável e um ADR no M0/M1. |
| Princípios de design (SOLID, coesão/acoplamento, SoC, information hiding) | M2 | Nenhuma. | Não avaliado | Apontar violações em código acoplado. |
| Arquitetura de código (camadas, hexagonal, clean, onion, vertical slice, modularização) | M3 | Nenhuma. | Não avaliado | Explicar o que a hexagonal protege e quando é exagero. |
| DDD tático e estratégico | M4 | Nenhuma. | Não avaliado | Diferenciar entidade, objeto de valor e agregado num caso. |
| Estilos e design de sistemas (monólito, modular, microservices, SOA, serverless, EDA, APIs, batch, CDC, webhooks) | M5 | Nenhuma. | Não avaliado | Justificar quando não usar microservices. |
| Cache e consistência de dados (cache aside, read/write-through, CQRS, outbox, CDC, fonte da verdade) | M7 | Nenhuma. | Não avaliado | Cenário de dado obsoleto em cache. |
| Sistemas distribuídos e resiliência (CAP/PACELC, circuit breaker, bulkhead, rate limiting, saga, 2PC, locks, leader election) | M9 | Nenhuma além da linha “Idempotência”. | Não avaliado | Responder “o que acontece quando a rede falha?” num fluxo concreto. |
| Escalabilidade e capacidade (horizontal/vertical, stateless, autoscaling, Little, Amdahl, filas) | M10 | Nenhuma. | Não avaliado | Estimar capacidade com Little's Law. |
| Cloud e plataforma (Docker, Kubernetes, service mesh, regiões/zonas, VPC, IAM, IaC) | M11 | Nenhuma. | Não avaliado | Justificar topologia por disponibilidade e custo. |
| Operação (SLI/SLO/SLA, error budget, health/readiness/liveness, incidentes, chaos) | M13 | Nenhuma. | Não avaliado | Definir SLO e alerta para o laboratório. |
| System design e trade-offs | M14 | Nenhuma. | Não avaliado | Estudo de caso conduzido como entrevista. |
