---
layout: post
title: 'Adicionando um novo projeto na lista da #Hacktoberfest 2019'
date: 2019-09-27 08:00:00 -0300
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

_TK Nota da autora_: existem inúmeras formas de fazer esse pull request, aqui eu vou ensinar um formato usando o navegador para que você possa fazer sua contribuição mesmo que você não tenha conhecimentos profundos de git. Se você já tem prática em contribuir com projetos no GitHub, pula direto para essa seção que tem uma lista de passos menos detalhada do PR que deve ser o suficiente pra você fazer a sua contribuição.

## Passo 1

Abra o repósitorio que você quer adicionar na lista numa página. Aqui vamos usar de exemplo o[ Guia do Cientista de Dados das Galáxias](https://github.com/PizzaDeDados/datascience-pizza), na seção de Variados. 

TK imagem guia

## Passo 2

Em outra página, abra [o repositório desse site aqui](https://github.com/jtemporal/jtemporal.github.io).

TK imagem do repositório

## Passo 3

No repositório desse site, 

Para isso vamos usar o seguinte pedaço de código:

    <div>
      <a class="github-project-share" href="LINK DO REPOSITÓRIO" >
        <p> DESCRIÇÃO </p>
        <img src="LINK DA FOTO"/>
      </a>
    </div>