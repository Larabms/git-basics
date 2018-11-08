# Git basics

## Criando um novo repositório

Primeiramente, crie uma pasta, entre nela e inicialize o repositório.

```
mkdir git-basics
cd git-basics
git init
```
Crie uma arquivo *markdown* para *readme*.

`touch README.md`

## Se identificando

Indique seu nome e e-mail. O parâmetro `--global` é opicional, para se identificar em todos os repositórios, ao invés de apenas no atual.

```
git config --global user.name "Ygor Canalli"
git config --global user.email "ygor.canalli@gmail.com"
```
## *Staging area*

O staging area é a área de preparação de um *commit*. Utilizando seu editor de texto favorito, adicione algum conteúdo ao arquivo `README.md`. Para um exemplo de uso da linguagem *markdown*, o fonte deste tutorial.

### Verificando o *staging area*

Você poderá verificar o que foi alterado, o que será *commitado* e o que não será. Para isso, utilize o comando

```
git status
```

### Adicionando ao *staging area*

Verificando o *status* você perceberá que o *git* detecta a criação do arquivo `README.md`, porém consta como um alteração que não será *commitada*. Para que o arquivo seja incluído no próximo *commit*, utilize o comando

```
git add README.md
```

### Removendo do *staging area*

Para remover um arquivo do *staging area*, ou seja, não incluí-lo no próximo *commit*, utilize o comando

```
git checkout -- <meu-arquivo>
```

## *Commitando* alterações

Um *commit* é uma operação irreversível de atualização do repositório. Sendo assim, não é possível desfazer um commit, embora seja possível reverter o repositório para a versão anterior e prosseguir a partir dela, porém o *commit* em questão jamais deixará de fazer parte do histórico. Por isso, existe um estado intermediário, o *stating area*. É uma boa prática que cada *commit* seja uma alteração atômica, que diga respeito a somente uma coisa, para que seje possível rastrear cada modificação que o repositório passou. Para um exemplo, verifique o exemplo deste tutorial. É sempre aconselhável verificar o *staging area* antes de realizar um *commit*. Para *commitar* as alterações indicadas utilizamos o comando

```
git commit -m 'minha mensagem'
```

Também é possível realizar um commit sem indicar uma mensagem, neste caso será aberto um editor (em geral o `vi`) onde você deverá deixar uma mensagem que indique o que foi alterado no commit em questão. Após salvar e sair do editor, o git procederá à criação do *commit*.

## Repositórios remotos

O git permite que você tenha um repositório remoto, para onde você pode enviar alterações e recuperá-las novamente no futuro. Em geral utilizamos como repositórios remotos serviços de nuvem como GitHub, GitLab e BitBucket.

### Adicionando um repositório remoto

Para adicionar um repositório remoto, precisamos dar um nome a ele, que usualmente é `origin` e a URL remota. O exemplo abaixo adiciona um repositório remoto com o endereço deste tutorial. Você poderá fazer com qualquer repositório remoto que tenha criado.

```
git remote add origin https://github.com/ygorcanalli/git-basics.git

```

### Enviando alterações com o comando _push_

O comando _push_ envia seus commits para o repositório remoto. A primeira vez que utilizamos este comando, precisamos indicar para onde serão enviadas as alterações. Utilizamos o comando abaixo para enviar para o remote chamado `origin` no branch `master` (falaremos sobre branches mais adiante):

```
git push -u origin master
```

Tendo configurado o destino do remote, nas próximas vezes basta utilizar o comando `git push`, e seus commits serão enviados. Você pode alterar o destino novamente utilizando o comando anterior.
