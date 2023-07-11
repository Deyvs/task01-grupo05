# task01-grupo05
Tarefa 01 da aula de git.

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