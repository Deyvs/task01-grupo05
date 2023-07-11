# task01-grupo05

Tarefa 01 da aula de git.

### Git Rebase

1 - Funcionamento:

O comando "git rebase" combina alterações de um branch em outro, reorganizando o histórico de commits, sendo assim, ele traz as alterações de um branch e as aplica em outro, resultando em um histórico linear. Essa opção é muito útil quando os branches estão "dessincronizados" e você precisa incorporar as alterações de um branch em outro. Porém o rebase deve ser usado com cuidado.

2 - Sintaxe:

git rebase "branch-de-destino"

3 - Aplicação:

O git rebase é usado em cenários quando:

- Precisa incorporar alterações de um branch de desenvolvimento em um branch principal (main);
- Precisa atualizar um branch local com as alterações mais recentes de um branch remoto;
- Precisa dividir commits menores e mais específicos antes de enviá-los para revisão;

Fonte: https://www.treinaweb.com.br/blog/git-merge-e-git-rebase-quando-usa-los?gclid=CjwKCAjw2K6lBhBXEiwA5RjtCfnqSedzBRJwDBbHbq-06Q2urk84oEL6Tkb2i6LHoMvYxQg7vmALlxoC9NYQAvD_BwE

### Git Cherry Pick

#### _Aplique as alterações introduzidas por alguns commits existentes_

#### Funcionamento

Dado um ou mais commits existentes, aplique a alteração que cada um introduz, registrando um novo commit para cada um. Isso requer que a sua árvore de trabalho esteja limpa (nenhuma alteração a partir do commit HEAD).

Quando não é óbvio como aplicar uma alteração, acontece o seguinte:

1. O ramo atual e o ponteiro HEAD permanecem no último commit realizado com sucesso.

2. A referência CHERRY_PICK_HEAD é configurada para apontar para o commit que introduziu a mudança que é difícil de aplicar.

3. Caminhos nos quais a mudança aplicada corretamente são atualizados no arquivo de índice e na sua árvore de trabalho.

4. Para os caminhos conflitantes, o arquivo do índice registra até três versões, conforme descrito na seção "MESCLAGEM REAL" do git-merge[1]. Os arquivos da árvore de trabalho incluirão uma descrição do conflito entre os marcadores de conflito habituais <<<<<<< e >>>>>>>.

5. Nenhuma outra modificação é feita.

#### Sintaxe básicas

> git cherry-pick master
> Aplique a mudança introduzida pelo commit na ponta do branch master e crie um novo commit com esta mudança.

> git cherry-pick ..master
> git cherry-pick ^HEAD master
> Aplique as alterações introduzidas por todos os commits que são ancestrais do master, mas não do HEAD para produzir novos commits.

> git cherry-pick master~4 master~2
> Aplique as alterações introduzidas pelo quinto e terceiro últimos commits apontados pelo master e crie 2 novos commits com essas mudanças.

#### Fontes

- [Git] -git <https://git-scm.com/docs/git-cherry-pick/pt_BR>
- [markdown-it] - <https://www.markdownguide.org/getting-started/#documentation>

### Git Revert

O comando **git revert** é usado para desfazer as alterações introduzidas por um ou mais commits anteriores. Ele cria um novo commit que reverte as mudanças especificadas, permitindo que você desfaça as mudanças dos commits anteriores sem excluí-los completamente do histórico do Git.

Sintaxe básica do comando **git revert**:

`git revert <commit>`
Onde `commit` representa o identificador do commit que você deseja reverter.

Ele gera automaticamente uma mensagem de commit que descreve a reversão que está sendo aplicada. O commit revertido permanece no histórico, e um novo commit é criado para registrar a reversão.

Ao reverter um commit, o Git analisa as alterações introduzidas por esse commit e as desfaz, restaurando o estado dos arquivos para como estavam antes. Isso pode envolver a adição de linhas removidas, remoção de linhas adicionadas e assim por diante.

Você também pode reverter vários commits de uma vez, especificando vários hashes de commit:

`git revert <commit1> <commit2> <commit3> ...`

Dessa forma, você pode desfazer as alterações de vários commits em uma única operação.

Outros exemplos de uso:

`git revert HEAD~3`
Desfaz as alterações especificadas pelo quarto commit anterior no HEAD e cria um novo commit com as alterações revertidas.

`git revert -n master~5..master~2`
Desfaz as alterações feitas pelos commits do quinto commit anterior no master (incluído) até o terceiro commit anterior no master (incluído), mas não cria nenhum commit com as alterações revertidas. A reversão apenas modifica a árvore de trabalho e o índice.

É importante lembrar que o comando **git revert** cria novos commits para desfazer as alterações, preservando assim a integridade do histórico do Git. Esses novos commits podem ser enviados para um repositório remoto, assim como qualquer outro commit.

### Git Squash

O `git squash` é usado para combinar vários commits relacionados em um único commit. Ele permite reescrever a história do repositório Git, tornando-a mais organizada e coerente.

O squash é útil quando foram feitos vários commits pequenos e deseja-se consolidá-los em um único commit significativo antes de enviá-lo para um branch principal ou compartilhá-lo com outras pessoas.

A sintaxe básica para executar o git squash é a seguinte:

```bash
git rebase -i HEAD~[n]
```

Onde [n] é o número de commits que se deseja combinar.

Isso abrirá um editor de texto com uma lista dos commits selecionados, conforme pode-se ver abaixo:

```
pick <commit-hash> <commit-message>
pick <commit-hash> <commit-message>
pick <commit-hash> <commit-message>
```

Para combinar commits, deve-se substituir "pick" por "squash" ou simplesmente "s" nos commits que se deseja unir.

Após salvar e fechar o arquivo, o Git irá realizar o squash dos commits selecionados. Isso abrirá outro editor de texto onde pode-se editar a mensagem do commit resultante, se desejar. Basta editar a mensagem, salvar e fechar o arquivo para concluir o squash.
