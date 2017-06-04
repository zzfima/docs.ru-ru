---
title: "Сортировка элементов в последовательности | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d59b93a9-50c8-4770-a114-d902f6a0ea76
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Сортировка элементов в последовательности
Для сортировки последовательности по одному или нескольким ключам используется оператор <xref:System.Linq.Enumerable.OrderBy%2A>.  
  
> [!NOTE]
>  В [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] предусмотрена поддержка упорядочения по простым примитивным типам, таким как `string`, `int` и т. д.  В этой технологии не поддерживается упорядочение для сложных многозначных классов, таких как анонимные типы.  В ней также не поддерживаются типы данных `byte`.  
  
## Пример  
 В следующем примере выполняется сортировка сотрудников \(`Employees`\) по дате приема на работу.  
  
 [!code-csharp[DLinqQueryExamples#20](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#20)]
 [!code-vb[DLinqQueryExamples#20](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#20)]  
  
## Пример  
 В следующем примере для сортировки заказов \(`Orders`\), поставленных в Лондон \(`London`\), по типу перевозки используется предложение `where`.  
  
 [!code-csharp[DLinqQueryExamples#21](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#21)]
 [!code-vb[DLinqQueryExamples#21](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#21)]  
  
## Пример  
 В следующем примере выполняется сортировка продуктов \(`Products`\) по цене единицы товара по убыванию.  
  
 [!code-csharp[DLinqQueryExamples#22](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#22)]
 [!code-vb[DLinqQueryExamples#22](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#22)]  
  
## Пример  
 В следующем примере для сортировки клиентов \(`Customers`\) по городу, а затем по контактному лицу используется составной оператор `OrderBy`.  
  
 [!code-csharp[DLinqQueryExamples#24](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#24)]
 [!code-vb[DLinqQueryExamples#24](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#24)]  
  
## Пример  
 В следующем примере выполняется сортировка заказов от сотрудника `EmployeeID 1` по стране доставки, а затем по типу перевозки по убыванию.  
  
 [!code-csharp[DLinqQueryExamples#25](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#25)]
 [!code-vb[DLinqQueryExamples#25](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#25)]  
  
## Пример  
 В следующем примере объединяются операторы <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.Max%2A> и <xref:System.Linq.Enumerable.GroupBy%2A>, чтобы найти продукты \(`Products`\) с максимальной ценой за единицу товара в каждой категории, а затем выполнить сортировку полученной группы по коду категории.  
  
 [!code-csharp[DLinqQueryExamples#26](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#26)]
 [!code-vb[DLinqQueryExamples#26](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#26)]  
  
 Если выполнить предыдущий запрос для учебной базы данных "Northwind", результаты должны выглядеть следующим образом:  
  
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
 [Примеры запросов](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)   
 [Загрузка образцов баз данных](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)