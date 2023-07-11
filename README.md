# task01-grupo05

Tarefa 01 da aula de git.

# Create branch dev

# git cherry-pick
#### _Aplique as alterações introduzidas por alguns commits existentes_


## Funcionamento

Dado um ou mais commits existentes, aplique a alteração que cada um introduz, registrando um novo commit para cada um. Isso requer que a sua árvore de trabalho esteja limpa (nenhuma alteração a partir do commit HEAD).

Quando não é óbvio como aplicar uma alteração, acontece o seguinte:

1. O ramo atual e o ponteiro HEAD permanecem no último commit realizado com sucesso.

2. A referência CHERRY_PICK_HEAD é configurada para apontar para o commit que introduziu a mudança que é difícil de aplicar.

3. Caminhos nos quais a mudança aplicada corretamente são atualizados no arquivo de índice e na sua árvore de trabalho.

4. Para os caminhos conflitantes, o arquivo do índice registra até três versões, conforme descrito na seção "MESCLAGEM REAL" do git-merge[1]. Os arquivos da árvore de trabalho incluirão uma descrição do conflito entre os marcadores de conflito habituais <<<<<<< e >>>>>>>.

5. Nenhuma outra modificação é feita.


## Sintaxe básicas

> git cherry-pick master
Aplique a mudança introduzida pelo commit na ponta do branch master e crie um novo commit com esta mudança.

> git cherry-pick ..master
git cherry-pick ^HEAD master
Aplique as alterações introduzidas por todos os commits que são ancestrais do master, mas não do HEAD para produzir novos commits.

> git cherry-pick master~4 master~2
Aplique as alterações introduzidas pelo quinto e terceiro últimos commits apontados pelo master e crie 2 novos commits com essas mudanças.


## Fontes 

- [Git] -git <https://git-scm.com/docs/git-cherry-pick/pt_BR>
- [markdown-it] - <https://www.markdownguide.org/getting-started/#documentation>