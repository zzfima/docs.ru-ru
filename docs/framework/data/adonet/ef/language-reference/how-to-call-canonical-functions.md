---
title: "Как вызывать канонические функции | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b3d84873-7403-4957-8e20-b4ae39f50214
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Как вызывать канонические функции
Класс <xref:System.Data.Objects.EntityFunctions> содержит методы, предоставляющие доступ к каноническим функциям для использования в запросах LINQ to Entities.  Дополнительные сведения о канонических функциях см. в разделе [Канонические функции](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md).  
  
> [!NOTE]
>  Методы <xref:System.Data.Objects.EntityFunctions.AsUnicode%2A> и <xref:System.Data.Objects.EntityFunctions.AsNonUnicode%2A> в классе <xref:System.Data.Objects.EntityFunctions> не имеют эквивалентных канонических функций.  
  
 Канонические функции, которые производят вычисление по ряду значений и возвращают одиночное значение \(известные также как статистические канонические функции\), могут вызываться напрямую.  Другие канонические функции могут вызываться только в составе запроса LINQ to Entities.  Чтобы вызвать агрегатную функцию напрямую, ей необходимо передать экземпляр <xref:System.Data.Objects.ObjectQuery%601>.  Дополнительные сведения см. в приведенном ниже втором примере.  
  
 Некоторые канонические функции можно вызвать с помощью методов среды CLR в запросах LINQ to Entities.  Список методов CLR, сопоставленных с каноническими функциями, см. в разделе [Сопоставление методов CLR каноническим функциям](../../../../../../docs/framework/data/adonet/ef/language-reference/clr-method-to-canonical-function-mapping.md).  
  
## Пример  
 В следующем примере используется модель [AdventureWorks Sales Model](http://msdn.microsoft.com/ru-ru/f16cd988-673f-4376-b034-129ca93c7832).  В этом примере выполняется запрос LINQ to Entities, в котором используется метод <xref:System.Data.Objects.EntityFunctions.DiffDays%2A> для возврата всех продуктов, для которых разница между датами `SellEndDate` и `SellStartDate` меньше 365 суток:  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#1)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#1)]  
  
## Пример  
 В следующем примере используется модель [AdventureWorks Sales Model](http://msdn.microsoft.com/ru-ru/f16cd988-673f-4376-b034-129ca93c7832).  В этом примере напрямую вызывается статистическая функция <xref:System.Data.Objects.EntityFunctions.StandardDeviation%2A> для возврата стандартного отклонения промежуточных итогов `SalesOrderHeader`.  Обратите внимание, что в функцию передается экземпляр <xref:System.Data.Objects.ObjectQuery%601>, что позволяет вызывать ее, хотя она и не входит в состав запроса LINQ to Entities.  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#2)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#2)]  
  
## См. также  
 [Вызов функций в запросах LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md)   
 [Запросы в LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)