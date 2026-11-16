# Protocolo de leitura e gravação no repositório

Vale para toda sessão, em nuvem ou local, em qualquer máquina. O repositório é a única fonte de estado: o container da nuvem é descartável e o chat não é memória.

## Princípios

1. **Nada está registrado até estar no `origin/main`.** Editar arquivo no container não é registrar. O tutor só diz "registrado" depois de confirmar o push.
2. **Uma sessão por vez.** Se outra sessão (outra máquina) estiver aberta, ela escreve no mesmo `progresso/` e gera conflito. Encerre uma antes de abrir a outra.
3. **Histórico por git, não por cópia.** Nada de duplicar arquivos "v2", "backup" ou "atualizado". Sessões antigas não são reescritas, só corrigidas com nota datada.
4. **Sem segredos.** Nunca commitar senhas, tokens, chaves, `.env`, dados de clientes ou dados reais. Dados do laboratório são sintéticos.

## No início da sessão

1. Confirmar que está na raiz do repositório: `git rev-parse --show-toplevel`.
2. Sincronizar: `git fetch origin main` e `git status`. Se a branch local não for `main` (comum em sessão em nuvem), seguir em frente mesmo assim, mas o push será `HEAD:main` (ver abaixo). Se houver alterações não commitadas que o tutor não fez, parar e avisar o estudante.
3. Se o clone estiver atrás do `origin/main`: `git pull --ff-only origin main`.
4. Ler, nesta ordem: `progresso/RESUMO.md`, `progresso/REVISOES.md`, a última sessão do projeto ativo (`projetos/<projeto>/sessoes/`), e só então o que o tema exigir (`metodo/ROADMAP.md` no módulo atual, `progresso/MATRIZ.md`). Não ler o histórico inteiro sem necessidade.
5. Criar o arquivo da sessão agora, com status `em andamento` (modelo: `metodo/modelos/sessao.md`), em `projetos/<projeto>/sessoes/AAAA-MM-DD-tema.md`. Se já existir um da mesma data, acrescentar `-2`.

## Durante a sessão: checkpoints

Se a sessão morrer antes do encerramento, só o que foi enviado por push sobrevive. Por isso:

- Ao fechar cada conceito (as 5 perguntas respondidas e classificadas), ao executar cada exercício ou experimento e antes de qualquer pausa longa, atualizar o arquivo da sessão e fazer commit e push.
- Mensagem de commit: `sessao: <tema> — <o que foi registrado>`. Código do laboratório: `lab: <mudança>`. ADR: `adr: <decisão>`.
- Registrar o que **foi demonstrado** separado do que **foi apenas explicado**. Não registrar teste, medição ou resultado que não foi executado.

## No encerramento

Ver `99-encerrar-sessao.md`. A parte de git é:

```bash
git add -A
git status --short            # conferir: só arquivos esperados, nenhum segredo
git commit -m "sessao: <tema> — encerramento"
git push origin HEAD:main
```

- Se o push for rejeitado por não ser fast-forward: `git pull --rebase origin main`, resolver, e repetir o push. Nunca `--force`.
- Em sessão em nuvem a branch local costuma ter outro nome. Para um repositório pessoal de estudo, o destino é sempre `main`, sem pull request.
- **Confirmação obrigatória.** Depois do push, mostrar ao estudante: o hash curto (`git rev-parse --short HEAD`), o resultado do push, os arquivos alterados e a prova de que o remoto está igual: `git ls-remote origin main` deve mostrar o mesmo hash que `git rev-parse HEAD`.
- **Se o push falhar** (permissão, rede, conflito não resolvido): dizer claramente que o registro **não foi salvo**, mostrar o erro, não afirmar que a sessão foi registrada e entregar o conteúdo dos arquivos alterados para o estudante salvar à mão.

## Sessão sem acesso ao repositório (chat comum, voz)

Não há como ler nem gravar. O estudante cola o conteúdo de `progresso/RESUMO.md` e da última sessão. No fim, o tutor entrega o texto completo dos arquivos que mudariam, indicando o caminho de cada um, para o estudante salvar e fazer o commit depois. Marcar a sessão como `registro pendente`.

## Organização dos arquivos

- `progresso/`: estado atual do estudante. Sobrescrever é permitido, o histórico está no git.
- `projetos/<projeto>/sessoes/`: um arquivo por sessão, nunca apagado.
- `projetos/<projeto>/docs/adr|diagramas|experimentos/`: artefatos do projeto.
- Sessão que não pertence a um projeto com código (diagnóstico, teoria, estudo de caso em papel) vai em `projetos/estudos-gerais/`.
- Código do laboratório: `projetos/<projeto>/app/` (ou a pasta que o README do projeto indicar).
