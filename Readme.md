# Curso de Git e Github
# Professor: Willian Justen
# Plataforma de Estudo: Udemy

Arquivo da aula de Git e Github para iniciantes.

Este é um repositório teste para ensinar como o Git funciona.

Saiba mais em [willianjusten.com.br](http://willianjusten.com.br)

# Ciclo de Vida dos status dos Arquivos

- UNTRACKED = O untracked ou não marcado, é o momento em que o arquivo acabou de ser adicionado no repositório, mas ainda não foi visto pelo git.
- UNMODIFIED = O unmodified ou não modificado, ele existe no git, mas não teve nenhuma modificação em cima dele.
- MODIFIED = O modified ou modificado, acontece após modificarmos algum arquivo unmodified.
- STAGED = O staged ou área, é o momento em que o arquivo vai ficar nessa stage, sendo avisada "o momento em que a versao for fechada, leve esses arquivos".
E assim que for feito o commit, que é criar essa versão, esse hash, todos os arquivos que foram commitados voltarão para o estado de unmodified.

# Comandos Básicos do Git

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

- Para adicionar(commitar) todos os arquivos modificados + a mensagem
$ git commit -am "Insira aqui a sua mensagem"

- Para desfazer, voltar para o estado anterior da edição, um arquivo que esteja no estado de MODIFIED, utilize:
$ git checkout <nome-do-arquivo>

- Para resetar um arquivo que esteja pronto para commitar, ou seja, que foi feito o git add, que esteja no estado de MODIFIED e esteja na STAGE AREA, utilize:
$ git reset HEAD <nome-do-arquivo>

- Para desfazer um commit que subiu errado, por engano, utilize:
$ git reset --soft --mixed --hard

- Ele vai pegar as modificações e vai voltar(matar o commit feito), mas o arquivo estará na stage area pronto para ser commitado novamente
$ git reset --soft <hash-do-commit>

- Ele vai matar o commit, porem ele ira retornar os arquivos para antes do staged, ou seja, para o estado de MODIFIED
$ git reset --mixed <hash-do-commit>

- Ele simplesmente ignora a existencia do commit e tudo o que foi feito nele, ele vai matar tudo o que foi feito no commit
$ git reset --hard <hash-do-commit>

#Observação: O git reset é muito importante, porém é preciso tomar cuidado, pois ele altera o histórico dos commit, por exemplo, se voce ja tinha dado um push em um commit e deseja voltar, resetou com hard, matou o commit e deseja subir de novo, o git irá avisar, "existe uma diferença no que voce quer enviar e no que ele tem, por favor atualize", só será possivel atualizar com --force ou -f, entao o git reset --hard deve ser usado com bastante cuidado, deve-ser optar por essa forma, somente se nao tiver dado um push para o repositorio remoto, porque poderá causar bastante confusao no historico e bastante problemas.

#GitHub - Criando um repositório remoto, passo a passo

…or create a new repository on the command line
echo "# git-course" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/Edufreitass/git-course.git
git push -u origin master

…or push an existing repository from the command line
git remote add origin https://github.com/Edufreitass/git-course.git
git push -u origin master

- Para enviar os commits locais para o repositorio remoto
$ git push origin master

- Para clonar um repositorio do github
$ git clone <endereco-do-repositorio>

#Fork, serve para voce fazer uma copia de outro repositorio para o seu, para ajudar a contribuir com o codigo de outra pessoa, ajustar estruturas, corrigir bugs etc. As mudanças sendo feitas, voce envia um pull request para o outro dev, informando as alteraçoes feitas, os bugs corrigidos etc. Para fazer um fork, basta clicar no botao Fork e aguardar a copia a ser feita. O FORK é diferente do CLONE, o clone voce so consegue fazer para os repositorios que sao meus de fato, se eu nao for dono do repositorio, eu posso ate clonar, mas eu fizer alguma modificaçao, eu nao vou conseguir enviar, porque o repositorio nao é meu e eu nao tenho permissao. Entao quando eu quero fazer alguma modificação em um repositorio que nao é meu, eu faço um FORK e depois subo, faço um pull request.

# O que é um branch?

- É um ponteiro  móvel que leva a um commit.
- O branch default, chamado MASTER, é criado automaticamente após iniciarmos o primeiro repositorio.
- O branch sempre aponta para um commit.
- Podemos ter 2 branch apontando para o mesmo commit.
- Podemos ter 2 branch apontando para commit diferente.

# Por que usar branch?

# Vantagens
- Poder modificar sem alterar o local principal (master)
- Facilmente "desligável", fácil e rápido de apagar
- Múltiplas pessoas trabalhando
- Evita conflitos

- Para criar uma branch
$ git branch <nome-da-branch>

- Para criar uma branch e mudar para ela instantaneamente
$ git checkout -b <nome-da-branch>

- Para listar as branches existentes
$ git branch

- Para mostrar os commits para os quais as branches estao apontando
$ git branch -v

- Para deletar uma branch
$ git branch -D <nome-da-branch>

- Para navegar entre as branch
$ git checkout <nome-da-branch>

- Para editar o comentario do ultimo commit efetuado
$ git commit -m "Nova mensagem" --amend

- Para editar o comentario de um commit antigo de modo interativo
$ git rebase -i

- Seu editor de texto irá iniciar. Troque no texto a palavra pick por reword (ou só r) do commit desejado, exemplo:
pick fef7501 Primeiro commit.
reword 90d77f4 Segundo commit.
pick b82a17f Terceiro commit.

# Rebase 3620553..b82a17f onto 3620553
#
# Commands:
#  p, pick = use commit
#  r, reword = use commit, but edit the commit message
#  e, edit = use commit, but stop for amending
#  s, squash = use commit, but meld into previous commit
#  f, fixup = like "squash", but discard this commit's log message
#  x, exec = run command (the rest of the line) using shell
#
# These lines can be re-ordered; they are executed from top to bottom.
#
# If you remove a line here THAT COMMIT WILL BE LOST.
#
# However, if you remove everything, the rebase will be aborted.
#
# Note that empty commits are commented out

- Salve e o arquivo e feche seu editor. Seu editor será iniciado novamente, dessa vez com a mensagem original do commit a ser modificado. Modifique-a, salve e feche o editor.

- Tanto ao fazer um --amend simples ou um reword com rebase você estará rescrevendo o histórico do git. Isto é, o git gerará um novo SHA1 para o commit. Você não conseguirá, por exemplo, realizar um push pois parte da árvore original de commits não está presente na do seu branch local.

- No caso do rebase todos os commits que fazem parte do rebase serão rescritos (novo SHA1) mesmo se não alterados.

- A não ser que você force o push (git push -f) o git rejeita commits que rescrevem seu histórico.

- A recomendação que eu deixo é: Somente rescreva commits que não estão em outras árvores (commits que ainda não foram em um push). Caso contrário saiba o que está fazendo..

# Unindo branches

# Entendo o Merge

- Se criarmos uma nova branch e fizemos um commit nessa branch, a branch master continuara apontado para ela mesma e essa branch nova apontara para esse novo commit criado.

- Mas ao fazer um MERGE, ou seja, juntar, mesclar todas as modificaçoes feitas na outra branch, um novo commit sera criado, para que tudo volte a funcionar de FORMA LINEAR.

- O Merge é uma operação não destrutiva, ou seja, ele nao vai destruir nenhum commmit, pelo ao contrario, ele vai criar um novo commit para juntar tudo, ele nao estragar, movimentar o historico.

- PERGUNTAS

1. Sempre que um novo branch for criado a base dele será o master?

2. É possível criar um branch apontando para um commit 2 versões mais antiga, por exemplo?

3. Tem alguma forma de saber para qual commit o ponteiro do seu branch está apontando?

- RESPOSTAS

1) A base é criada a partir do branch que você está. Ou seja, se você estiver na branch-A, ao criar a branch-B, ela vai começar da A.

