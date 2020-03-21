---
title: 'LINQ to Entities: рекомендации и известные проблемы'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: acd71129-5ff0-4b4e-b266-c72cc0c53601
ms.openlocfilehash: 90119da0fce7a708323d790f91f28206cac0a0dc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150146"
---
# <a name="known-issues-and-considerations-in-linq-to-entities"></a>LINQ to Entities: рекомендации и известные проблемы
В этом разделе содержится информация об известных проблемах с запросами линз для организаций.  
  
- [Запросы LINQ, которые нельзя кэшировать](#LINQQueriesThatAreNotCached)  
  
- [Потеря данных об упорядочении](#OrderingInfoLost)  
  
- [Целые числа без знака не поддерживаются](#UnsignedIntsUnsupported)  
  
- [Ошибки преобразования типа](#TypeConversionErrors)  
  
- [Обращение к нескалярным переменным не поддерживается](#RefNonScalarClosures)  
  
- [Вложенные запросы могут не работать с SQL Server 2000](#NestedQueriesSQL2000)  
  
- [Проектирование анонимного типа](#ProjectToAnonymousType)  
  
<a name="LINQQueriesThatAreNotCached"></a>
## <a name="linq-queries-that-cannot-be-cached"></a>Запросы LINQ, которые нельзя кэшировать  
 Начиная с .NET Framework 4.5, запросы LINQ to Entities автоматически сохраняются в кэше. Тем не менее запросы LINQ to Entities, которые применяют оператор `Enumerable.Contains` к коллекции в памяти, автоматически не кэшируются. Также в скомпилированных запросах LINQ не допускаются коллекции в памяти с параметрами.  
  
<a name="OrderingInfoLost"></a>
## <a name="ordering-information-lost"></a>Потеря данных об упорядочении  
 Проектирование столбцов в анонимный тип приведет к потере информации о заказе в некоторых запросах, выполняемых в соответствии с базой данных S'L Server 2005, установленной на уровне совместимости "80".  Это происходит в том случае, если имя столбца в списке упорядочения соответствует имени столбца в селекторе, как показано в следующем примере.  
  
 [!code-csharp[DP L2E Conceptual Examples#SBUDT543840](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#sbudt543840)]
 [!code-vb[DP L2E Conceptual Examples#SBUDT543840](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#sbudt543840)]  
  
<a name="UnsignedIntsUnsupported"></a>
## <a name="unsigned-integers-not-supported"></a>Целые числа без знака не поддерживаются  
 Указание неподписанного типа целых в запросе на то, чтобы объекты, не поддерживается, поскольку рамочная система entity не поддерживает неподписанные целые ряды. Если вы укажете неподписанный <xref:System.ArgumentException> целый размер, во время перевода экспрессии запроса будет брошено исключение, как показано в следующем примере. В этом примере производится запрос заказа с идентификатором 48000.  
  
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
  
## <a name="see-also"></a>См. также раздел

- [ЛИНЗ для юридических лиц](linq-to-entities.md)
