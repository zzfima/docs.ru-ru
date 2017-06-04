---
title: "Как вызывать встроенные определяемые пользователем функции | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f80d4327-b6a5-4aa8-a743-e95d09a2a02e
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Как вызывать встроенные определяемые пользователем функции
Пользовательские функции можно вызывать из строки кода, однако функции, включенные в запрос, выполнение которого отложено, выполняются только одновременно с запросом.  Для получения дополнительной информации см. [Introduction to LINQ Queries \(C\#\)](../Topic/Introduction%20to%20LINQ%20Queries%20\(C%23\).md).  
  
 Если та же функция вызывается за пределами запроса, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] создает простой запрос из выражения вызова метода.  Ниже показан синтаксис SQL \(параметр `@p0` привязан к передаваемой константе\).  
  
```  
SELECT dbo.ReverseCustName(@p0)  
```  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] создает следующий код:  
  
 [!code-csharp[DLinqUDFS#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/Program.cs#4)]
 [!code-vb[DLinqUDFS#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/Module1.vb#4)]  
  
## Пример  
 В следующем запросе [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] показан вызов созданной пользовательской функции `ReverseCustName`, осуществляемый из строки кода.  Функция не выполняется немедленно, поскольку выполнение запроса отложено.  Код SQL, созданный для этого запроса, преобразуется в вызов пользовательской функции в базе данных \(см. код SQL, расположенный после запроса\).  
  
 [!code-csharp[DLinqUDFS#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/Program.cs#5)]
 [!code-vb[DLinqUDFS#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/Module1.vb#5)]  
  
```  
SELECT [t0].[ContactName],  
    dbo.ReverseCustName([t0].[ContactTitle]) AS [Title]  
FROM [Customers] AS [t0]  
```  
  
## См. также  
 [Определяемые пользователем функции](../../../../../../docs/framework/data/adonet/sql/linq/user-defined-functions.md)