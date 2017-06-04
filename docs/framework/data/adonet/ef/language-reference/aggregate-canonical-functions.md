---
title: "Канонические статистические функции | Microsoft Docs"
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
ms.assetid: 3bcff826-ca90-41b3-a791-04d6ff0e5085
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Канонические статистические функции
Статистические выражения \- выражения, которые уменьшают количество входных значений, например, до одного значения.  Статистические выражения обычно используются совместно с предложением группирования GROUP BY выражения SELECT, а на область их использования накладываются ограничения.  
  
 В следующей таблице приведены канонические статистические функции языка [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
|Функция|Описание|  
|-------------|--------------|  
|`Avg(` `expression` `)`|Возвращает среднее для значений, отличных от NULL.<br /><br /> **Аргументы**<br /><br /> Имеют типы `Int32`,  `Int64`, `Double` и `Decimal`.<br /><br /> **Возвращаемое значение**<br /><br /> Тип параметра `expression`.  Возвращает `Null`, если все входные значения представляют собой значения `null`.<br /><br /> **Пример**<br /><br /> [!code-csharp[DP EntityServices Concepts#EDM_AVG](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_avg)]
 [!code-sql[DP EntityServices Concepts#EDM_AVG](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_avg)]|  
|`BigCount(` `expression` `)`|Возвращает объем данных, подвергаемых статистической обработке, включая значения NULL и повторяющиеся значения.<br /><br /> **Аргументы**<br /><br /> Любой тип.<br /><br /> **Возвращаемое значение**<br /><br /> `Int64`.<br /><br /> **Пример**<br /><br /> [!code-csharp[DP EntityServices Concepts#EDM_BIGCOUNT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_bigcount)]
 [!code-sql[DP EntityServices Concepts#EDM_BIGCOUNT](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_bigcount)]|  
|`Count(` `expression` `)`|Возвращает объем данных, подвергаемых статистической обработке, включая значения NULL и повторяющиеся значения.<br /><br /> **Аргументы**<br /><br /> Любой тип.<br /><br /> **Возвращаемое значение**<br /><br /> `Int32`.<br /><br /> **Пример**<br /><br /> [!code-csharp[DP EntityServices Concepts#EDM_COUNT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_count)]
 [!code-sql[DP EntityServices Concepts#EDM_COUNT](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_count)]|  
|`Max(` `expression` `)`|Возвращает максимум для значений, отличных от NULL.<br /><br /> **Аргументы**<br /><br /> Данные типа `Byte`, `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, `Decimal`, `DateTime`, `DateTimeOffset`, `Time`, `String`, `Binary`.<br /><br /> **Возвращаемое значение**<br /><br /> Тип параметра `expression`.  Возвращает `Null`, если все входные значения представляют собой значения `null`.<br /><br /> **Пример**<br /><br /> [!code-csharp[DP EntityServices Concepts#EDM_MAX](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_max)]
 [!code-sql[DP EntityServices Concepts#EDM_MAX](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_max)]|  
|`Min(` `expression` `)`|Возвращает минимум для значений, отличных от NULL.<br /><br /> **Аргументы**<br /><br /> Значения типа `Byte`, `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, `Decimal`, `DateTime`, `DateTimeOffset`, `Time`, `String`, `Binary`.<br /><br /> **Возвращаемое значение**<br /><br /> Тип параметра `expression`.  Возвращает `Null`, если все входные значения представляют собой значения `null`.<br /><br /> **Пример**<br /><br /> [!code-csharp[DP EntityServices Concepts#EDM_MIN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_min)]
 [!code-sql[DP EntityServices Concepts#EDM_MIN](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_min)]|  
|`StDev(` `expression` `)`|Возвращает стандартное отклонение для значений, отличных от NULL.<br /><br /> **Аргументы**<br /><br /> Имеют типы `Int32`, `Int64`, `Double` и `Decimal`.<br /><br /> **Возвращаемое значение**<br /><br /> Объект `Double`.  Возвращает `Null`, если все входные значения представляют собой значения `null`.<br /><br /> **Пример**<br /><br /> [!code-csharp[DP EntityServices Concepts#EDM_STDEV](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_stdev)]
 [!code-sql[DP EntityServices Concepts#EDM_STDEV](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_stdev)]|  
|`StDevP(` `expression` `)`|Возвращает стандартное отклонение для заполнения по всем значениям.<br /><br /> **Аргументы**<br /><br /> Имеют типы `Int32`, `Int64`, `Double` и `Decimal`.<br /><br /> **Возвращаемое значение**<br /><br /> Объект `Double`.  Возвращает `Null`, если все входные значения представляют собой значения `null`.<br /><br /> **Пример**<br /><br /> [!code-csharp[DP EntityServices Concepts#EDM_STDEVP](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_stdevp)]
 [!code-sql[DP EntityServices Concepts#EDM_STDEVP](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_stdevp)]|  
|`Sum(` `expression` `)`|Возвращает сумму для значений, отличных от NULL.<br /><br /> **Аргументы**<br /><br /> Имеют типы  `Int32`, `Int64`, `Double` и `Decimal`.<br /><br /> **Возвращаемое значение**<br /><br /> Объект `Double`.  Возвращает `Null`, если все входные значения представляют собой значения `null`.<br /><br /> **Пример**<br /><br /> [!code-csharp[DP EntityServices Concepts#EDM_SUM](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_sum)]
 [!code-sql[DP EntityServices Concepts#EDM_SUM](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_sum)]|  
|`Var(` `expression` `)`|Возвращает дисперсию всех значений, отличных от NULL.<br /><br /> **Аргументы**<br /><br /> Имеют типы `Int32`, `Int64`, `Double` и `Decimal`.<br /><br /> **Возвращаемое значение**<br /><br /> Объект `Double`.  Возвращает `Null`, если все входные значения представляют собой значения `null`.<br /><br /> **Пример**<br /><br /> [!code-csharp[DP EntityServices Concepts#EDM_VAR](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_var)]
 [!code-sql[DP EntityServices Concepts#EDM_VAR](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_var)]|  
|`VarP(` `expression` `)`|Возвращает дисперсию для заполнения по всем значениям, отличным от NULL.<br /><br /> **Аргументы**<br /><br /> Имеют типы `Int32`, `Int64`, `Double` и `Decimal`.<br /><br /> **Возвращаемое значение**<br /><br /> Объект `Double`.  Возвращает `Null`, если все входные значения представляют собой значения `null`.<br /><br /> **Пример**<br /><br /> [!code-csharp[DP EntityServices Concepts#EDM_VARP](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_varp)]
 [!code-sql[DP EntityServices Concepts#EDM_VARP](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_varp)]|  
  
 Эквивалентную функциональность предоставляет управляемый поставщик клиента Microsoft SQL.  Для получения дополнительной информации см. [Функции SqlClient для платформы Entity Framework](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).  
  
## Статистические функции на основе коллекций  
 Статистические функции на основе коллекций \(функции коллекций\) работают с коллекциями и возвращают значение.  Например, если ORDERS \- коллекция всех заказов, то можно рассчитать самую раннюю дату отгрузки с использованием следующего выражения:  
  
```  
min(select value o.ShipDate from LOB.Orders as o)  
```  
  
 Выражения внутри статистических функций на основе коллекций вычисляются в текущей внешней области разрешения имен.  
  
## Статистические функции на основе групп  
 Статистические функции на основе групп вычисляются для группы, определенной предложением GROUP BY.  Для каждой группы результата выполняется отдельное статистическое вычисление с использованием элементов каждой группы в качестве входных значений.  Если в выражении SELECT используется предложение группирования, в проекции или предложении сортировки могут употребляться только имена выражений группирования, статистические функции или константные выражения.  
  
 В следующем примере вычисляется средняя величина заказа для каждого продукта.  
  
```  
select p, avg(ol.Quantity) from LOB.OrderLines as ol  
  group by ol.Product as p  
```  
  
 Возможна статистическая функция на основе групп без явного предложения группирования в выражении SELECT.  В этом случае все элементы будут обрабатываться как одна группа.  Это эквивалентно группированию на основе константы.  Например, выражение:  
  
```  
select avg(ol.Quantity) from LOB.OrderLines as ol  
```  
  
 Оно эквивалентно следующему выражению:  
  
```  
select avg(ol.Quantity) from LOB.OrderLines as ol group by 1  
```  
  
 Выражения внутри статистической функции на основе групп вычисляются в области разрешения имен, видимой для выражения предложения WHERE.  
  
 Как и в [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)], статистические функции на основе групп могут также задавать модификатор ALL или DISTINCT.  Если задан модификатор DISTINCT, то перед вычислением статистической функции из входного набора исключаются повторяющиеся значения.  Если задан модификатор ALL \(или не указан никакой модификатор\), то исключение повторяющихся значений не выполняется.  
  
## См. также  
 [Канонические функции](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)