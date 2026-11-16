# Encerrar a sessão e registrar

## Texto para colar

> Encerrar. Siga `metodo/prompts/99-encerrar-sessao.md`.

## Instruções ao tutor

1. Pergunte o **tempo estudado** (uma pergunta, espere a resposta).
2. Dê o **veredito honesto** em três linhas: o que o estudante demonstrou de fato, a lacuna mais séria e o que ele precisa fazer para fechá-la. Sem suavizar.
3. Complete o arquivo da sessão (`projetos/<projeto>/sessoes/AAAA-MM-DD-tema.md`) seguindo `metodo/modelos/sessao.md`: tempo, classificação das respostas, o que foi apenas explicado versus demonstrado, trade-offs que o estudante ignorou, ajuda utilizada, evidências reais (arquivos, comandos, resultados), verificações não executadas, estado anterior → novo estado e a revisão agendada. Mude o status para `concluída` (ou `incompleta`, dizendo onde parou). Não invente testes, resultados ou domínio.
4. Atualize em `progresso/`:
   - `RESUMO.md`: estado, tópico ativo, próximo passo específico. Sem respostas das perguntas de revisão.
   - `MATRIZ.md`: só as competências com evidência nova, com estado anterior → novo e justificativa.
   - `REVISOES.md`: novas perguntas de revisão, sem gabarito, com data prevista; marque as revisões feitas e o resultado.
   - `BACKLOG.md`: dúvidas laterais e pendências; marque as concluídas sem apagá-las.
5. Se o método mudou, registre em `metodo/CHANGELOG.md` com versão, data e motivo. Se o plano pessoal mudou, registre em `progresso/HISTORICO_DO_PLANO.md`.
6. Faça commit e push conforme `00-protocolo-git.md` e **mostre a confirmação** (hash, resultado do push, arquivos, `ls-remote` igual ao HEAD). Se o push falhar, diga que a sessão não foi registrada e entregue o conteúdo dos arquivos.
7. Termine com o próximo passo exato e as perguntas de revisão pendentes (sem respostas).
