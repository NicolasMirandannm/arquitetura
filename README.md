# Arquitetura de software: formação com tutor de IA

Rotina de estudo teórico e prático, com avaliação crítica e sincera, em que **o repositório guarda todo o estado**. Funciona em sessões na nuvem ou locais, em qualquer computador.

## Estrutura

| Pasta | O que tem | Compartilhável? |
| --- | --- | --- |
| `metodo/` | Roadmap (M0–M14), lista de conceitos, prompts, modelos e changelog do método. | **Sim.** Sem dados pessoais. |
| `progresso/` | Estado do estudante: perfil, ambiente, resumo de retomada, matriz de competências, revisões, backlog, histórico do plano. | Não. |
| `projetos/<projeto>/` | Sessões (`sessoes/`), ADRs, diagramas, experimentos (`docs/`) e código (`app/`) de cada projeto. | Não. |

Projetos atuais: `laboratorio-pedidos` (API de pedidos em Java/Spring, onde o código evolui módulo a módulo) e `estudos-gerais` (diagnóstico, teoria e estudos de caso em papel).

## Rotina

1. Abra uma sessão (Claude Code na web, com este repositório anexado, ou local na pasta do repositório).
2. Cole o prompt de `metodo/prompts/02-sessao-diaria.md` (uma linha, com o tema).
3. Estude. O tutor faz checkpoints com commit e push durante a sessão.
4. Para encerrar, diga "Encerrar" (`metodo/prompts/99-encerrar-sessao.md`). Confira a confirmação do push (hash e `ls-remote`).
5. Só abra outra sessão, em outra máquina, depois de encerrar a anterior.

Primeira vez: `metodo/prompts/01-primeira-sessao.md`. Detalhes de uso e de adoção por outras pessoas: `metodo/README.md`.
