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

_TK Nota da autora_: existem inúmeras formas de fazer esse _pull request_, aqui eu vou ensinar um formato usando o navegador para que você possa fazer sua contribuição mesmo que você não tenha conhecimentos profundos de git. Se você já tem prática em contribuir com projetos no GitHub, pula direto para essa seção que tem uma lista de passos menos detalhada do PR que deve ser o suficiente pra você fazer a sua contribuição.

## Passo 1

Abra [o repositório desse site aqui](https://github.com/jtemporal/jtemporal.github.io).

TK imagem do repositório

## Passo 2

No repositório desse site, que você acabou de abrir, navegue até a pasta `.github/` e copie o conteúdo do arquivo `repo-owner+repo-name.md` (eu recomendo que você use o modo Raw do arquivo para fazer essa cópia). Veja o gif a seguir com esse processo:

TK gif passo_2

## Passo 3

Ainda no repositório desse site, vá até a pasta `_hacktoberfest_projects/`, lá é onde moram os dados de todos os projetos que estão sendo mostrados na lista de 2019:

TK gif passo_3

na pasta `_hacktoberfest_projects/` temos muitas pastas, elas existem apenas como por questões organizacionais, cada pasta tem o nome de uma linguagem, e o projeto que você quer adicionar deve ser acrescentado na pasta correspondente à linguagem principal do projeto.

## Passo 4

Agora, numa nova página, abra o repósitorio que você quer adicionar na lista. Aqui vamos usar de exemplo o [Guia do Cientista de Dados das Galáxias](https://github.com/PizzaDeDados/datascience-pizza) (Guia).

TK imagem guia

## Passo 5

O Guia é um projeto agnóstico de linguagem, afinal é apenas um grande conjunto de arquivos em markdown, sendo assim, vamos criar o arquivo do Guia na pasta  `Variados`. Para criar o arquivo clique em Create new file, em seguida cole o conteúdo que copiamos do arquivo `repo-owner+repo-name.md`, dê o nome do arquivo seguindo o padrão `<nome-do-dono-do-repo>+<nome-nome-do-repo>.md`. Veja o gif:

TK passo5