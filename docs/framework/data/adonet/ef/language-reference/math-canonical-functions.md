---
title: "Математические канонические функции | Microsoft Docs"
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
ms.assetid: 6f6cddc6-b561-4ebe-84b6-841ef5b4113b
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Математические канонические функции
Язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] включает математические канонические функции.  
  
 В следующей таблице приведены математические канонические функции языка [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
|Функция|Описание|  
|-------------|--------------|  
|`Abs(` `value` `)`|Возвращает абсолютное значение `value`.<br /><br /> **Аргументы**<br /><br /> Имеют тип `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double` и `Decimal`.<br /><br /> **Возвращаемое значение**<br /><br /> Тип параметра `value`.<br /><br /> **Пример**<br /><br /> `Abs(-2)`|  
|`Ceiling(` `value` `)`|Возвращает наименьшее целое число, которое не меньше значения `value`.<br /><br /> **Аргументы**<br /><br /> Имеют тип `Single`, `Double` и `Decimal`.<br /><br /> **Возвращаемое значение**<br /><br /> Тип параметра `value`.<br /><br /> **Пример**<br /><br /> [!code-csharp[DP EntityServices Concepts#EDM_CEILING](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_ceiling)]
 [!code-sql[DP EntityServices Concepts#EDM_CEILING](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_ceiling)]|  
|`Floor(` `value` `)`|Возвращает наибольшее целое число, которое не больше значения `value`.<br /><br /> **Аргументы**<br /><br /> Имеют тип `Single`, `Double` и `Decimal`.<br /><br /> **Возвращаемое значение**<br /><br /> Тип параметра `value`.<br /><br /> **Пример**<br /><br /> [!code-csharp[DP EntityServices Concepts#EDM_FLOOR](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_floor)]
 [!code-sql[DP EntityServices Concepts#EDM_FLOOR](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_floor)]|  
|`Power(` `value`, `exponent``)`|Возвращает результат для заданного значения `value` по заданному показателю `exponent`.<br /><br /> **Аргументы**<br /><br /> `value`:  `Int32, Int64, Double` или `Decimal`.<br /><br /> `exponent`:  `Int64``, Double` или `Decimal`.<br /><br /> **Возвращаемое значение**<br /><br /> Тип параметра `value`.<br /><br /> **Пример**<br /><br /> `Power(748.58,2)`|  
|`Round(` `value` `)`|Возвращает целую часть `value`, округленную до ближайшего целого значения.<br /><br /> **Аргументы**<br /><br /> Имеют тип `Single`, `Double` и `Decimal`.<br /><br /> **Возвращаемое значение**<br /><br /> Тип параметра `value`.<br /><br /> **Пример**<br /><br /> `Round(748.58)`|  
|`Round(` `value`, `digits``)`|Возвращает значение `value`, округленное до ближайшего указанного знака `digits`.<br /><br /> **Аргументы**<br /><br /> `value`: `Double` или `Decimal`.<br /><br /> `digits`: `Int16` или `Int32`.<br /><br /> **Возвращаемое значение**<br /><br /> Тип параметра `value`.<br /><br /> **Пример**<br /><br /> `Round(748.58,1)`|  
|`Truncate(` `value`, `digits``)`|Возвращает значение `value`, усеченное до ближайшего указанного знака `digits`.<br /><br /> **Аргументы**<br /><br /> `value`: `Double` или `Decimal`.<br /><br /> `digits`: `Int16` или `Int32`.<br /><br /> **Возвращаемое значение**<br /><br /> Тип параметра `value`.<br /><br /> **Пример**<br /><br /> `Truncate(748.58,1)`|  
  
 Эти функции возвращают `null` при получении на входе `null`.  
  
 Эквивалентную функциональность предоставляет управляемый поставщик клиента Microsoft SQL.  Для получения дополнительной информации см. [Функции SqlClient для платформы Entity Framework](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).  
  
## См. также  
 [Канонические функции](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)