2) Para fazer isso, primeiro faça um git checkout HASH-DESEJADO e então crie um novo branch a partir dali com:

git checkout -b NOME-BRANCH

3) Dá para saber a diferença entre o master e o branch, mas não exatamente qual o commit diretamente.

# Prós:
- Operação não destrutiva

# Contras:
- Commit extra
- Histórico poluído

# Entendo o Rebase

- O rebase move o commit feito em outra branch para o final do ultimo commit da master, para ficar tudo de forma linear.

- Ele pega tudo que ele tiver no branch separado, e coloca no inicio da fila, sempre. É um processo chamado de fast-formard.

- Apos o rebase ser feito, a branch master e a outra branch  estarao apontando para o mesmo commit, evitando fazer aquela arvore confusa que o merge faz.

- Um ponto NEGATIVO do rebase é que, é que a ordem cronologica é perdida. Pois ao fazer rebase, voce pega um commit de outra branch e move ele para o final da fila, ou seja, voce nao esta mais se preocupando se o commit foi feito antes ou depois, simplesmente voce estara colocando ele para o inicio da fila. Usando rebase voce acaba mudando o historico, e essa mudança de historica é preciso tomar bastante cuidado, pois se houver outra pessoa trabalhando na mesma branch, o que pode acontecer é que, ela nao vai conseguir subir as coisas dela, pois dará conflito, o git ira dizer que o historico esta diferente. Em geral é recomendado usar o rebase, sempre quando voce for da pull das modificações, exemplo, git pull --rebase, assim voce nao tera o risco de fazer mudança de historico que nao poderia e que outras pessoas estivessem mexendo e seria prejudicada.

