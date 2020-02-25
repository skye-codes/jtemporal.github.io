---
title: Publishing your own website with Jekyll
layout: post
image: "/images/tutorial.png"
date: 2018-01-07T10:00:00.000+00:00
tags:
- english
- tutorial
- jekyll
- ruby
- terminal
- site
- github pages
- github
- github
comments: true
description: Learn to get your website up and running using the terminal, jekyll and
  other tools.

---
***

_Author note:_ [Siga esse tutorial em Português.](https://jtemporal.com/do-tema-ao-ar/)

***

In a [pro tip, I talked about how using Jekyll](https://jtemporal.com/choosing-a-jekyll-theme/) is an excellent idea to get your site online. In this tutorial, we will deploy a website using GitHub, Jekyll, and the terminal.

## Choosing a theme

The first step is to go to [Jekyll Themes](http://jekyllthemes.org/) and choose a theme you like. For this tutorial, I choose [Fresh](http://jekyllthemes.org/themes/fresh/), a blog theme, with not only the posts listing but also some extra pages like "About" and "Contact". It's responsive, which is a significant feature if you take into account that much content today is consumed via mobile devices. Take a look at Fresh's Demo:
![fresh demo](https://github.com/artemsheludko/fresh/blob/master/assets/img/fresh.gif?raw=true)

## Preparing the environment

You'll need to install (if you haven't already) the following list of requirements:

* Ruby
* Jekyll
* Git
* Gem

Keep in mind that the next steps are tailored for my operating system (Elementary OS), so you may need to adapt those steps for your OS.

_Edit:_ If you are following this tutorial on macOS Catalina, feel free to skip the installation steps below.

Installing our requirements:

``` console
$ sudo apt install git
$ sudo apt install ruby-full
$ sudo apt install rubygems       # ou rubygems-integration
$ gem install jekyll bundler
```

Why do we need all this?

1. **git**: We'll use [GitHub](http://github.com/) to host our site, and we need git to do that;
2. **ruby-full**: A more stable old version of Ruby. Since Jekyll is a Ruby-built tool, we need it installed on your computer for Jekyll to work;
3. **rubygems**: Just like Python's pip and Node's npm, there is gem for Ruby dependencies. It's a package manager, and a necessary requirement it to install Jekyll and the other packages for Fresh to run;
4. **jekyll**: The static site generator;
5. **bundler**: Is the "inception" of packages, it is a package that controls other packages, it controls versions of packages and their dependencies on projects.

## Downloading the theme

For those who are already used to Git, I think this part will be quite straightforward. The [link to the repository is this one](https://github.com/artemsheludko/fresh). For those who are not used the steps are these:

``` console
$ git clone https://github.com/artemsheludko/fresh.git
```

_Note_: Here, I prefer to clone on purpose, but for those who are more intimate with Git and its processes, you can go ahead and fork it. In this tutorial, I'm cloning it because sometimes, when opening a pull request, you might end up opening one to the original repository instead of your own copy. To avoid that, and make things easier for git beginners, let's go with cloning.

## Running the project

After cloning is time to run this, right?! The steps below will serve your site locally:

``` console
$ cd fresh
$ bundle install
$ bundle exec jekyll serve
```

<br>
<center>
<img src="https://i.imgur.com/Cxh1nNO.png" alt="Terminal running fresh locally">
</center>

_Note:_ if by any chance you don't have a Gemfile in the theme you picked, the `bundle install` step won't work, I recommend you read [this Gemfile pro-tip](https://jtemporal.com/rb-project-dep-gemfile/) to understand a little bit more about Gemfiles and how to create your own.

Now go to your favorite browser and go to `http://localhost:4000/fresh/`. Cool, huh?! 🎉

All right, let's understand what we just did:

1. **bundle install**: This command will look in your Gemfile and Gemfile.lock for package names and versions to install the necessary dependencies to run the project, that's why if you don't have a Gemfile this step doesn't work;
2. **bundle exec jekyll serve**: This is the command runs the Jekyll server allowing you to see your site on your browser. Every time you run this command, the site is built.

To stop the server just hit `Ctrl + c`, you will need the server offline for the configuration steps.

## Configuration file

Let's start with the configuration. Most themes rely on the configuration file to "fill the blanks" on the site. This makes the templates easily adaptable; you just have to change the `_config.yml` to change things such as the site title, author, and so on.

Open the `_config.yml` file in your favorite editor, and let's update it. To see changes to the site, whenever you change `_config.yml`, you'll need to stop and restart the Jekyll server. Since the server relies on the configuration file to build everything, this is the only file that you need to restart the server every time you want to see the changes you made take place.

### Profile Info

In this part goes the initial information:

* The title (`title`): The name that appears when you open a tab in the browser;
* Name (`name`): usually something descriptive of what your blog is about;      
* The description (`description`): which goes inside the HTML and when someone shares your blog is this description that appears, it also helps to put your site in search results like Google and DuckDuckGo;      
* The page (`baseurl`): From which link your site is served, the path to your home      
* The URL (`url`): This is where the domain goes, may it be the one that GitHub Pages makes available (username.github.io) or one that you will buy (as is my case here).

Edit this first block for something like this:

``` yml
# Profile information
name: Contos # Tales
title: Um blog com Jekyll # a jekyll blog
description: >
    Uma coleção de contos
    # A collection of tales
permalink: ':title/'
baseurl: "/blogfresh" # the subpath of your site, e.g. /blog
url: "http://jtemporal.com" # the base hostname & protocol for your site, e.g. http://example.com
```

Execute novamente o comando do servidor `bundle exec jekyll serve`. Dessa vez o site que você precisa acessar mudou pois mudamos o `baseurl` para `/blogfresh`. Agora acesse `http://localhost:4000/blogfresh/` para ver as mudanças. Com essas alterações no `_config.yml` o site deve estar parecido com isso:

![blog alterado profile info](https://i.imgur.com/kut6tWL.png)

### Social

É aqui que vem os links para suas redes sociais. As que você não quiser deixar disponível basta não preencher. Eu vou ensinar como esconder os botões para as redes sociais que não tiverem um valor aqui em outro blog post, por enquanto vamos colocar apenas uma delas:

``` yml
# Social
facebook: #Add your Facebook
twitter: #Add your Twitter
google-plus: #Add your Google+
github: @jtemporal
```

Infelizmente esse tema não "esconde" os botões para as redes sociais que não possuem um usuário/link válido.

### Formulário de contato

Se você quiser que as pessoas entrem em contato com você pelo formulário de contato do site é só remover o comentário e colocar o seu e-mail no lugar de `your-email@domain.com`. Como eu não curto receber e-mail deixei comentado mesmo `¯\_(ツ)_/¯`.

``` yml
# Contact form
email: #your-email@domain.com
```

### Comentários

Essa uma parte legal, comentários nos seus posts! Se você não conhece o [Disqus](http://disqus.com/) ainda, ele nada mais é do que uma plataforma que ajuda a aumentar o envolvimento nos seus sites. Ele permite de forma relativamente fácil que pessoas comentem no seu blog. Crie uma conta e coloque o seu identficador aqui:

``` yml
# Comments
discus-identifier: jtemporal
```

Após reiniciar o servidor para que as mudanças do arquivo de configuração façam efeito, você deve ter uma área paracida com a da imagem abaixo no fim de um post:

![area de comentarios disqus](https://i.imgur.com/3Lc0O9q.png)

### Paginação

É nessa seção que você define quantos posts aparecem por página no seu site:

* Posts por página (`paginate`): quantos blog posts aparecem em cada página;
* URL de uma página (`paginate_path`): essa variável define como vão ser geradas as URLs de uma página específica, por exemplo, `blog/page2/index.html`.

``` yml
# Paginate
paginate: 5
paginate_path: /page:num/
```

### Configurações de build

Aqui você não vai precisar mudar nada, mas é bom entender o que tá rolando né?!

* Renderizador de markdown (`markdown`): aqui você pode escolher que renderizador de Markdown usar. O padrão é o `kramdown`;
* Gems necessárias para esse tema (`gems`): aqui vai uma lista de gems que precisam ser instaladas;
* Diretórios e arquivos para exclusão (`exclude`): esses são arquivos e diretórios para serem desconsiderados na hora de gerar as páginas do site;
* Diretórios e arquivos para inclusão (`include`): esses são arquivos e diretórios para serem considerados na hora de gerar as páginas do site, se você quiser servir algum arquivo a partir do seu site você deve incluir ele nessa lista.

``` yml
# Build settings
markdown: kramdown
gems:
  - jekyll-feed
  - jekyll-paginate
exclude:
  - Gemfile
  - Gemfile.lock
include: [_pages]
```

Ao terminar de arrumar o `_config.yml` lembre-se de commitar as mudanças! Vou assumir que você fez isso a cada passo daqui pra frente ;)

## Posts

O Fresh, assim como todos os outros temas disponíveis trazem exemplos de posts. A primeira coisa eu você vai notar ao abrir um deles no editor de texto é que ele tem uma espécie de cabeçalho conhecido como [Front Matter](https://jekyllrb.com/docs/frontmatter/). Lá são definidos coisas como o layout do post, o título, a data de publicação e por aí vai...

### Entendendo o Front Matter

* `layout`: O Jekyll enxerga todas as páginas do blog como um blog post que ele precisa renderizar, inclusive as páginas _About_, _Contact_ e _Home_ então a tag layout é utilizada para diferenciar a renderização, as opções são: post ou default;
* `title`: O título da postagem;
* `date`: A data e hora da publicação no formato `AAAA-MM-DD HH:MM:SS` ainda é possível passar o fuso horário da publicação caso queira usando esse campo;
* `description`: Cada blogpost pode ter um paragrafo de sinopse na listagem de posts. É aqui que essa sinopse vai.

#### Primeiro post

Vamos criar um post novo do zero e colocar no site. Crie um arquivo dentro do diretório `_posts`:

``` console
$ touch _posts/2018-01-07-ola-mundo.md
```

É costumeiro usar o padrão `AAAA-MM-DD-nome-do-post.md` nos nomes dos arquivos. Lembre-se que é apartir do nome do arquivo que vão ser geradas as URLs para cada post.

Abra o arquivo que acabamos de criar, cole o seguinte Front Matter e conteudo:

``` plaintext
---
layout: post
title:  "Olá mundo"
date:   2018-01-07 00:00:00
description: Primeiro blogpost
---

Olá mundo!
```

Se o servidor Jekyll não estiver rodando, inicie ele. Se já estiver rodando ao criar e salvar o arquivo dê um tempinho para que ele possa gerar o HTML desse novo post. Vá até o navegador e recarregue a página. Et voilà!

![Primeiro blogpost](https://i.imgur.com/z528dqZ.png)

Commite esse arquivo.

## Publicando o site

Bom, como lá no começo fizemos um `git clone` todas as ligações desse repositório estão com o repositório inicial. Como assim? Os repositrórios Git fazem comunicação com o GitHub (ou qualquer outra rede) por meio do que chamamos de `remote`. Não vou entrar em detalhes do funcionamento disso nesse post mas você pode ler mais sobre isso [na documentação oficial do Git](https://git-scm.com/docs/git-remote).

Aqui nós vamos fazer alguns passos, alguns deles pelo site do GitHub, outros no terminal mesmo.

### Terminal: segunda fase

Os comandos do terminal acontecem em duas fases, a primeira é essa aqui que consiste em renomear o `remote` do repositório original para `upstream` isso é útil pois você pode utilizar o `upstream` para atualizar o código do seu tema.

``` console
$ git remote rename origin upstream
```

Depois disso vamos ao GitHub.

### GitHub

Aqui, assumindo que você já possui uma conta no GitHub, [caso não tenha é só criar, é rapidinho](https://github.com/join?source=header-home). Para os passos a seguir eu vou mostrar duas versões, uma para quem **já tem um site** publicado (como eu) e uma para quem está publicando um site pela **primeira vez**.

#### Meu primeiro site

1. [Criar um repositório novo](https://github.com/new) como esse é o seu primeiro site, esse repositório precisa ter um nome especial seguindo o padrão `meu-nome-de-usuario.github.io`:
   ![foto do repo username.github.io](https://i.imgur.com/2vOk9OJ.png)
2. Copiar as instruções que vem na área `...or push an existing repository from the command line`:
   ![instruçoes de remote primeiro site](https://i.imgur.com/me5fQgM.png)

#### Já tenho um site

Pra quem já tem um site no GitHub, esse novo site vai ser uma do seu site atual. Por exemplo, eu tenho esse site aqui `http://jtemporal.com` e esse blog novo vai virar `http://jtemporal.com/blog`. O mesmo padrão se repete se você não tiver um domínio personalizado, seu site ficará algo tipo `https://jtemporal/github.io/blogfresh`. Vamos lá:

1. [Criar um repositório novo](https://github.com/new): só seguir a imagem abaixo, você não precisa configurar mais nada, e lembrete que aqui eu dei o mesmo nome que está no meu `url` lá no `_config.yml`:
   ![criando novo repo no gihub](https://i.imgur.com/EX0HGFq.png)
2. Copiar as instruções que vem na área `...or push an existing repository from the command line`:
   ![instruçoes de remote](https://i.imgur.com/kcFTVrk.png)

### Terminal: segunda fase

A segunda fase do terminal consiste em mandar o nosso código para o GitHub e colocar o site no ar de fato. Vamos lá que tá quase:

``` console
$ git remote add origin git@github.com:jtemporal/blogfresh.git
# ou: git remote add origin git@github.com:jtemporal/jtemporal.github.io.git
$ git push -u origin master
```

### GitHub: o retorno

Depois de mandar o código para o GitHub agora precisamos configurar o site, simbora!
Vamos começar indo para aba de `Settings` do repositório:
![aba de configurações](https://i.imgur.com/f3rxngC.png)

Descendo nessa página de configurações encontramos a seção referente ao GitHub Pages. É essa seção que acaba publicando o site:
![seção GitHub Pages](https://i.imgur.com/7brruPu.png)

Quando selecionado `None` na área de Source, o GitHub Pages está desativado. Então vamos selecionar um ramo para publicar nosso site a partir dele, nesse caso o ramo será o `master` mesmo:
![selecionando o ramo de publicacao](https://i.imgur.com/fFh4CN0.png)

E agora clicar em `Save`:
![clique em save](https://i.imgur.com/60Li2Ww.png)

E o resultado será algo parecido com:
![site publicado](https://i.imgur.com/BRM01sH.png)

É só acessar o link do site agora que deve estar lá bonitão ;)

E agora? Bem agora você pode começar a escrever outros posts e ir commitando eles. Todo commit/pull request para a master vai automagicamente executar os passos de build do site e deploy. Happy blogging!

***

## Links e considerações

* Existem outras formas de instalar o Ruby na sua máquina, encontre elas estão listadas na [documentação do Ruby em português](https://www.ruby-lang.org/pt/documentation/installation/).
* [Bundler](http://bundler.io/).
* Eu usei os comandos do Git para chaves SSH, escolha pessoal minha, se preferir use os mesmos comandos utilizando o acesso via HTTPS. Caso queira utilizar o SSH assim como eu você vai precisar de chaves, [esses tutoriais do GitHub em inglês ensina como gerá-las e utilizá-las](https://help.github.com/articles/connecting-to-github-with-ssh/).
* Prometo fazer um post explicando como alterar o layout e outras coisas no tema em breve.