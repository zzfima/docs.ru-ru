---
title: Общие сведения об Entity SQL
ms.date: 03/30/2017
ms.assetid: f0bb8120-e709-40a3-ac1e-5520dc47477d
ms.openlocfilehash: 54a3832cffbf3376e6b3ab0826b280b676ccc1a0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54534648"
---
# <a name="entity-sql-overview"></a>Общие сведения об Entity SQL
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] представляет собой язык, подобный языку SQL, который позволяет выполнять запросы к концептуальным моделям в [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)]. Концептуальные модели представляют данные в виде сущностей и связей, и [!INCLUDE[esql](../../../../../../includes/esql-md.md)] позволяет запрашивать эти сущности и связи в формате, который хорошо знаком тем, кто использовал SQL.  
  
 Платформа [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] работает с зависящими от хранилища поставщиками данных в целях преобразования общих конструкций языка [!INCLUDE[esql](../../../../../../includes/esql-md.md)] в специфичные для хранилища запросы. Поставщик EntityClient предоставляет способ выполнения команды языка [!INCLUDE[esql](../../../../../../includes/esql-md.md)] на модели сущностей и получения разнообразных типов данных, в том числе скалярных результатов, результирующих наборов и графов объектов. При создании объекта <xref:System.Data.EntityClient.EntityCommand> можно указать имя хранимой процедуры или текст запроса, присвоив строку запроса на языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)] его свойству <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType>. <xref:System.Data.EntityClient.EntityDataReader> предоставляет доступ к результатам выполнения <xref:System.Data.EntityClient.EntityCommand> к модели EDM. Для выполнения команды, возвращающей значение <xref:System.Data.EntityClient.EntityDataReader>, нужно вызвать метод <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A>.  
  
 Помимо поставщика EntityClient, платформа [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] обеспечивает выполнение запросов [!INCLUDE[esql](../../../../../../includes/esql-md.md)] к концептуальной модели и возврат данных в виде строго типизированных объектов среды CLR, которые являются экземплярами типов сущностей. Дополнительные сведения см. в разделе [работа с объектами](../../../../../../docs/framework/data/adonet/ef/working-with-objects.md).  
  
 В этом разделе приведены основные сведения о языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
## <a name="in-this-section"></a>В этом разделе  
 [Отличия Entity SQL от Transact-SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)  
  
 [Краткий справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-quick-reference.md)  
  
 [Система типов](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md)  
  
 [Определения типов](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md)  
  
 [Сборка типов](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)  
  
 [Кэширование плана запроса](../../../../../../docs/framework/data/adonet/ef/language-reference/query-plan-caching-entity-sql.md)  
  
 [Пространства имен](../../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md)  
  
 [Идентификаторы](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)  
  
 [Параметры](../../../../../../docs/framework/data/adonet/ef/language-reference/parameters-entity-sql.md)  
  
 [Переменные](../../../../../../docs/framework/data/adonet/ef/language-reference/variables-entity-sql.md)  
  
 [Неподдерживаемые выражения](../../../../../../docs/framework/data/adonet/ef/language-reference/unsupported-expressions-entity-sql.md)  
  
 [Литералы](../../../../../../docs/framework/data/adonet/ef/language-reference/literals-entity-sql.md)  
  
 [Литералы NULL и вывод типов](../../../../../../docs/framework/data/adonet/ef/language-reference/null-literals-and-type-inference-entity-sql.md)  
  
 [Набор символов ввода](../../../../../../docs/framework/data/adonet/ef/language-reference/input-character-set-entity-sql.md)  
  
 [Выражения запросов](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)  
  
 [Функции](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md)  
  
 [Приоритет операторов](../../../../../../docs/framework/data/adonet/ef/language-reference/operator-precedence-entity-sql.md)  
  
 [Разбивка на страницы](../../../../../../docs/framework/data/adonet/ef/language-reference/paging-entity-sql.md)  
  
 [Семантика сравнения](../../../../../../docs/framework/data/adonet/ef/language-reference/comparison-semantics-entity-sql.md)  
  
 [Составление вложенных запросов Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/composing-nested-entity-sql-queries.md)  
  
 [Допускающие значения NULL структурированные типы](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)  
  
## <a name="see-also"></a>См. также
- [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [Язык Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
- [Спецификации CSDL, SSDL и MSL](../../../../../../docs/framework/data/adonet/ef/language-reference/csdl-ssdl-and-msl-specifications.md)
