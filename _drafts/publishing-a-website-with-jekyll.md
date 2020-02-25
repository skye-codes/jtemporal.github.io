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

Rerun the `bundle exec jekyll serve` command. This time the site you need to access changed because we changed `baseurl` to `/blogfresh`. Now go to `http://localhost:4000/blogfresh/` to see the changes. With these changes in `_config.yml`, the site should look something like this:

![blog alterado profile info](https://i.imgur.com/kut6tWL.png)

### Social

This is where the links to your social networks come from. The ones you don't want to make available just don't fill out. Let's fill the values for the ones I want:

``` yml
# Social
facebook: #Add your Facebook
twitter: #Add your Twitter
google-plus: #Add your Google+
github: @jtemporal
```

Unfortunately, this theme does not "hide" the buttons for social networks that do not have a valid username/link. I'll write a post on how to do that soon.

### Contact Form

If you want people to contact you through the site contact form, just uncomment them and put your email address in place of `your-email@domain.com`. Since I do not like receiving emails, I left it commented `¯\_(ツ)_/¯`.

``` yml
# Contact form
email: #your-email@domain.com
```

### Comments

That's a fun part, comments on your posts! If you don't know [Disqus](http://disqus.com/) yet, it's a platform that helps increase engagement on your site. It allows people to comment on your blog in a relatively easy way. Create an account and place your identifier here:

``` yml
# Comments
discus-identifier: jtemporal
```

After restarting the server for the configuration file changes to take effect, you should have an area that looks like the image below at the end of each post:

![area de comentarios disqus](https://i.imgur.com/3Lc0O9q.png)

### Pagination

This is where you define how many posts appear per page on your site:

* Posts per page (`paginate`): how many blog posts appear on each page;
* Page URL (`paginate_path`): This variable defines how the URLs of a specific page will be generated, for example, `blog/page2/index.html`.

``` yml
# Paginate
paginate: 5
paginate_path: /page:num/
```

### Build settings

Here you will not need to change anything, but it is good to understand what each of these things means, right?!

* Markdown Renderer (`markdown`): Here, you can choose which Markdown renderer to use. The default is `kramdown`;      
* Gems needed for this theme (`gems`): here is a list of gems that need to be installed;      
* Exclude directories and files (`exclude`): These are files and directories to be disregarded when generating site pages;      
* Include files and directories (`include`): These are files and directories to consider when building site pages; if you want to serve a file, let's say a PDF file, you must include it in this list.

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

When you finish fixing `_config.yml`, remember to commit the changes! Committing everything is a necessary step to guarantee that what you see on your computer is what everyone accessing your site on the internet is seeing. I will assume you'll commit every step from now on 😉

## Posts

Fresh, as well as all other themes available, provide examples of posts. The first thing you'll notice when opening one of them in the text editor is that it has a kind of header known as [Front Matter](https://jekyllrb.com/docs/frontmatter/). We use the Front Matter to set values to things like the post title, date of publication, and so on.

### Understanding the Front Matter

* `layout`: Jekyll sees all blog pages as a blog post that it needs to render, including About, Contact and Home pages, so the layout tag is used to differentiate rendering, the options for fresh are: post or default;      
* `title`:  The title of the post;      
* `date`: The date and time of publication following `YYYY-MM-DD HH:MM:SS` format. You can still set the time zone of the article using this field;
* `description`: Each blog post can have a synopsis paragraph in the post listing. This is where this synopsis goes.

#### First post

Let's create a new post from scratch and put it on the site. Create a file inside the `_posts` directory:

``` console
$ touch _posts/2018-01-07-hello-world.md
```

It is customary to use the pattern `YYYY-MM-DD-post-name.md` in file names. Remember that it is from the filename that the URLs will be generated for each post, so choose your file names carefully.

Open the file we just created, paste the following Front Matter and content:


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