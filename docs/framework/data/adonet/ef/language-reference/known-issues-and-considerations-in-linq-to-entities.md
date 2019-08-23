---
title: 'LINQ to Entities: рекомендации и известные проблемы'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: acd71129-5ff0-4b4e-b266-c72cc0c53601
ms.openlocfilehash: 66af3395d7ba7271323ad6461e8e1fb8c823a1c6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913904"
---
# <a name="known-issues-and-considerations-in-linq-to-entities"></a>LINQ to Entities: рекомендации и известные проблемы
В этом разделе содержатся сведения об известных проблемах с LINQ to Entities запросами.  
  
- [Запросы LINQ, которые не могут быть кэшированы](#LINQQueriesThatAreNotCached)  
  
- [Потеря сведений о заказе](#OrderingInfoLost)  
  
- [Неподдерживаемые целые числа без знака](#UnsignedIntsUnsupported)  
  
- [Ошибки преобразования типов](#TypeConversionErrors)  
  
- [Ссылки на нескалярные переменные не поддерживаются](#RefNonScalarClosures)  
  
- [Вложенные запросы могут завершаться ошибкой с SQL Server 2000](#NestedQueriesSQL2000)  
  
- [Проецирование в анонимный тип](#ProjectToAnonymousType)  
  
<a name="LINQQueriesThatAreNotCached"></a>   
## <a name="linq-queries-that-cannot-be-cached"></a>Запросы LINQ, которые нельзя кэшировать  
 Начиная с .NET Framework 4.5, запросы LINQ to Entities автоматически сохраняются в кэше. Тем не менее запросы LINQ to Entities, которые применяют оператор `Enumerable.Contains` к коллекции в памяти, автоматически не кэшируются. Также в скомпилированных запросах LINQ не допускаются коллекции в памяти с параметрами.  
  
<a name="OrderingInfoLost"></a>   
## <a name="ordering-information-lost"></a>Потеря данных об упорядочении  
 Проецирование столбцов в анонимный тип приведет к потере сведений о заказе в некоторых запросах, выполняемых для базы данных SQL Server 2005, для которой задан уровень совместимости "80".  Это происходит в том случае, если имя столбца в списке упорядочения соответствует имени столбца в селекторе, как показано в следующем примере.  
  
 [!code-csharp[DP L2E Conceptual Examples#SBUDT543840](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#sbudt543840)]
 [!code-vb[DP L2E Conceptual Examples#SBUDT543840](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#sbudt543840)]  
  
<a name="UnsignedIntsUnsupported"></a>   
## <a name="unsigned-integers-not-supported"></a>Целые числа без знака не поддерживаются  
 Указание целочисленного типа без знака в LINQ to Entitiesном запросе не поддерживается, так как [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] не поддерживает целые числа без знака. Если указать целое число без знака, <xref:System.ArgumentException> во время преобразования выражения запроса будет создано исключение, как показано в следующем примере. В этом примере производится запрос заказа с идентификатором 48000.  
  
 [!code-csharp[DP L2E Conceptual Examples#UIntAsQueryParam](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#uintasqueryparam)]
 [!code-vb[DP L2E Conceptual Examples#UIntAsQueryParam](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#uintasqueryparam)]  
  
<a name="TypeConversionErrors"></a>   
## <a name="type-conversion-errors"></a>Ошибки преобразования типа  
 Когда в Visual Basic свойство сопоставляется со столбцом типа данных SQL Server bit, имеющим значение 1 при помощи функции `CByte`, то возникнет исключение <xref:System.Data.SqlClient.SqlException> с сообщением «Ошибка арифметического переполнения». В следующем примере производится запрос столбца `Product.MakeFlag` в образце базы данных AdventureWorks, и при переборе результатов запроса выдается исключение.  
  
 [!code-vb[DP L2E Conceptual Examples#SBUDT544355](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#sbudt544355)]  
  
<a name="RefNonScalarClosures"></a>   
## <a name="referencing-non-scalar-variables-not-supported"></a>Обращение к нескалярным переменным не поддерживается  
 Обращение к нескалярным переменным, например к сущностям, в запросе не поддерживаются. При выполнении такого запроса возникает исключение <xref:System.NotSupportedException> с сообщением «Невозможно создать константу типа `EntityType`. В этом контексте поддерживаются только типы-примитивы (такие как Int32, String, и Guid)».  
  
> [!NOTE]
> Обращение к набору скалярных переменных поддерживается.  
  
 [!code-csharp[DP L2E Conceptual Examples#SBUDT555877](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#sbudt555877)]
 [!code-vb[DP L2E Conceptual Examples#SBUDT555877](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#sbudt555877)]  
  
<a name="NestedQueriesSQL2000"></a>   
## <a name="nested-queries-may-fail-with-sql-server-2000"></a>Вложенные запросы могут не работать с SQL Server 2000  
 В SQL Server 2000 запросы LINQ to Entities могут не работать, если они порождают вложенные запросы Transact-SQL с тремя и более уровнями вложенности.  
  
<a name="ProjectToAnonymousType"></a>   
## <a name="projecting-to-an-anonymous-type"></a>Проектирование анонимного типа  
 Если при определении первоначального пути запроса в него включены связанные объекты с помощью метода <xref:System.Data.Objects.ObjectQuery%601.Include%2A> для <xref:System.Data.Objects.ObjectQuery%601>, а затем возвращаемые объекты анонимного типа проектировались с помощью LINQ, то объекты, указанные в методе добавления, не включаются в результаты запроса.  
  
 [!code-csharp[DP L2E Conceptual Examples#ProjToAnonType1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#projtoanontype1)]
 [!code-vb[DP L2E Conceptual Examples#ProjToAnonType1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#projtoanontype1)]  
  
 Для получения связанных объектов не следует проектировать возвращаемые типы как анонимный тип.  
  
 [!code-csharp[DP L2E Conceptual Examples#ProjToAnonType2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#projtoanontype2)]
 [!code-vb[DP L2E Conceptual Examples#ProjToAnonType2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#projtoanontype2)]  
  
## <a name="see-also"></a>См. также

- [LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md)
