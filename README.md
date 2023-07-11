# task01-grupo05

Tarefa 01 da aula de git.

### Git Revert

O comando **git revert** é usado para desfazer as alterações introduzidas por um ou mais commits anteriores. Ele cria um novo commit que reverte as mudanças especificadas, permitindo que você desfaça as mudanças dos commits anteriores sem excluí-los completamente do histórico do Git.

Sintaxe básica do comando **git revert**:

```git revert <commit>```
Onde ```commit``` representa o identificador do commit que você deseja reverter.

Ele gera automaticamente uma mensagem de commit que descreve a reversão que está sendo aplicada. O commit revertido permanece no histórico, e um novo commit é criado para registrar a reversão.

Ao reverter um commit, o Git analisa as alterações introduzidas por esse commit e as desfaz, restaurando o estado dos arquivos para como estavam antes. Isso pode envolver a adição de linhas removidas, remoção de linhas adicionadas e assim por diante.

Você também pode reverter vários commits de uma vez, especificando vários hashes de commit:

```git revert <commit1> <commit2> <commit3> ...```

Dessa forma, você pode desfazer as alterações de vários commits em uma única operação.

Outros exemplos de uso:

```git revert HEAD~3```
Desfaz as alterações especificadas pelo quarto commit anterior no HEAD e cria um novo commit com as alterações revertidas.

```git revert -n master~5..master~2```
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

