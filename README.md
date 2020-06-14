# Estudo sobre GIT e GITHUB

#### Qual o motivo para utilizar o GIT

- Controlar versões do projeto.
- Organização.
- Branching (As vezes você esta no meio de um desenvolvimento e derrepente surge uma ideia, utilizando GIT você pode criar uma branch e verificar se a ideia é valida, caso não seja basta exlcuir a branch) 

#### Qual o motivo para usar o GITHUB
Existem diversos motivos, porém os mais importantes são:

- Compartilhe seus projetos
- Utilize-o como portifólio
- Integração com Git
- Fazer network e amigos
- Aprenda e colaborar

#### Readme

 - É feito em markdown
   [https://help.github.com/pt/github/writing-on-github/basic-writing-and-formatting-syntax](https://help.github.com/pt/github/writing-on-github/basic-writing-and-formatting-syntax)
   
- Link de editor de README
[https://pandao.github.io/editor.md/en.html](https://pandao.github.io/editor.md/en.html)

#### Abaixo realizei um passo a passo dos comandos básicos

Utilizei o Windows PowerShell

#### Cria uma pasta para realizar os testes GIT

    mkdir manual_git
    cd manual_git
    
  
#### Inicializar um repositório local

    git init

***Resultado***

    Initialized empty Git repository in C:/paginas/trabalhos/git/manual_git/.git/

####  Mostrar o estado atual do repositório

    git status 

***Resultado***

    On branch master
    No commits yet
    nothing to commit (create/copy files and use "git add" to track)

#### Vamos criar um arquivo e verificar novamente com git status
*Este arquivo deve ser criado dentro da pasta onde o repositório foi iniciado. *

    ni index.html 	
	git status

***Resultado***

    On branch master
    No commits yet
    Untracked files:
      (use "git add <file>..." to include in what will be committed)
            index.html
    nothing added to commit but untracked files present (use "git add" to track)

#### Adicionar arquivo para ser comitado

    git add
	git status

***Resultado***

    On branch master    
    No commits yet    
    Changes to be committed:
      (use "git rm --cached <file>..." to unstage)
            new file:   index.html

#### Enviando os arquivos para o repositório local com git commit

    git commit -m "Meu primeiro commit do manual de estudo GIT"

 ***Resultado***

    [master (root-commit) 7fe1451] Meu primeiro commit do manual de estudo GIT
     1 file changed, 0 insertions(+), 0 deletions(-)
     create mode 100644 index.html

#### Vamos verificar como esta o nosso repositório local com git log
*Listei abaixo diversos formas de utilizar o git log, é sempre bom ver o historico da evolução do repositório para entender como a tecnologia foi criada e por quais atualizações ela passou.*

    git log (Exibe o histórico de commit)
    git log --oneline --parents (Para uma representação gráfica baseada em texto do histórico)
    git log --all (Para visualizar o histórico de commits de todas as branches)
    git log --graph (Para uma representação gráfica baseada em texto do histórico)
    git log -p -2 (Exibir histórico com diff das duas últimas alterações)

***Resultado de um git log simples***

    commit 7fe1451ddf00f50a2943622f2c77173559db8037 (HEAD -> master)
    Author: Cleber Costa <cleber.email@gmail.com>
    Date:   Sun Jun 14 11:15:31 2020 -0300
    		Meu primeiro commit do manual de estudo GIT
  
#### Remover um repositório local

    rm -rf .git

#### Verificar as modificações do arquivo com git diff
*Abra o arquivo index.html e adicione a frase Olá Mundo e salve*

    git diff index.html

***Resultado (Nota o sinal de + na linha que foi adicionada ao arquivo index.html)*
**

    diff --git a/index.html b/index.html
    index e69de29..faf65ce 100644
    --- a/index.html
    +++ b/index.html
    @@ -0,0 +1 @@
    +Olá Mundo
    \ No newline at end of file

#### Vamos realizar commit da alteração, para isso precisamos realizar a sequência de comandos abaixo.

    git add index.html
    git commit -m "meu segundo commit, nova linha no arquivo index.html"

***Veja como ficou o histórico com git log***

    commit 66404a8651676514659eebdd35b34ecce3e1b045 (HEAD -> master)
    Author: Cleber Costa <cleber.email@gmail.com>
    Date:   Sun Jun 14 11:26:48 2020 -0300
    
        meu segundo commit, nova linha no arquivo index.html
    
    commit 7fe1451ddf00f50a2943622f2c77173559db8037
    Author: Cleber Costa <cleber.email@gmail.com>
    Date:   Sun Jun 14 11:15:31 2020 -0300
    
        Meu primeiro commit do manual de estudo GIT

#### Caso a descrição do commit não tenha ficado clara, você pode refazer o commit utilizando o comando.

    git commit --amend -m "alterando a observacao do commit"
    
***Resultado***

    [master 0d707bf] alterando a observacao do commit
     Date: Sun Jun 14 11:26:48 2020 -0300
     1 file changed, 1 insertion(+)

***Veja como ficou o historico utilizando novamente git log***

    commit 0d707bf5f91f2ef26437157c83aa5e3ce2673b67 (HEAD -> master)
    Author: Cleber Costa <cleber.email@gmail.com>
    Date:   Sun Jun 14 11:26:48 2020 -0300
    
        alterando a observacao do commit
    
    commit 7fe1451ddf00f50a2943622f2c77173559db8037
    Author: Cleber Costa <cleber.email@gmail.com>
    Date:   Sun Jun 14 11:15:31 2020 -0300
    
        Meu primeiro commit do manual de estudo GIT
  

# GITHUT REPOSITÓRIO REMOTO

Acesse o site [GITHUB](https://github.com/ "GITHUB") e crie uma conta.

Após criar a conta e confirmar a crfiação através do e-mail, clique no sinal de (+) e depois clique em New Repository, sugiro dar o mesmo nome do seu respositório local **manual_git**.

Após criar o repositório o proprio site do GITHUB irá exibir duas opções de ajuda.

*Essas opções devem ser executada através da linha de comando* 

A primeira opção ensinar a criar um novo repositório através da linha de comando (não iremos utilizar esta opção)

    echo "# manual_git" >> README.md
    git init
    git add README.md
    git commit -m "first commit"
    git remote add origin git@github.com:cleberemail/manual_git.git
    git push -u origin master

A segunda opção ensina a enviar um repositório existente a através da linha de comando

    git remote add origin git@github.com: cleberemail / manual_git.git
    git push -u origin master

# PASSO A PASSOA EDITANDO UM ARQUIVO LOCAL, ATUALIZANDO REPOSITÓRIO LOCAL E POR FIM ATUALIZANDO O REPSOSITÓRIO REMOTO

1. Edite o arquivo index.html
2. git add index.html
3. git commit -m "segundo commit"
4. git push

Volte ao GitHub e explore as alterações do seu repositório remoto.


Em breve estarei falando sobre as branch

**Branch**

**git branch** - mostra a lista de branch

**git branch nome_da_nova_branch** - server para criar uma nova branch

**git checkout -b nome_da_nova_branch** - server para criar uma nova branch e ir para esta nova branch

**git checkout nome_da_branch** - serve para trocar de branch

**git branch -D nome_da_branch** - serve para deletar uma branch

**git push origin nome_da_branch** - serve para enviar a nossa branch do repositório local para o repositório remoto

**git commit -a -m <comentário>**
