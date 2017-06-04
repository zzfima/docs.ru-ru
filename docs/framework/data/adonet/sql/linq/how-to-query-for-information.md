---
title: "Как выполнять запросы о сведениях | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e538d288-2070-40ca-9da6-4fbc68cd6ad0
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Как выполнять запросы о сведениях
Для запросов в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] используется тот же синтаксис, что и для запросов [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].  Единственное отличие заключается в том, что объекты, на которые ссылаются запросы [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], сопоставляются с элементами базы данных.  Для получения дополнительной информации см. [Introduction to LINQ Queries \(C\#\)](../Topic/Introduction%20to%20LINQ%20Queries%20\(C%23\).md).  
  
 Технология [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует написанные пользователем запросы в эквивалентные запросы SQL и отправляет их на сервер для обработки.  
  
 Некоторым запросам [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)], возможно, требуется уделить особое внимание в приложениях [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  Для получения дополнительной информации см. [Основные понятия о запросах](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md).  
  
## Пример  
 Следующий запрос возвращает список клиентов из Лондона.  В этом примере используется таблица `Customers` из учебной базы данных "Northwind".  
  
 [!code-csharp[DLinqQuerying#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#1)]
 [!code-vb[DLinqQuerying#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#1)]  
  
## См. также  
 [Создание модели объектов](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)   
 [Загрузка образцов баз данных](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)   
 [Выполнение запросов к базе данных](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)