#Curso de Git e Github
#Professor: Willian Justen
#Plataforma de Estudo: Udemy

Arquivo da aula de Git e Github para iniciantes.

Este é um repositório teste para ensinar como o Git funciona.

Saiba mais em [willianjusten.com.br](http://willianjusten.com.br)

#Ciclo de Vida dos status dos Arquivos

- UNTRACKED = O untracked ou não marcado, é o momento em que o arquivo acabou de ser adicionado no repositório, mas ainda não foi visto pelo git.
- UNMODIFIED = O unmodified ou não modificado, ele existe no git, mas não teve nenhuma modificação em cima dele.
- MODIFIED = O modified ou modificado, acontece após modificarmos algum arquivo unmodified.
- STAGED = O staged ou área, é o momento em que o arquivo vai ficar nessa stage, sendo avisada "o momento em que a versao for fechada, leve esses arquivos".
E assim que for feito o commit, que é criar essa versão, esse hash, todos os arquivos que foram commitados voltarão para o estado de unmodified.

#Comandos Básicos do Git

- Configurar nome do usuario
$ git config --global user.name "insira-seu-nome"

- Configurar email do usuario
$ git config --global user.email "insira-seu-email"

- Configurar editor principal do git
$ git config --global core.edito <nome-do-editor>

- Visualizar a config do nome do usuario
$ git config user.name

- Visualizar a config do email do usuario
$ git config user.email

- Visualizar todas as configurações
$ git config --list

- Criar uma pasta através do terminal
$ mkdir <nome-da-pasta>

- Entrar na pasta criada
$ cd <nome-da-pasta>

- Inicializar repositório do Git
$ git init

- Para listar arquivos
$ ls

- Para listar arquivos, incluindo os ocultos
$ ls -la

- Para editar um arquivo atraves do terminal, utilizando VIM ou VI
$ vim <nome-do-arquivo>

- Para entrar no modo de inserçao(edição) do arquivo
$ Pressione o INSERT

- Para salvar o arquivo
$ Pressione o ESC, logo após pressione o SHIFT + ":" e digite "w", que é igual a escrever e "q" para sair, ficando assim ":wq"

- Para reportar(exibir) o estado atual do repositório
$ git status

- Para adicionar o arquivo na stage area
$ git add <nome-do-arquivo>

- Para commitar, ou seja, criar uma imagem(snapshot), uma versão dos arquivos que estão na stage area
$ git commit -m "Insira aqui a sua mensagem, é uma boa prática inserir informações pertinentes, para que a mensagem seja de fácil entendimento"

- Para ver o histórico, quais foram as versões, quais arquivos mudaram, utilize:
$ git log

- Exibe os caminhos das branches, quais foram os merges, quais tags foram geradas etc
$ git log --decorate

- Para filtrar pelo autor do commit
$ git log --author="Insira o nome"

- Exibe em ordem alfabética, quais foram os autores, quantos commits fizeram e quais foram
$ git shortlog

- Para exibir somente a quantidade de commits e o autor
$ git shortlog -sn

- Exibe em forma gráfica, o que esta acontecendo com as branches e as versões
$ git log --graph

- Para identificar, o que aconteceu no commit, o que foi adicionado, o que não foi etc, usamos a hash do commit
$ git show <hash-do-commit>

- Para exibir as mudanças antes de serem enviadas, antes de salvar a versao e fazer o commit
$ git diff

- Exibe somente o nome do arquivo que foi modificado
$ git diff --name-only

- Para adicionar e commitar um arquivo com um unico comando
$ git commit -am "Insira aqui a sua mensagem"
