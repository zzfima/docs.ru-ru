---
title: "Известные проблемы и замечания по LINQ to Entities | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: acd71129-5ff0-4b4e-b266-c72cc0c53601
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Известные проблемы и замечания по LINQ to Entities
Этот раздел содержит сведения об известных проблемах, относящихся к запросам [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].  
  
-   [Запросы LINQ, которые нельзя кэшировать](#LINQQueriesThatAreNotCached)  
  
-   [Потеря данных об упорядочении](#OrderingInfoLost)  
  
-   [Целые числа без знака не поддерживаются](#UnsignedIntsUnsupported)  
  
-   [Ошибки преобразования типа](#TypeConversionErrors)  
  
-   [Обращение к нескалярным переменным не поддерживается](#RefNonScalarClosures)  
  
-   [Вложенные запросы могут не работать с SQL Server 2000](#NestedQueriesSQL2000)  
  
-   [Проектирование анонимного типа](#ProjectToAnonymousType)  
  
<a name="LINQQueriesThatAreNotCached"></a>   
## Запросы LINQ, которые нельзя кэшировать  
 Начиная с .NET Framework 4.5, запросы LINQ to Entities автоматически сохраняются в кэше.  Тем не менее запросы LINQ to Entities, которые применяют оператор `Enumerable.Contains` к коллекции в памяти, автоматически не кэшируются.  Также в скомпилированных запросах LINQ не допускаются коллекции в памяти с параметрами.  
  
<a name="OrderingInfoLost"></a>   
## Потеря данных об упорядочении  
 Проецирование столбцов на анонимные типы приведет к потере данных об упорядочении в некоторых запросах к базе данных [!INCLUDE[ssVersion2005](../../../../../../includes/ssversion2005-md.md)], для которой установлен уровень совместимости «80».  Это происходит в том случае, если имя столбца в списке упорядочения соответствует имени столбца в селекторе, как показано в следующем примере.  
  
 [!code-csharp[DP L2E Conceptual Examples#SBUDT543840](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#sbudt543840)]
 [!code-vb[DP L2E Conceptual Examples#SBUDT543840](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#sbudt543840)]  
  
<a name="UnsignedIntsUnsupported"></a>   
## Целые числа без знака не поддерживаются  
 Указание целых чисел без знака в запросе [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] не поддерживается, поскольку [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] не поддерживает целые числа без знака. Если указано целое число без знака, возникает исключение <xref:System.ArgumentException> в процессе преобразования выражения запроса, как показано в следующем примере.  В этом примере производится запрос заказа с идентификатором 48000.  
  
 [!code-csharp[DP L2E Conceptual Examples#UIntAsQueryParam](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#uintasqueryparam)]
 [!code-vb[DP L2E Conceptual Examples#UIntAsQueryParam](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#uintasqueryparam)]  
  
<a name="TypeConversionErrors"></a>   
## Ошибки преобразования типа  
 Когда в Visual Basic свойство сопоставляется со столбцом типа данных SQL Server bit, имеющим значение 1 при помощи функции `CByte`, то возникнет исключение <xref:System.Data.SqlClient.SqlException> с сообщением «Ошибка арифметического переполнения».  В следующем примере производится запрос столбца `Product.MakeFlag` в образце базы данных AdventureWorks, и при переборе результатов запроса выдается исключение.  
  
 [!code-vb[DP L2E Conceptual Examples#SBUDT544355](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#sbudt544355)]  
  
<a name="RefNonScalarClosures"></a>   
## Обращение к нескалярным переменным не поддерживается  
 Обращение к нескалярным переменным, например к сущностям, в запросе не поддерживаются.  При выполнении такого запроса возникает исключение <xref:System.NotSupportedException> с сообщением «Невозможно создать константу типа `EntityType`.  В этом контексте поддерживаются только типы\-примитивы \(такие как Int32, String, и Guid\)».  
  
> [!NOTE]
>  Обращение к набору скалярных переменных поддерживается.  
  
 [!code-csharp[DP L2E Conceptual Examples#SBUDT555877](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#sbudt555877)]
 [!code-vb[DP L2E Conceptual Examples#SBUDT555877](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#sbudt555877)]  
  
<a name="NestedQueriesSQL2000"></a>   
## Вложенные запросы могут не работать с SQL Server 2000  
 В SQL Server 2000 запросы LINQ to Entities могут не работать, если они порождают вложенные запросы Transact\-SQL с тремя и более уровнями вложенности.  
  
<a name="ProjectToAnonymousType"></a>   
## Проектирование анонимного типа  
 Если при определении первоначального пути запроса в него включены связанные объекты с помощью метода <xref:System.Data.Objects.ObjectQuery%601.Include%2A> для <xref:System.Data.Objects.ObjectQuery%601>, а затем возвращаемые объекты анонимного типа проектировались с помощью LINQ, то объекты, указанные в методе добавления, не включаются в результаты запроса.  
  
 [!code-csharp[DP L2E Conceptual Examples#ProjToAnonType1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#projtoanontype1)]
 [!code-vb[DP L2E Conceptual Examples#ProjToAnonType1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#projtoanontype1)]  
  
 Для получения связанных объектов не следует проектировать возвращаемые типы как анонимный тип.  
  
 [!code-csharp[DP L2E Conceptual Examples#ProjToAnonType2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#projtoanontype2)]
 [!code-vb[DP L2E Conceptual Examples#ProjToAnonType2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#projtoanontype2)]  
  
## См. также  
 [LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md)