# Método: formação em arquitetura de software com tutor de IA

Currículo, prompts e modelos para estudar arquitetura de software com repertório de decisões (problema, alternativas, trade-offs, quando usar e quando não usar). Este diretório é independente de quem estuda: dados pessoais não ficam aqui.

## O que há aqui
- `ROADMAP.md`: objetivo, postura do tutor (crítica e sincera), método das 5 perguntas, estados de competência e módulos M0–M14.
- `CONCEITOS.md`: lista de conceitos-alvo; o roadmap tem um mapa de cobertura (seção 7).
- `prompts/`: um arquivo por situação; `00-protocolo-git.md` vale para todas.
- `modelos/`: sessão, resumo, matriz, perfil, projeto, ADR e experimento.
- `CHANGELOG.md`: versões do método.

## Como adotar (para outra pessoa)
1. Crie seu próprio repositório (privado, de preferência) e copie `metodo/` para dentro dele. Se este repositório for público, pode usá-lo como template ou fazer fork e depois apagar `progresso/` e `projetos/`.
2. Crie `progresso/` com os modelos: `resumo.md`→`RESUMO.md`, `matriz.md`→`MATRIZ.md`, `perfil.md`→`PERFIL.md`, e arquivos vazios `REVISOES.md`, `BACKLOG.md`, `AMBIENTE.md`, `HISTORICO_DO_PLANO.md`.
3. Crie `projetos/estudos-gerais/sessoes/` e um projeto de laboratório com `projeto-README.md`.
4. Copie o `CLAUDE.md` da raiz deste repositório para a raiz do seu.
5. Abra uma sessão com o repositório acessível ao Claude e cole o prompt de `prompts/01-primeira-sessao.md`.

Requisito para sessões em nuvem: o repositório precisa estar acessível ao Claude com permissão de escrita (Claude GitHub App instalado nele). Sem permissão de push o registro não é salvo; o protocolo manda o tutor avisar isso.

## Duas máquinas, nenhuma perda
O estado vive no `origin/main`. Qualquer sessão começa sincronizando e termina com push confirmado. Regra de ouro: **uma sessão por vez**. A sessão local pode usar o mesmo repositório clonado em cada máquina.

## Compartilhar só o método
Se o repositório for privado, o link da pasta `metodo/` não abre para outras pessoas. Para publicar só esta pasta, extraia o histórico dela para outro repositório:

```bash
git subtree split --prefix=metodo -b metodo-publico
git push git@github.com:<usuario>/<repo-do-metodo>.git metodo-publico:main
```

## Limites
- O tutor é um modelo de linguagem: pode errar e tender a elogiar. Evidência que vale é a que fica no repositório (código, testes, medições, ADRs). Faça bancas (`06-banca.md`) em sessões novas.
- Capacidades, preços e configurações de ferramentas mudam: o tutor deve consultar fontes oficiais atuais.
- Não há promessa de prazo para concluir nem de nível profissional.
