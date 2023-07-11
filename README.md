# task01-grupo05

Tarefa 01 da aula de git.

# Create branch dev
1 - Funcionamento: 

O comando "git rebase" combina alterações de um branch em outro, reorganizando o histórico de commits, sendo assim, ele traz as alterações de um branch e as aplica em outro, resultando em um histórico linear. Essa opção é muito útil quando os branches estão "dessincronizados" e você precisa incorporar as alterações de um branch em outro. Porém o rebase deve ser usado com cuidado.

2 - Sintaxe: 

git rebase "branch-de-destino"

3 - Aplicação: 

O git rebase é usado em cenários quando:
- Precisa incorporar alterações de um branch de desenvolvimento em um branch principal (main);
- Precisa atualizar um branch local com as alterações mais recentes de um branch remoto;
- Precisa dividir commits menores e mais específicos antes de enviá-los para revisão;