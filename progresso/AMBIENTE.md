# Ambientes de estudo

Fatos verificados em 16/11/2026 na sessão de configuração do repositório (não é sessão de estudo). Reverificar antes de depender deles: versões e limites mudam.

## Nuvem (Claude Code na web, ambiente "Estudo Arquitetura")

- Verificado: Java e Maven e Gradle instalados; PostgreSQL 16 instalado (cliente e pacote do servidor; servidor não foi iniciado); git 2.43; gh; Node 22; Python 3.13; 4 vCPU; 16 GB de RAM; disco com folga.
- Verificado: o cliente Docker existe, mas o **daemon não está rodando** (`docker run` falhou). Não foi testado se dá para subir um.
- Rede limitada: Maven Central, Docker Hub e GitHub responderam ao teste; um build real ainda não foi feito.
- Container efêmero: só o que foi enviado por push ao repositório sobrevive.
- Execução em VM compartilhada: medições de desempenho (M10) têm ruído; registrar como fator de confusão.
- Provável inviável ou a verificar: M6 (atrasos de rede induzidos), M11 (containers e Kubernetes) e M13 (Prometheus, Grafana, Kafka, ELK) por depender de Docker e privilégios.

## Notebook e PC (local)

- Notebook (declarado em 16/11/2026, não verificado): Windows, 16 GB de RAM (declarado). Saída colada pelo estudante em 16/11/2026: Temurin OpenJDK 21.0.13 LTS (terminal UCRT64/MSYS2) e Docker Desktop 4.98.0 (engine 29.9.2, daemon respondendo). Faltam: CPU, Maven/Gradle, editor. Obs.: o `java` visto é o do shell UCRT64; confirmar que é o mesmo no PowerShell/IDE.
- PC: não levantado.
- Sugestão: laboratórios de M6, M10, M11 e M13 no PC local com este mesmo repositório.

## Acesso ao repositório

- Repositório: https://github.com/NicolasMirandannm/arquitetura
- Em 16/11/2026 o push a partir da nuvem foi recusado: o Claude GitHub App não está instalado nesse repositório. Resolver antes da primeira sessão (ver `BACKLOG.md`).
