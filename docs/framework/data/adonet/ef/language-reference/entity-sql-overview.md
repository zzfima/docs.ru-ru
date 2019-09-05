---
title: Общие сведения об Entity SQL
ms.date: 03/30/2017
ms.assetid: f0bb8120-e709-40a3-ac1e-5520dc47477d
ms.openlocfilehash: 4d7db9c6a7aaeef900132663a5b0aa7420afe668
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251073"
---
# <a name="entity-sql-overview"></a>Общие сведения об Entity SQL
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] представляет собой язык, подобный языку SQL, который позволяет выполнять запросы к концептуальным моделям в [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)]. Концептуальные модели представляют данные как сущности и связи, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] а также позволяют запрашивать эти сущности и связи в формате, привычном для тех, кто использовал SQL.  
  
 Платформа [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] работает с зависящими от хранилища поставщиками данных в целях преобразования общих конструкций языка [!INCLUDE[esql](../../../../../../includes/esql-md.md)] в специфичные для хранилища запросы. Поставщик EntityClient предоставляет способ выполнения команды языка [!INCLUDE[esql](../../../../../../includes/esql-md.md)] на модели сущностей и получения разнообразных типов данных, в том числе скалярных результатов, результирующих наборов и графов объектов. При создании объекта <xref:System.Data.EntityClient.EntityCommand> можно указать имя хранимой процедуры или текст запроса, присвоив строку запроса на языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)] его свойству <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType>. <xref:System.Data.EntityClient.EntityDataReader> предоставляет доступ к результатам выполнения <xref:System.Data.EntityClient.EntityCommand> к модели EDM. Для выполнения команды, возвращающей значение <xref:System.Data.EntityClient.EntityDataReader>, нужно вызвать метод <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A>.  
  
 Помимо поставщика EntityClient, платформа [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] обеспечивает выполнение запросов [!INCLUDE[esql](../../../../../../includes/esql-md.md)] к концептуальной модели и возврат данных в виде строго типизированных объектов среды CLR, которые являются экземплярами типов сущностей. Дополнительные сведения см. в разделе [Работа с объектами](../working-with-objects.md).  
  
 В этом разделе приведены основные сведения о языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
## <a name="in-this-section"></a>В этом разделе  
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
  
 [Разбивка на страницы](paging-entity-sql.md)  
  
 [Семантика сравнения](comparison-semantics-entity-sql.md)  
  
 [Составление вложенных запросов Entity SQL](composing-nested-entity-sql-queries.md)  
  
 [Допускающие значения NULL структурированные типы](nullable-structured-types-entity-sql.md)  
  
## <a name="see-also"></a>См. также

- [Справочник по Entity SQL](entity-sql-reference.md)
- [Язык Entity SQL](entity-sql-language.md)
- [Спецификации CSDL, SSDL и MSL](csdl-ssdl-and-msl-specifications.md)
