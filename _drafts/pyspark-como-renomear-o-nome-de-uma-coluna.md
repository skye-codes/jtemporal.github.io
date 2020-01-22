---
layout: post
date: 2020-01-22 20:06:44 -0200
image: "/images/colinha.png"
comments: true
title: 'PySpark: como renomear o nome de uma coluna'
description: Aprenda a usar um método para renomear colunas
tags:
- português
- colinha
- spark
- python
- pyspark

---
    data = sqlContext.createDataFrame([("Alberto", 2), ("Dakota", 2)], 
                                      ["Name", "askdaosdka"])
    data.show()
    data.printSchema()

data.withColumnRenamed("askdaosdka", "age")