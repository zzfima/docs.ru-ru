---
title: Общие сведения об Entity SQL
ms.date: 03/30/2017
ms.assetid: f0bb8120-e709-40a3-ac1e-5520dc47477d
ms.openlocfilehash: 880b81f2b6d4c4b893d28c919490f88dfb2a42e8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150380"
---
# <a name="entity-sql-overview"></a>Общие сведения об Entity SQL
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]— это язык, похожий на S'L, который позволяет заставить заставить заранее о концептуальных моделях в рамочной системе entity. Концептуальные модели представляют данные как сущности и отношения и [!INCLUDE[esql](../../../../../../includes/esql-md.md)] позволяют заставить заинтересовать эти сущности и отношения в формате, знакомом тем, кто использовал S'L.  

 Рамочная система сущности работает с поставщиками данных для хранения данных для перевода генерических [!INCLUDE[esql](../../../../../../includes/esql-md.md)] в запросы, касающиеся данных. Поставщик EntityClient предоставляет способ выполнения команды языка [!INCLUDE[esql](../../../../../../includes/esql-md.md)] на модели сущностей и получения разнообразных типов данных, в том числе скалярных результатов, результирующих наборов и графов объектов. При создании объекта <xref:System.Data.EntityClient.EntityCommand> можно указать имя хранимой процедуры или текст запроса, присвоив строку запроса на языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)] его свойству <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType>. <xref:System.Data.EntityClient.EntityDataReader> предоставляет доступ к результатам выполнения <xref:System.Data.EntityClient.EntityCommand> к модели EDM. Для выполнения команды, возвращающей значение <xref:System.Data.EntityClient.EntityDataReader>, нужно вызвать метод <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A>.  
  
 Помимо поставщика EntityClient, рамочная система [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Entity Framework позволяет использовать для выполнения запросов в отношении концептуальной модели и возврата данных в качестве сильно набранных объектов CLR, которые являются экземплярами типов сущностей. Для получения дополнительной информации [см.](../working-with-objects.md)  
  
 В этом разделе приведены основные сведения о языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
## <a name="in-this-section"></a>в этом разделе  
 [Отличия Entity SQL от Transact-SQL](how-entity-sql-differs-from-transact-sql.md)  
  
 [Краткий справочник по Entity SQL](entity-sql-quick-reference.md)  
  
 [Система типов](type-system-entity-sql.md)  
  
 [Определения типов](type-definitions-entity-sql.md)  
  
 [Сборка типов](constructing-types-entity-sql.md)  
  
 [Кэширование плана запроса](query-plan-caching-entity-sql.md)  
  
 [Пространства имен](namespaces-entity-sql.md)  
  
 [Идентификаторы](identifiers-entity-sql.md)  
  
 [Параметры](parameters-entity-sql.md)  
  
 [Переменные](variables-entity-sql.md)  
  
 [Неподдерживаемые выражения](unsupported-expressions-entity-sql.md)  
  
 [Литералы](literals-entity-sql.md)  
  
 [Литералы NULL и вывод типов](null-literals-and-type-inference-entity-sql.md)  
  
 [Набор символов ввода](input-character-set-entity-sql.md)  
  
 [Выражения запросов](query-expressions-entity-sql.md)  
  
 [Функции](functions-entity-sql.md)  
  
 [Приоритет операторов](operator-precedence-entity-sql.md)  
  
 [Разбиение по страницам](paging-entity-sql.md)  
  
 [Семантика сравнения](comparison-semantics-entity-sql.md)  
  
 [Составление вложенных запросов Entity SQL](composing-nested-entity-sql-queries.md)  
  
 [Допускающие значения NULL структурированные типы](nullable-structured-types-entity-sql.md)  
  
## <a name="see-also"></a>См. также раздел

- [Справочник по Entity SQL](entity-sql-reference.md)
- [Язык Entity SQL](entity-sql-language.md)
- [Спецификации CSDL, SSDL и MSL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)
