---
title: "Нахождение наименьшего значения в числовой последовательности | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 78203093-f242-4572-9b31-9495b10926aa
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Нахождение наименьшего значения в числовой последовательности
Для возвращения минимального значения из последовательности числовых значений используется оператор <xref:System.Linq.Enumerable.Min%2A>.  
  
## Пример  
 В следующем примере выполняется поиск минимальной цены продукта.  
  
 Если выполнить этот запрос в образце базы данных Northwind, то будут получены следующие выходные данные: `2.5000`.  
  
 [!code-csharp[DLinqQueryExamples#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#9)]
 [!code-vb[DLinqQueryExamples#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#9)]  
  
## Пример  
 В следующем примере выполняется поиск минимального объема доставки для заказа.  
  
 Если выполнить этот запрос в образце базы данных Northwind, то будут получены следующие выходные данные: `0.0200`.  
  
 [!code-csharp[DLinqQueryExamples#10](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#10)]
 [!code-vb[DLinqQueryExamples#10](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#10)]  
  
## Пример  
 В следующем примере для поиска `Products`, имеющего минимальную цену за единицу в каждой категории используется функция Min.  Результат упорядочивается по категории.  
  
 [!code-csharp[DLinqQueryExamples#11](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#11)]
 [!code-vb[DLinqQueryExamples#11](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#11)]  
  
 Если выполнить предыдущий запрос для учебной базы данных "Northwind", результаты будут выглядеть следующим образом.  
  
 `1`  
  
 `Guaraná Fantástica`  
  
 `2`  
  
 `Aniseed Syrup`  
  
 `3`  
  
 `Teatime Chocolate Biscuits`  
  
 `4`  
  
 `Geitost`  
  
 `5`  
  
 `Filo Mix`  
  
 `6`  
  
 `Tourtière`  
  
 `7`  
  
 `Longlife Tofu`  
  
 `8`  
  
 `Konbu`  
  
## См. также  
 [Агрегатные запросы](../../../../../../docs/framework/data/adonet/sql/linq/aggregate-queries.md)   
 [Загрузка образцов баз данных](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)