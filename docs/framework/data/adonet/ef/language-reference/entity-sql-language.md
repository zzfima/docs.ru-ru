---
title: Язык Entity SQL
ms.date: 03/30/2017
ms.assetid: 9e7d8837-28c5-429d-a824-7bafb59724cf
ms.openlocfilehash: a2e4b7245dbfccf7864481b52a0e868a85efbca6
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251018"
---
# <a name="entity-sql-language"></a>Язык Entity SQL
Entity SQL представляет собой независимый от хранилища язык запросов, аналогичный языку SQL. Entity SQL позволяет выполнять запросы к данным сущности, представленным либо в виде объектов, либо в табличной форме. Возможность использования Entity SQL необходимо рассматривать в следующих случаях:  
  
- Если запрос должен создаваться динамически во время выполнения. В этом случае следует также рассмотреть возможность использования методов построителя запросов <xref:System.Data.Objects.ObjectQuery%601> вместо создания строки запроса Entity SQL во время выполнения.  
  
- Если требуется определить запрос как часть определения модели. В модели данных поддерживается только Entity SQL. Дополнительные сведения см. в разделе [QueryView Element (MSL)](/ef/ef6/modeling/designer/advanced/edmx/msl-spec#queryview-element-msl) .  
  
- Если EntityClient применяется для возврата допускающих только для чтения данных сущности в виде наборов строк с использованием <xref:System.Data.EntityClient.EntityDataReader>. Дополнительные сведения см. [в разделе Поставщик EntityClient для Entity Framework](../entityclient-provider-for-the-entity-framework.md).  
  
- Для специалиста по языкам запросов на основе SQL язык Entity SQL может оказаться самым естественным выбором.  
  
## <a name="using-entity-sql-with-the-entityclient-provider"></a>Использование Entity SQL с поставщиком EntityClient  
 Если требуется использовать Entity SQL с поставщиком EntityClient, см. дополнительные сведения в следующих разделах:  
  
 [Поставщик EntityClient для Entity Framework](../entityclient-provider-for-the-entity-framework.md)  
  
 [Практическое руководство. Создание строки подключения EntityConnection](../how-to-build-an-entityconnection-connection-string.md)  
  
 [Практическое руководство. Выполнение запроса, возвращающего результаты тип PrimitiveType](../how-to-execute-a-query-that-returns-primitivetype-results.md)  
  
 [Практическое руководство. Выполнение запроса, возвращающего результаты Структуралтипе](../how-to-execute-a-query-that-returns-structuraltype-results.md)  
  
 [Практическое руководство. Выполнение запроса, возвращающего результаты Рефтипе](../how-to-execute-a-query-that-returns-reftype-results.md)  
  
 [Практическое руководство. Выполнение запроса, возвращающего сложные типы](../how-to-execute-a-query-that-returns-complex-types.md)  
  
 [Практическое руководство. Выполнение запроса, возвращающего вложенные коллекции](../how-to-execute-a-query-that-returns-nested-collections.md)  
  
 [Практическое руководство. Выполнение параметризованного Entity SQL запроса с помощью команды EntityCommand](../how-to-execute-a-parameterized-entity-sql-query-using-entitycommand.md)  
  
 [Практическое руководство. Выполнение параметризованной хранимой процедуры с помощью EntityCommand](../how-to-execute-a-parameterized-stored-procedure-using-entitycommand.md)  
  
 [Практическое руководство. Выполнение полиморфизма запроса](../how-to-execute-a-polymorphic-query.md)  
  
 [Практическое руководство. Навигация по связям с помощью оператора Navigate](../how-to-navigate-relationships-with-the-navigate-operator.md)  
  
## <a name="using-entity-sql-with-object-queries"></a>Использование Entity SQL с запросами объектов  
 Если требуется использовать Entity SQL с запросами объектов, см. дополнительные сведения в следующих разделах:  
  
 [Практическое руководство. Выполнение запроса, возвращающего объекты типа сущности](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738694(v=vs.100))  
  
 [Практическое руководство. Выполнение параметризованного запроса](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738521(v=vs.100))  
  
 [Практическое руководство. Навигация по связям с помощью свойств навигации](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896321(v=vs.100))  
  
 [Практическое руководство. Вызов определяемой пользователем функции](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100))  
  
 [Практическое руководство. Фильтрация данных](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716755(v=vs.100))  
  
 [Практическое руководство. Сортировка данных](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716784(v=vs.100))  
  
 [Практическое руководство. Данные группы](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896341(v=vs.100))  
  
 [Практическое руководство. Статистические данные](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716738(v=vs.100))  
  
 [Практическое руководство. Выполнение запроса, возвращающего объекты анонимного типа](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738512(v=vs.100))  
  
 [Практическое руководство. Выполнение запроса, возвращающего коллекцию типов-примитивов](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738451(v=vs.100))  
  
 [Практическое руководство. Запросы к связанным объектам в EntityCollection](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716708(v=vs.100))  
  
 [Практическое руководство. Упорядочение объединения двух запросов](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896299(v=vs.100))  
  
 [Практическое руководство. Страница с результатами запроса](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))  
  
## <a name="in-this-section"></a>В этом разделе  
 [Общие сведения об Entity SQL](entity-sql-overview.md)  
  
 [Справочник по Entity SQL](entity-sql-reference.md)  
  
## <a name="see-also"></a>См. также

- [ADO.NET Entity Framework](../index.md)
- [Справочник по языку](index.md)
