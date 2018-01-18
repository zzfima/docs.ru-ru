---
title: "Функции даты и времени"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 971762d0-663b-4b64-8c61-352a8e6d3949
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: e68a78a3a24bf6da4e9827cb17d4715b6d60d0b8
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="date-and-time-functions"></a>Функции даты и времени
Поставщик данных .NET Framework для SQL Server (SqlClient) предоставляет функции даты и времени, которые выполняют операции с входным значением типа `System.DateTime` и возвращают значение типа `string` `System.DateTime` или числовое значение. Эти функции находятся в пространстве имен SqlServer, которое доступно при использовании SqlClient. Свойство пространства имен поставщика позволяет платформе Entity Framework узнать, какой префикс используется этим поставщиком для конкретных конструкций, таких как типы или функции. В следующей таблице приведены функции даты и времени SqlClient.  
  
|Функция|Описание:|  
|--------------|-----------------|  
|`DATEADD(` `datepart`, `number`, `date``)`|Возвращает новое значение типа `DateTime`, получаемое добавлением интервала к указанной дате.<br /><br /> **Аргументы**<br /><br /> `datepart`: значение `String`, указывающее часть даты, для которой должно быть возвращено новое значение.<br /><br /> `number`: значение `Int32`, `Int64`, `Decimal` или `Double`, используемое для увеличения значения `datepart`.<br /><br /> `date:`Выражение, возвращающее `DateTime`, или `DateTimeOffset`, или `Time` с точностью = [0-7] или строку символов в формате даты.<br /><br /> **Возвращаемое значение**<br /><br /> Новое значение `DateTime`, `DateTimeOffset` или `Time` с точностью = [0-7].<br /><br /> **Пример**<br /><br /> `SqlServer.DATEADD('day', 22, cast('6/9/2006' as DateTime))`|  
|`DATEDIFF(` `datepart`, `startdate`, `enddate``)`|Возвращает количество границ даты и времени, пересекаемых между двумя указанными датами.<br /><br /> **Аргументы**<br /><br /> `datepart`: значение `String`, представляющее часть даты, по которой должна быть вычислена разность.<br /><br /> `startdate`: начальная дата для вычисления выражения, которое возвращает значение `DateTime`, `DateTimeOffset` или `Time` с точностью = [0-7], либо символьная строка в формате даты.<br /><br /> `enddate:`Конечная дата для вычисления является выражение, возвращающее `DateTime`, или `DateTimeOffset`, или `Time` с точностью = [0-7] или строку символов в формате даты.<br /><br /> **Возвращаемое значение**<br /><br /> Объект `Int32`.<br /><br /> **Пример**<br /><br /> `SqlServer.DATEDIFF('day', cast('6/9/2006' as DateTime),`<br /><br /> `cast('6/20/2006' as DateTime))`|  
|`DATENAME(` `datepart`, `date``)`|Возвращает символьную строку, содержащую заданную часть указанной даты.<br /><br /> **Аргументы**<br /><br /> `datepart`: значение `String`, указывающее часть даты, для которой должно быть возвращено новое значение.<br /><br /> `date`: выражение, которое возвращает значение `DateTime,`, `DateTimeOffset` или `Time` с точностью = [0-7], либо символьная строка в формате даты.<br /><br /> **Возвращаемое значение**<br /><br /> Символьная строка, содержащая заданную часть указанной даты.<br /><br /> **Пример**<br /><br /> `SqlServer.DATENAME('year', cast('6/9/2006' as DateTime))`|  
|`DATEPART(` `datepart`, `date``)`|Возвращает целое число, представляющее указанную часть даты.<br /><br /> **Аргументы**<br /><br /> `datepart`: значение `String`, указывающее часть даты, для которой должно быть возвращено новое значение.<br /><br /> `date`: выражение, которое возвращает значение `DateTime,`, `DateTimeOffset,` или `Time` с точностью = [0-7], либо символьная строка в формате даты.<br /><br /> **Возвращаемое значение**<br /><br /> Заданная часть указанной даты в виде значения типа `Int32`.<br /><br /> **Пример**<br /><br /> `SqlServer.DATEPART('year', cast('6/9/2006' as DateTime))`|  
|`DAY(` `date` `)`|Возвращает день указанной даты в виде целого числа.<br /><br /> **Аргументы**<br /><br /> `date`: Выражение типа `DateTime` или `DateTimeOffset` с точностью = 0-7.<br /><br /> **Возвращаемое значение**<br /><br /> День указанной даты в виде значения типа `Int32`.<br /><br /> **Пример**<br /><br /> `SqlServer.DAY(cast('6/9/2006' as DateTime))`|  
|`GETDATE()`|Возвращает текущую дату и время во внутреннем формате SQL Server для значений datetime.<br /><br /> **Возвращаемое значение**<br /><br /> Текущее значение системных даты и времени в виде значения типа `DateTime` с точностью 3.<br /><br /> **Пример**<br /><br /> `SqlServer.GETDATE()`|  
|`GETUTCDATE()`|Возвращает значение datetime в формате UTC (универсальное синхронизированное время или среднее время по Гринвичу).<br /><br /> **Возвращаемое значение**<br /><br /> Значение `DateTime` с точностью 3 в формате UTC.<br /><br /> **Пример**<br /><br /> `SqlServer.GETUTCDATE()`|  
|`MONTH(` `date` `)`|Возвращает месяц заданной даты в виде значения целочисленного типа.<br /><br /> **Аргументы**<br /><br /> `date`: Выражение типа `DateTime` или `DateTimeOffset` с точностью = 0-7.<br /><br /> **Возвращаемое значение**<br /><br /> Месяц заданной даты в виде значения типа `Int32`.<br /><br /> **Пример**<br /><br /> `SqlServer.MONTH(cast('6/9/2006' as DateTime))`|  
|`YEAR(` `date` `)`|Возвращает год заданной даты в виде значения целочисленного типа.<br /><br /> **Аргументы**<br /><br /> `date`: Выражение типа `DateTime` или `DateTimeOffset` с точностью = 0-7.<br /><br /> **Возвращаемое значение**<br /><br /> Год указанной даты в виде значения типа `Int32`.<br /><br /> **Пример**<br /><br /> `SqlServer.YEAR(cast('6/9/2006' as DateTime))`|  
|`SYSDATETIME()`|Возвращает значение `DateTime` с точностью 7.<br /><br /> **Возвращаемое значение**<br /><br /> Значение `DateTime` с точностью 7.<br /><br /> **Пример**<br /><br /> `SqlServer.SYSDATETIME()`|  
|`SYSUTCDATE()`|Возвращает значение datetime в формате UTC (универсальное синхронизированное время или среднее время по Гринвичу).<br /><br /> **Возвращаемое значение**<br /><br /> Значение типа `DateTime` с точностью 7 в формате UTC.<br /><br /> **Пример**<br /><br /> `SqlServer.SYSUTCDATE()`|  
|`SYSDATETIMEOFFSET()`|Возвращает значение типа `DateTimeOffset` с точностью 7.<br /><br /> **Возвращаемое значение**<br /><br /> Значение типа `DateTimeOffset` с точностью 7 в формате UTC.<br /><br /> **Пример**<br /><br /> `SqlServer.SYSDATETIMEOFFSET()`|  
  
 Дополнительные сведения о функциях даты и времени, поддерживаемых SqlClient, см. в документации к версии SQL Server, указанной в манифесте поставщика SqlClient.  
  
|SQL Server 2000|SQL Server 2005|SQL Server 2008|  
|---------------------|---------------------|---------------------|  
|[Функции даты и времени (Transact-SQL)](http://go.microsoft.com/fwlink/?LinkId=115908)|[Функции даты и времени (Transact-SQL)](http://go.microsoft.com/fwlink/?LinkId=115909)|[Функции даты и времени (Transact-SQL)](http://go.microsoft.com/fwlink/?LinkId=98360)|  
  
## <a name="see-also"></a>См. также  
 [Функции SqlClient для Entity Framework](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)
