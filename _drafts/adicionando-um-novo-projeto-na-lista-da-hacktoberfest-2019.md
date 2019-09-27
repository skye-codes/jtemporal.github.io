---
layout: post
title: 'Adicionando um novo projeto na lista da #Hacktoberfest 2019'
date: 2019-09-27T11:00:00.000+00:00
image: "/images/tutorial.png"
tags:
- tutorial
comments: true
description: Vou te mostrar o passo a passo pra colocar um repo na lista de 2019

---
A lista de projetos brasileiros para contribuir nesse Hacktoberfest de 2019 é gerada automáticamente usando algumas mágicas do Liquid como eu explico nesse outro artigo. Então, vamos ver como podemos adicionar um novo projeto nessa lista por meio de um _pull request_?

TK gif lets do this

## Materiais

1. Um navegador (eu vou usar o Firefox, mas você pode usar o que preferir);
2. Uma conta no GitHub;
3. Disposição.

_TK Nota da autora_: existem inúmeras formas de fazer esse _pull request_ (PR), aqui eu vou ensinar um formato usando o navegador para que você possa fazer sua contribuição mesmo que você não tenha conhecimentos profundos de git. Se você já tem prática em contribuir com projetos no GitHub, pula direto para essa seção que tem uma lista de passos menos detalhada do PR que deve ser o suficiente pra você fazer a sua contribuição.

## Abrindo o repositório do PR

Pra começar abra [o repositório desse site aqui](https://github.com/jtemporal/jtemporal.github.io) numa página do seu navegador.

<center>
<img src="/images/repo-jtemporal.png" alt="Imagem mostrando o repositório deste site"/>
<br>
<small><i>Imagem mostrando o repositório deste site</i></small>
</center>

## Copiando o template

No repositório desse site, que você acabou de abrir, navegue até a pasta `.github/` e copie o conteúdo do arquivo `repo-owner+repo-name.md` (eu recomendo que você use o modo Raw do arquivo para fazer essa cópia). Veja o gif a seguir com esse processo:

<center>
<img src="https://media.giphy.com/media/Y0Jt7zY8vxlWJ0dIGv/giphy.gif" alt="Gif mostrando o passo a passo descrito acima"/>
</center>

Esse arquivo é o template de informações necessárias para mostrar corretamente um projeto na lista.

## Onde moram os projetos

Ainda no repositório desse site, vá até a pasta `_hacktoberfest_projects/`, lá é onde moram os dados de todos os projetos que estão sendo mostrados na lista de 2019:

TK gif passo_3

na pasta `_hacktoberfest_projects/` temos muitas pastas, elas existem apenas como por questões organizacionais, cada pasta tem o nome de uma linguagem, e o projeto que você quer adicionar deve ser acrescentado na pasta correspondente à linguagem principal do projeto.

## Escolhendo um projeto para adicionar

Agora, numa nova página, abra o repósitorio que você quer adicionar na lista. Aqui vamos usar de exemplo o [Guia do Cientista de Dados das Galáxias](https://github.com/PizzaDeDados/datascience-pizza) (Guia).

<center>
<img src="/images/repo-guia-github.png" alt="Imagem mostrando o repositório Guia do Cientista de Dados das Galáxias"/>
<br>
<small><i>Imagem mostrando o repositório Guia do Cientista de Dados das Galáxias</i></small>
</center>

## Criando um arquivo para o projeto

O Guia é um projeto agnóstico de linguagem, afinal é apenas um grande conjunto de arquivos em markdown, sendo assim, vamos criar o arquivo do Guia na pasta  `Variados`. Para criar o arquivo clique em `Create new file`, em seguida cole o conteúdo que copiamos do arquivo `repo-owner+repo-name.md` no espaço de conteúdo, dê o nome do arquivo seguindo o padrão `<nome-do-dono-do-repo>+<nome-nome-do-repo>.md`. Veja o gif:

TK passo5

## Abrindo o PR

Finalmente

a pasta nao existe

o repo nao tem descricao