- PERGUNTAS

1. Quando utilizo o rebase, ele está fazendo um merge? Ou seja ele considera meu branch atual com as modificações e mescla com meu master, passando a ser o ultimo commit do master?

- RESPOSTAS

1. Sim, o rebase é uma espécie de "merge", o que muda é que ele sempre tenta colocar suas mudanças ao final de tudo e ao invés de criar um commit só para fazer essa junção, ele coloca o commit ao final do branch de destino e só.

# Prós:
- Evita commits extras
- Histórico linear

# Contras:
- Perde ordem cronológica

- Ele é responsável por guardar modificações que ainda nao foram commitadas, numa pasta, num arquivo, em que eu possa chamar depois que eu achar necessário
$ git stash

- Apos o comando acima, ele irá salvar seu arquivo e mantera ele guardado ate que voce utilize outro comando para aplicar as modificações, sera exibida uma mensagem com a sigla WIP(Working in Progress)

- Para aplicar as modificações guardadas no git stash, utilize:
$ git stash apply

- Exibe a lista de todos os stash que estiver em andamento
$ git stash list

- Ele limpa tudo que estiver no stash, ou seja, ele nao terá mais nenhuma modificação guardada.
$ git stash clear

- Para criar ALIAS(atalhos), como por exemplo, o atalho para git status, utilize:
$ git config --global alias.s status

- Para listar os ALIAS criados, inclusive todas a configurações
$ git config --list

- Para remover um ALIAS criado
$ git config --global --unset alias.nome_do_alias

- PERGUNTA

Qual a função do "--" em "git config --global alias." ou em qualquer outro comando ?
Talvez seja uma pergunta boba, e que poderia ter sido feita em aulas anteriores, mas eu só fiquei curioso sobre a função do "--" agora.
Procurei no stackexchange mas não achei nada que falasse especificamento do "--" .

- RESPOSTA

Opa, isso na realidade é quando você tá passando algum parâmetro para uma função. Existem duas formas:

Um traço ( -  ), onde você passa a versão simplificada do parâmetro se existir. Exemplo: -h (help)
Dois traços ( -- ), onde você passa a versão completa do parâmetro. Exemplo: --help

Nem todos os comandos possuem a opção de passar parâmetros, mas a maioria sim =)

Isso é uma forma comum que existe no terminal/prompt de comando para extender o poder dos comandos.


