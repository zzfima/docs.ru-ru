---
title: Математические канонические функции
ms.date: 03/30/2017
ms.assetid: 6f6cddc6-b561-4ebe-84b6-841ef5b4113b
ms.openlocfilehash: 9d823eb45babca4b8f5dd717b4fb92c1984d1c8c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="math-canonical-functions"></a>Математические канонические функции
Язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] включает математические канонические функции.  
  
 В следующей таблице приведены математические канонические функции языка [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
|Функция|Описание|  
|--------------|-----------------|  
|`Abs(` `value` `)`|Возвращает абсолютное значение `value`.<br /><br /> **Аргументы**<br /><br /> `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, И `Decimal`.<br /><br /> **Возвращаемое значение**<br /><br /> Тип параметра `value`.<br /><br /> **Пример**<br /><br /> `Abs(-2)`|  
|`Ceiling(` `value` `)`|Возвращает наименьшее целое число, которое не меньше значения `value`.<br /><br /> **Аргументы**<br /><br /> Объект `Single`, `Double`, и `Decimal`.<br /><br /> **Возвращаемое значение**<br /><br /> Тип параметра `value`.<br /><br /> **Пример**<br /><br /> [!code-csharp[DP EntityServices Concepts#EDM_CEILING](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_ceiling)]
 [!code-sql[DP EntityServices Concepts#EDM_CEILING](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_ceiling)]|  
|`Floor(` `value` `)`|Возвращает наибольшее целое число, которое не больше значения `value`.<br /><br /> **Аргументы**<br /><br /> Объект `Single`, `Double`, и `Decimal`.<br /><br /> **Возвращаемое значение**<br /><br /> Тип параметра `value`.<br /><br /> **Пример**<br /><br /> [!code-csharp[DP EntityServices Concepts#EDM_FLOOR](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_floor)]
 [!code-sql[DP EntityServices Concepts#EDM_FLOOR](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_floor)]|  
|`Power(` `value`, `exponent``)`|Возвращает результат для заданного значения `value` по заданному показателю `exponent`.<br /><br /> **Аргументы**<br /><br /> `value`: `Int32, Int64, Double`, Или `Decimal`.<br /><br /> `exponent`: `Int64``, Double`, Или `Decimal`.<br /><br /> **Возвращаемое значение**<br /><br /> Тип параметра `value`.<br /><br /> **Пример**<br /><br /> `Power(748.58,2)`|  
|`Round(` `value` `)`|Возвращает целую часть `value`, округленную до ближайшего целого значения.<br /><br /> **Аргументы**<br /><br /> Объект `Single`, `Double`, и `Decimal`.<br /><br /> **Возвращаемое значение**<br /><br /> Тип параметра `value`.<br /><br /> **Пример**<br /><br /> `Round(748.58)`|  
|`Round(` `value`, `digits``)`|Возвращает значение `value`, округленное до ближайшего указанного знака `digits`.<br /><br /> **Аргументы**<br /><br /> `value`: `Double` или `Decimal`.<br /><br /> `digits`: `Int16` или `Int32`.<br /><br /> **Возвращаемое значение**<br /><br /> Тип параметра `value`.<br /><br /> **Пример**<br /><br /> `Round(748.58,1)`|  
|`Truncate(` `value`, `digits``)`|Возвращает значение `value`, усеченное до ближайшего указанного знака `digits`.<br /><br /> **Аргументы**<br /><br /> `value`: `Double` или `Decimal`.<br /><br /> `digits`: `Int16` или `Int32`.<br /><br /> **Возвращаемое значение**<br /><br /> Тип параметра `value`.<br /><br /> **Пример**<br /><br /> `Truncate(748.58,1)`|  
  
 Эти функции возвращают `null` при получении на входе `null`.  
  
 Эквивалентную функциональность предоставляет управляемый поставщик клиента Microsoft SQL. Дополнительные сведения см. в разделе [функции SqlClient для Entity Framework](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).  
  
## <a name="see-also"></a>См. также  
 [Канонические функции](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)
