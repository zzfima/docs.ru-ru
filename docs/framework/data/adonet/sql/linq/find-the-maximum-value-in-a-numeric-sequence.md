---
title: "Нахождение наибольшего значения в числовой последовательности | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 70d7c058-0280-4815-a008-6f290093591a
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Нахождение наибольшего значения в числовой последовательности
Используйте оператор <xref:System.Linq.Enumerable.Max%2A> для нахождения максимального значения в числовой последовательности.  
  
## Пример  
 В следующем примере выполняется поиск самой последней даты приема сотрудника на работу.  
  
 Если этот запрос запустить в образце базы данных Northwind, то будут получены следующие выходные данные: `11/15/1994 12:00:00 AM`.  
  
 [!code-csharp[DLinqQueryExamples#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#6)]
 [!code-vb[DLinqQueryExamples#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#6)]  
  
## Пример  
 В следующем примере выполняется максимальное количество единиц продукта на складе.  
  
 Если этот пример запустить в образце базы данных Northwind, то будут получены следующие выходные данные: `125`.  
  
 [!code-csharp[DLinqQueryExamples#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#7)]
 [!code-vb[DLinqQueryExamples#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#7)]  
  
## Пример  
 В следующем примере для поиска `Products`, имеющего максимальную цену за единицу в каждой категории используется функция Max.  Результаты упорядочиваются по категории.  
  
 [!code-csharp[DLinqQueryExamples#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#8)]
 [!code-vb[DLinqQueryExamples#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#8)]  
  
 Если выполнить предыдущий запрос для учебной базы данных "Northwind", результаты будут выглядеть следующим образом.  
  
 `1`  
  
 `Côte de Blaye`  
  
 `2`  
  
 `Vegie-spread`  
  
 `3`  
  
 `Sir Rodney's Marmalade`  
  
 `4`  
  
 `Raclette Courdavault`  
  
 `5`  
  
 `Gnocchi di nonna Alice`  
  
 `6`  
  
 `Thüringer Rostbratwurst`  
  
 `7`  
  
 `Manjimup Dried Apples`  
  
 `8`  
  
 `Carnarvon Tigers`  
  
## См. также  
 [Агрегатные запросы](../../../../../../docs/framework/data/adonet/sql/linq/aggregate-queries.md)   
 [Загрузка образцов баз данных](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)