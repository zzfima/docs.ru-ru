---
title: Язык Entity SQL
ms.date: 03/30/2017
ms.assetid: 9e7d8837-28c5-429d-a824-7bafb59724cf
ms.openlocfilehash: b26d9a88130e0449d437ae9dd88e5e818f29f54d
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55826230"
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
  
 [Практическое руководство. Выполнение запроса, возвращающего объекты типа сущностей](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738694(v=vs.100))  
  
 [Практическое руководство. Выполнение параметризованного запроса](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738521(v=vs.100))  
  
 [Практическое руководство. Переход по отношениям с помощью свойств навигации](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896321(v=vs.100))  
  
 [Практическое руководство. Вызов определяемой пользователем функции](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100))  
  
 [Практическое руководство. Фильтрация данных](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716755(v=vs.100))  
  
 [Практическое руководство. Сортировка данных](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716784(v=vs.100))  
  
 [Практическое руководство. Группы данных](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896341(v=vs.100))  
  
 [Практическое руководство. Сводные данные](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716738(v=vs.100))  
  
 [Практическое руководство. Выполнение запроса, возвращающего объекты анонимного типа](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738512(v=vs.100))  
  
 [Практическое руководство. Выполнение запроса, возвращающего коллекцию примитивных типов](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738451(v=vs.100))  
  
 [Практическое руководство. Запрос связанных объектов в EntityCollection](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716708(v=vs.100))  
  
 [Практическое руководство. Порядок объединения двух запросов](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896299(v=vs.100))  
  
 [Практическое руководство. Постранично просмотреть результаты запроса](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))  
  
## <a name="in-this-section"></a>В этом разделе  
 [Общие сведения об Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
  
## <a name="see-also"></a>См. также
- [ADO.NET Entity Framework](../../../../../../docs/framework/data/adonet/ef/index.md)
- [Справочник по языку](../../../../../../docs/framework/data/adonet/ef/language-reference/index.md)
