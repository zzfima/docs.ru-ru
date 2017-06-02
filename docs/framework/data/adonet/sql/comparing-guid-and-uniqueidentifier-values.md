---
title: "Сравнение значений GUID и uniqueidentifier | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: aababd75-2335-43e3-ace8-4b7ae84191a8
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Сравнение значений GUID и uniqueidentifier
Тип данных идентификатора GUID в SQL Server представлен типом данных `uniqueidentifier`, который хранит 16\-байтовое двоичное значение.  Идентификатор GUID \- это двоичное число, главным образом используемое для назначения идентификаторов, которые должны быть уникальными в рамках сети с большим числом компьютеров в различных расположениях.  Идентификаторы GUID можно создавать путем вызова функции Transact\-SQL NEWID, они гарантированно будут уникальными в любом расположении.  Дополнительные сведения см. в разделе «Использование значений типа uniqueidentifier» электронной документации по SQL Server.  
  
## Работа со значениями SqlGuid  
 Так как значения GUID являются длинными и непрозрачными, они не несут никакой смысловой нагрузки для пользователей.  Если в качестве ключевых значений используются случайные значения GUID и вставляется много строк, то это порождает увеличение операций ввода\-вывода в индексах, что может отрицательно сказаться на производительности.  Кроме того, значения GUID относительно велики в сравнении с другими типами данных.  В целом значения GUID рекомендуется использовать только для узкого круга сценариев, для которых не подходят другие типы данных.  
  
### Сравнение значений GUID  
 Значения `uniqueidentifier` можно использовать в операторах сравнения.  Однако их упорядочение реализовано без использования поразрядного сравнения.  Над значениями `uniqueidentifier` можно выполнять только операции сравнения \(\=, \<\>, \<, \>, \<\=, \>\=\), а также проверку на значение NULL \(IS NULL и IS NOT NULL\).  Другие арифметические операторы запрещены.  
  
 В структурах <xref:System.Guid> и <xref:System.Data.SqlTypes.SqlGuid> имеется метод `CompareTo` для сравнения разных значений GUID.  Однако методы `System.Guid.CompareTo` и `SqlTypes.SqlGuid.CompareTo` реализованы по\-разному.  В <xref:System.Data.SqlTypes.SqlGuid> метод `CompareTo` реализуется при помощи поведения SQL Server в наиболее значимых последних 6 байтах значения.  В <xref:System.Guid> оцениваются все 16 байт.  В следующем примере демонстрируется это различие.  В первой части кода показаны несортированные значения <xref:System.Guid>, во второй части \- сортированные значения <xref:System.Guid>.  В третьей части показаны отсортированные значения <xref:System.Data.SqlTypes.SqlGuid>.  Выходные данные показаны после листинга кода.  
  
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
  
## См. также  
 [Типы данных SQL Server и ADO.NET](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)