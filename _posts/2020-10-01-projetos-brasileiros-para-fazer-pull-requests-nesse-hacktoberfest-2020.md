---
title: 'Projetos Brasileiros para fazer pull requests nesse #Hacktoberfest 2020'
layout: post
date: 2020-10-01T09:00:00.000+00:00
image: "/images/variados.png"
tags:
- pull request
- pull requests
- contribuitions
- open-source
- hacktoberfest
- GitHub
- Git
- open source
- português
comments: true
description: 'Versão 2020 da lista de projetos brasileiros para contribuir no #Hacktoberfest'

---
Depois dos sucessos das listas [de 2017](https://medium.com/nossa-coletividad/projetos-brasileiros-para-fazer-pull-requests-nesse-hacktoberfest-4dc9b9b576c0), [de 2018](https://medium.com/@jessicatemporal/projetos-brasileiros-para-contribuir-nesse-hacktoberfest-vers%C3%A3o-2018-4925959b9411) e [de 2019](https://jtemporal.com/projetos-brasileiros-para-fazer-pull-requests-nesse-hacktoberfest-o-retorno/), esse é o QUARTO ano que estou fazendo a lista/curadoria de projetos brasileiros para contribuir no #Hacktoberfest (esse ano invadido pela [@anaschwendler](https://twitter.com/anaschwendler)!!11)

Então aqui vai! Uma lista toda repleta de projetos pra você contribuir nesse mês de Outubro!

Novamente temos regrinhas:

1. Ser um projeto criado/desenvolvido/mantido por brasileiras(os);
2. Ter pelo menos uma _issue_ aberta.

## Avisos para 2020

2020 não está sendo um ano fácil pra ninguém, apenas contribua com o que pode! S2

Esse ano vamos manter a mesma forma de aumentar essa lista com mais projetos, como sempre, apenas abrindo um PR com o projeto. [As instruções de como adicionar projetos tá aqui](https://jtemporal.com/adicionando-um-novo-projeto-na-lista-da-hacktoberfest-2019/). Todo mundo segue apenas ganhando <3.

Os projetos continuam separados pela linguagem principal pra facilitar as buscas pra quem lê e também em ordem alfabética pela linguagem. 😉

Happy Hacking!

***

{% assign grouped = site.hacktoberfest_projects | group_by: "principal_language" %}
{% for group in grouped %}
<h2> {{ group.name }} </h2>
{% for item in group.items %}
<div class="github-project-share">
<a style="text-decoration: none;" href="{{ item.repo }}">
{% assign project_info = item.relative_path |  remove: ".md" | remove: ".yml" | split: "/"  %}
{% assign project = project_info[2] | replace: "+", "/" %}
<div class="github-project-share-card ">
<img src="{{ item.image }}" alt="" />
<h4>{{ project }}</h4>
<br/>
<p>{{ item.description }}</p><br>
<p><small>github.com</small></p>
</div>
</a>
</div>
{%endfor%}

***

{%endfor%}
