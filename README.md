# git-guide
*Guide's Git with some commands line daily used for developers which help us strongest.*

## Configurações iniciais
### Configuração do nome de usuário e e-mail
> Configura o nome do usuário e seu e-mail para serem utilizados no Git local.

```
git config user.name "[nome_usuario]"
git config user.email "[email]"
```

## Repositórios locais
### Inicialização de um repositório local
> Inicializa um diretório como um repositório local.

```
git init
```

### git status
> Exibe o status dos arquivos que estão no diretório do repositório.

```
git status
```

### git ls-files
> Exibe os arquivos que pertencem ao repositório e são monitorados pelo Git.

```
git ls-files
```

### git add
> Adiciona arquivos novos ou modificados para serem monitorados e versionados pelo Git.
> É possível adicionar um ou mais de um arquivo, todos ou os que satisfaçam uma condição.

> Adiciona o arquivo index.html

```
git add index.html
```

> adiciona os arquivos index.html e estilo.css

```
git add index.html estilo.css
```

> Adiciona todos os arquivos do repositório local

```
git add .
```

> Adiciona todos os arquivo com extensão JAVA

```
git add *.java
```

## Repositórios remotos
### git clone
> Permite clonar um repositório remoto para o local. Traz todas as alterações no repositório, como commits, tags e branchs.

```
git clone git://github.com/[nome_usuario]/[nome_repositorio].git
```

> Clona o repositório remoto **git-guide.git** do usuário **barcanjo**

```
git clone git://github.com/barcanjo/git-guide.git
```

### git remote
> Lista os repositórios remotos do seu repositório local.

```
git remote
git remote -v
```

### git remote add
> Configura um repositório remoto no seu repositório local, para envio e recebimento de alterações.

```
git remote add [alias_do_repositorio] [uri_do_repositorio]
git remote add origin https://github.com/jcfonsecagit/propostas_homepage.git
```

### git remote remove
> Para excluirmos um repositório remoto do repositório local, ou seja, não ter mais um repositório central para onde enviar e receber as alterações, podemos utilizar o parâmetro **remove**.

```
git remote remove [alias_repositorio_remoto]
```

## Tags
### git tag
> Exibe todas as tags do repositório.

```
git tag
```

## Controle de alterações
### git commit
> Cria uma commit com a mensagem "Início do projeto"

```
git commit -m "Início do projeto"
```

### git diff
> Mostra as diferenças entre commits e tags.
> No exemplo são exibidas as diferenças entre as tags v0.1 e v0.2, levando em considereção que a tag v0.2 é a mais atualizada.

```
git diff v0.1 v0.2
```

### git blame
> Permite consultar quem foi o autor ou modificador de cada linha de um arquivo.

```
git blame index.html
```

### git log
> Permite visualizar todas os commits do repositório.

```
git log
```

### git whatchanged
> Permite visualizar todas as alterações do repositório, incluindo os arquivos modificados.

```
git whatchanged
```

### git whatchanged -p
> Permite visualizar todas as alterações do repostirório, incluindo os arquivos e as linhas de código modificadas.

```
git whatchanged -p
```

## Sincronização do repositório remoto
### git push
> Envia todas as alterações do repositório local para o respositório remoto.

```
git push [alias_repositorio_remoto] [branch_repositorio_remoto]
```

> Envia todas as alterações para o respositório remoto chamado **origin** na branch **master**

```
git push origin master
```

> Podemos indicar o caminho (track) da branch remota para a nossa branch local. Isso pode ser feito no instante em que criamos a branch remota através da opção "-u".

```
git push -u [alias_repositorio_remoto] [branch_repositorio_remoto]
```

### git pull
> Recebe as alterações de um repositório remoto para um repositório local.

```
git pull [alias_repositorio_remoto] [branch_repositorio_remoto]
```

> Recebe as alterações do repositório remoto configurado com o nome **origin** e as envia para a branc **master**

```
git pull origin master
```

## Branch
### git branch
> Nos fornece todas as branches criadas na máquina. Ele também possibilita visualizar qual a branch que estamos atualmente através de um "*" que precede o nome da branch atual.

```
git branch
```

### git branch [nome_branch]
> Utilizamos o comando **git branch**, passando como opção o nome da branch que desejamos criar.

```
git branch [nome_branch]
```

### git checkout
> Se quisermos alterar o projeto numa outra branch isto é feito através do comando **git checkout** passando o nome da branch para a qual desejamos mudar.

```
git checkout [nome_branch]
```

### git checkout -b
> Podemos criar uma nova a branch e imediatamente utilizá-la através da opção **-b** passado ao comando git branch.

```
git branch -b [nome_nova_branch]
```

### git checkout -t
> Realizando o comando **git checkout -t**, uma nova branch local chamada design é criada, muda-se para essa branch, copiamos todo o conteúdo da branch remota design do repositório referente ao origin e trackeamos as duas branches.

```
git checkout -t [alias_repositorio_remoto]/[branch_repositorio_remoto]
```

### git branch -r
> Podemos visualizar as branches já existentes em um repositório remoto através da opção **-r** passado ao comando git branch.

```
git branch -r
```

### git branch -t
> Uma vez visto as branches remotas, como copiar uma delas para a máquina local? Isso é feito passando o nome do repositório e da branch remota ao comando git branch, além de indicar o nome da branch que será criada. Mais uma vez, temos o problema de indicar o caminho entre as branches. Para este caso, a opção **-t** resolve.

```
git branch -t [nome_branch] [alias_repositorio_remoto]/[nome_branch_remota]
```

### git branche -d
> Para excluir uma branch local utilizamos o parâmetro **-d**

```
git branch -d [nome_branch_local]
```

### git branch -a
> Nos fornece uma opção ao comando **git branch** para listar tanto as branches locais quanto as remotas.

```
git branch -a
```
