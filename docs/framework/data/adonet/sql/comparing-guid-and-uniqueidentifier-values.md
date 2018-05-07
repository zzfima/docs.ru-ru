---
title: Сравнение значений идентификатора GUID и uniqueidentifier
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: aababd75-2335-43e3-ace8-4b7ae84191a8
ms.openlocfilehash: ce6ba9a73e65b5f418ff9cf5a1ef4ca4ff0c36ba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="comparing-guid-and-uniqueidentifier-values"></a>Сравнение значений идентификатора GUID и uniqueidentifier
Тип данных идентификатора GUID в SQL Server представлен типом данных `uniqueidentifier`, который хранит 16-байтовое двоичное значение. Идентификатор GUID - это двоичное число, главным образом используемое для назначения идентификаторов, которые должны быть уникальными в рамках сети с большим числом компьютеров в различных расположениях. Идентификаторы GUID можно создавать путем вызова функции Transact-SQL NEWID, они гарантированно будут уникальными в любом расположении. Дополнительные сведения см. в разделе «Использование значений типа uniqueidentifier» электронной документации по SQL Server.  
  
## <a name="working-with-sqlguid-values"></a>Работа со значениями SqlGuid  
 Так как значения GUID являются длинными и непрозрачными, они не несут никакой смысловой нагрузки для пользователей. Если в качестве ключевых значений используются случайные значения GUID и вставляется много строк, то это порождает увеличение операций ввода-вывода в индексах, что может отрицательно сказаться на производительности. Кроме того, значения GUID относительно велики в сравнении с другими типами данных. В целом значения GUID рекомендуется использовать только для узкого круга сценариев, для которых не подходят другие типы данных.  
  
### <a name="comparing-guid-values"></a>Сравнение значений GUID  
 Значения `uniqueidentifier` можно использовать в операторах сравнения. Однако их упорядочение реализовано без использования поразрядного сравнения. Только операции, которые допускаются в отношении `uniqueidentifier` значение — это сравнения (=, <>, \<, >, \<=, > =) и проверки на значение NULL (IS NULL и IS NOT NULL). Другие арифметические операторы запрещены.  
  
 В структурах <xref:System.Guid> и <xref:System.Data.SqlTypes.SqlGuid> имеется метод `CompareTo` для сравнения разных значений GUID. Однако методы `System.Guid.CompareTo` и `SqlTypes.SqlGuid.CompareTo` реализованы по-разному. В <xref:System.Data.SqlTypes.SqlGuid> метод `CompareTo` реализуется при помощи поведения SQL Server в наиболее значимых последних 6 байтах значения. В <xref:System.Guid> оцениваются все 16 байт. В следующем примере демонстрируется это различие. В первой части кода показаны несортированные значения <xref:System.Guid>, во второй части - сортированные значения <xref:System.Guid>. В третьей части показаны отсортированные значения <xref:System.Data.SqlTypes.SqlGuid>. Выходные данные показаны после листинга кода.  
  
 [!code-csharp[DataWorks SqlTypes.Guid#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTypes.Guid/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTypes.Guid#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTypes.Guid/VB/source.vb#1)]  
  
 В этом примере получаются следующие результаты.  
  
```  
Unsorted Guids:  
3aaaaaaa-bbbb-cccc-dddd-2eeeeeeeeeee  
2aaaaaaa-bbbb-cccc-dddd-1eeeeeeeeeee  
1aaaaaaa-bbbb-cccc-dddd-3eeeeeeeeeee  
  
Sorted Guids:  
1aaaaaaa-bbbb-cccc-dddd-3eeeeeeeeeee  
2aaaaaaa-bbbb-cccc-dddd-1eeeeeeeeeee  
3aaaaaaa-bbbb-cccc-dddd-2eeeeeeeeeee  
  
Sorted SqlGuids:  
2aaaaaaa-bbbb-cccc-dddd-1eeeeeeeeeee  
3aaaaaaa-bbbb-cccc-dddd-2eeeeeeeeeee  
1aaaaaaa-bbbb-cccc-dddd-3eeeeeeeeeee  
```  
  
## <a name="see-also"></a>См. также  
 [Типы данных SQL Server и ADO.NET](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
