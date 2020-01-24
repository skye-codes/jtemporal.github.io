---
layout: post
date: 2020-01-24 10:17:01 -0200
image: "/images/colinha.png"
comments: true
title: 'PySpark: Usando window'
description: Como particionar seus dados para usar funções
tags: []

---
window functions usadas para particionar os seus dados e aplicar funções

com funciona? uso mais comum

from pyspark.sql.window import Window

window = Window().partitionBy('coluna com grupos').orderBy('coluna de ordenaçao')

window = (Window.orderBy(psf.col('count').desc(), psf.col('rank'))

             .rangeBetween(Window.unboundedPreceding, 0))

.over(Window.partitionBy()))

* qnd vc nao quer particionar?