---
title: Язык Entity SQL
ms.date: 03/30/2017
ms.assetid: 9e7d8837-28c5-429d-a824-7bafb59724cf
ms.openlocfilehash: 0c698f04c3b95ffb204a20d41e91ef3f6210c5d8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54494104"
---
# <a name="entity-sql-language"></a>Язык Entity SQL
Entity SQL представляет собой независимый от хранилища язык запросов, аналогичный языку SQL. Entity SQL позволяет выполнять запросы к данным сущности, представленным либо в виде объектов, либо в табличной форме. Возможность использования Entity SQL необходимо рассматривать в следующих случаях:  
  
-   Если запрос должен создаваться динамически во время выполнения. В этом случае следует также рассмотреть возможность использования методов построителя запросов <xref:System.Data.Objects.ObjectQuery%601> вместо создания строки запроса Entity SQL во время выполнения.  
  
-   Если требуется определить запрос как часть определения модели. В модели данных поддерживается только Entity SQL. Дополнительные сведения см. в разделе [элемент QueryView (MSL)](/ef/ef6/modeling/designer/advanced/edmx/msl-spec#queryview-element-msl)  
  
-   Если EntityClient применяется для возврата допускающих только для чтения данных сущности в виде наборов строк с использованием <xref:System.Data.EntityClient.EntityDataReader>. Дополнительные сведения см. в разделе [поставщик EntityClient для Entity Framework](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).  
  
-   Для специалиста по языкам запросов на основе SQL язык Entity SQL может оказаться самым естественным выбором.  
  
## <a name="using-entity-sql-with-the-entityclient-provider"></a>Использование Entity SQL с поставщиком EntityClient  
 Если требуется использовать Entity SQL с поставщиком EntityClient, см. дополнительные сведения в следующих разделах:  
  
 [Поставщик EntityClient для Entity Framework](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)  
  
 [Практическое руководство. Построить строку соединения EntityConnection](../../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)  
  
 [Практическое руководство. Выполнение запроса, возвращающего результаты PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)  
  
 [Практическое руководство. Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)  
  
 [Практическое руководство. Выполнение запроса, возвращающего результаты RefType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-reftype-results.md)  
  
 [Практическое руководство. Выполнение запроса, возвращающего сложные типы](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-complex-types.md)  
  
 [Практическое руководство. Выполнение запроса, возвращающего вложенные коллекции](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-nested-collections.md)  
  
 [Практическое руководство. Выполнение параметризованного запроса Entity SQL с использованием EntityCommand](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-entity-sql-query-using-entitycommand.md)  
  
 [Практическое руководство. Выполнить параметризированную хранимую процедуру с использованием EntityCommand](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-stored-procedure-using-entitycommand.md)  
  
 [Практическое руководство. Выполнить полиморфный запрос](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-polymorphic-query.md)  
  
 [Практическое руководство. Переход по отношениям с помощью оператора Navigate](../../../../../../docs/framework/data/adonet/ef/how-to-navigate-relationships-with-the-navigate-operator.md)  
  
## <a name="using-entity-sql-with-object-queries"></a>Использование Entity SQL с запросами объектов  
 Если требуется использовать Entity SQL с запросами объектов, см. дополнительные сведения в следующих разделах:  
  
 [Практическое руководство. Выполнение запроса, возвращающего объекты типа сущностей](https://msdn.microsoft.com/library/f73e137d-1534-42bb-9e31-99ca42c19b48)  
  
 [Практическое руководство. Выполнение параметризованного запроса](https://msdn.microsoft.com/library/42048f03-c65c-4d98-b50a-3e7d537a63e8)  
  
 [Практическое руководство. Переход по отношениям с помощью свойств навигации](https://msdn.microsoft.com/library/b1d71c7d-16a7-4b46-96ac-690176bd5057)  
  
 [Практическое руководство. Вызов определяемой пользователем функции](https://msdn.microsoft.com/library/ad131b86-8b4e-4747-8605-d4fc64fb9d02)  
  
 [Практическое руководство. Фильтрация данных](https://msdn.microsoft.com/library/776f8556-3350-4572-804a-b1513515c1b2)  
  
 [Практическое руководство. Сортировка данных](https://msdn.microsoft.com/library/c05f2506-cb9d-4ebc-822b-300042ad53e7)  
  
 [Практическое руководство. Группы данных](https://msdn.microsoft.com/library/df801d9d-9a8a-4157-97a6-5016b18998e1)  
  
 [Практическое руководство. Сводные данные](https://msdn.microsoft.com/library/4cf04ce8-3c0f-4f88-9d97-8fac8622598d)  
  
 [Практическое руководство. Выполнение запроса, возвращающего объекты анонимного типа](https://msdn.microsoft.com/library/3b264025-e911-4d73-90ce-992d2b9d189d)  
  
 [Практическое руководство. Выполнение запроса, возвращающего коллекцию примитивных типов](https://msdn.microsoft.com/library/115b52c0-4f27-4253-8991-284b450000b5)  
  
 [Практическое руководство. Запрос связанных объектов в EntityCollection](https://msdn.microsoft.com/library/11ce946f-16f8-4c1d-9d80-f740853807ba)  
  
 [Практическое руководство. Порядок объединения двух запросов](https://msdn.microsoft.com/library/853c583a-eaba-4400-830d-be974e735313)  
  
 [Практическое руководство. Постранично просмотреть результаты запроса](https://msdn.microsoft.com/library/ffc0f920-e7de-42e0-9b12-ef356421d030)  
  
## <a name="in-this-section"></a>В этом разделе  
 [Общие сведения об Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
  
## <a name="see-also"></a>См. также
- [ADO.NET Entity Framework](../../../../../../docs/framework/data/adonet/ef/index.md)
- [Справочник по языку](../../../../../../docs/framework/data/adonet/ef/language-reference/index.md)
