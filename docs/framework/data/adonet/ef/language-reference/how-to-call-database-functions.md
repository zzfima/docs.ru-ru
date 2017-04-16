---
title: "Как вызвать функции базы данных | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 79038efa-15bf-464a-83e2-35fe145252ce
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Как вызвать функции базы данных
Класс <xref:System.Data.Objects.SqlClient.SqlFunctions> содержит методы среды CLR, предоставляющие доступ к функциям SQL Server для использования в запросах LINQ to Entities.  При использовании методов <xref:System.Data.Objects.SqlClient.SqlFunctions> в запросах LINQ to Entities в базе данных выполняются соответствующие функции базы данных.  
  
> [!NOTE]
>  Функции базы данных, которые производят вычисление по ряду значений и возвращают одиночное значение \(известные также как статистические функции баз данных\), могут вызываться напрямую.  Другие канонические функции могут вызываться только в составе запроса LINQ to Entities.  Чтобы вызвать агрегатную функцию напрямую, ей необходимо передать экземпляр <xref:System.Data.Objects.ObjectQuery%601>.  Дополнительные сведения см. в приведенном ниже втором примере.  
  
> [!NOTE]
>  Методы класса <xref:System.Data.Objects.SqlClient.SqlFunctions> поддерживаются только в функциях SQL Server.  Аналогичные классы, предоставляющие функции баз данных, могут быть доступны в других поставщиках.  
  
## Пример  
 В следующем примере используется модель [AdventureWorks Sales Model](http://msdn.microsoft.com/ru-ru/f16cd988-673f-4376-b034-129ca93c7832).  В примере выполняется запрос LINQ to Entities, в котором с помощью метода <xref:System.Data.Objects.SqlClient.SqlFunctions.CharIndex%2A> возвращаются все контакты, в которых фамилия начинается с «Si»:  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#3)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#3)]  
  
## Пример  
 В следующем примере используется модель [AdventureWorks Sales Model](http://msdn.microsoft.com/ru-ru/f16cd988-673f-4376-b034-129ca93c7832).  В примере напрямую вызывается статистический метод <xref:System.Data.Objects.SqlClient.SqlFunctions.ChecksumAggregate%2A>.  Обратите внимание, что в функцию передается экземпляр <xref:System.Data.Objects.ObjectQuery%601>, что позволяет вызывать ее, хотя она и не входит в состав запроса LINQ to Entities.  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#4)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#4)]  
  
## См. также  
 [Вызов функций в запросах LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md)   
 [Запросы в LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)