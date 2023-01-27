# Lista de comandos úteis no git

## Criar uma "apelido" para um ou mais comandos
Criar uma alias para o comando status
````
git config --global alias.st status
````
Obs.: Caso queira deixar o atalho restrito a um projeto basta tirar a opção “global” do comando

Para executar o novo comando, basta:
````
git st
````

## Criar aliases que usam comandos do Shell
Dá para usar comandos do shell nos aliases criados. Com essa estratégia dá para ter comandos que só daria para fazer no Gitbash direto no prompt do DOS.
Exemplo:
````
git config --global alias.ls "! ls"
````
Nesse exemplo foi criado um comando git ls, que lista arquivos, como no Linux

## Criar um atalho para mais de um comando
Este exemplo cria um alias git ac que executa um add e um commit
````
git config --global alias.ac '!git add -A && git commit'
````

## Comando para listar os aliases criados
### No Windows
````
git config --list | findstr alias
````

### No Linux ou no Gitbash
````
git config --list | grep alias
````

## Comando para remover um alias
````
git config --global --unset alias.st
````

## Comando para renomear um branch local
````
git branch -m feature/002 feature/003
````


## Sequência de comandos para criar um Hotfix no Gitlab

### Criação do branch
````
git checkout main
git pull
git flow hotfix start 1.26.45.7
````


## 
````
git flow init -d
````









Estes materiais são resumos do documento criado por Lucas Salvador em 11/05/2020:

[Simplificando o git com git alias](https://medium.com/trainingcenter/simplificando-o-git-com-git-alias-de488094855f)

[Git alias - seja rápido, seja breve!](https://gist.github.com/kelvinst/331aff32508e2517afbd)

### Função do Rômulo
````
git config --global alias.clonar "!f() { git clone http://172.16.101.7/bimer/web/on-premises/v1/wisepcp.git WPCP-${2-0000} && cd $(pwd)/WPCP-${2-0000}/ && git flow init && git pull && git flow ${1-feature} start WPCP-${2-0000}; }; f"
````
