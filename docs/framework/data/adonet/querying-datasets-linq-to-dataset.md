---
title: "Запросы к объектам DataSet (LINQ to DataSet) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: bb68d2e4-623d-4d60-85e3-965254f6fee7
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Запросы к объектам DataSet (LINQ to DataSet)
После того как в объекте <xref:System.Data.DataSet> появятся данные, к нему можно выполнять запросы.  Составление запросов с использованием [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] похоже на использование [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] с другими источниками данных, поддерживающих [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)].  Тем не менее нужно помнить, что при использовании запросов [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] к <xref:System.Data.DataSet> запрашивается перечисление объектов типа <xref:System.Data.DataRow> вместо перечисления определенного типа.  Это означает, что в запросах [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] можно использовать любые элементы класса <xref:System.Data.DataRow>.  Это позволяет создавать мощные, сложные запросы.  
  
 Так же как и с помощью других реализаций [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)], запросы [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] можно создавать двух различных видов: в синтаксисе выражений запросов и синтаксисе запросов, основанных на методе.  Дополнительные сведения об этих двух видах см. в разделе [Getting Started with LINQ](http://msdn.microsoft.com/ru-ru/6cc9af04-950a-4cc3-83d4-2aeb4abe4de9). Синтаксис выражений запросов и синтаксис запросов на основе методов может быть использован для выполнения запросов к отдельным таблицам в <xref:System.Data.DataSet>, к нескольким таблицам в <xref:System.Data.DataSet>, а также к таблицам в типизированном <xref:System.Data.DataSet>.  
  
## Содержание  
 [Запросы к одиночным таблицам](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)  
 Описывается выполнение запросов к отдельным таблицам.  
  
 [Межтабличные запросы](../../../../docs/framework/data/adonet/cross-table-queries-linq-to-dataset.md)  
 Описывается выполнение межтабличных запросов.  
  
 [Запрос к типизированным объектам DataSet](../../../../docs/framework/data/adonet/querying-typed-datasets.md)  
 Описываются запросы к типизированным объектам <xref:System.Data.DataSet>.  
  
## См. также  
 [Примеры LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)   
 [Загрузка данных в DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)