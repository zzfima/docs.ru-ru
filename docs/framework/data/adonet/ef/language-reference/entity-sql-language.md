---
title: "Язык Entity SQL | Microsoft Docs"
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
ms.assetid: 9e7d8837-28c5-429d-a824-7bafb59724cf
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Язык Entity SQL
Entity SQL представляет собой независимый от хранилища язык запросов, аналогичный языку SQL.  Entity SQL позволяет выполнять запросы к данным сущности, представленным либо в виде объектов, либо в табличной форме.  Возможность использования Entity SQL необходимо рассматривать в следующих случаях:  
  
-   Если запрос должен создаваться динамически во время выполнения.  В этом случае следует также рассмотреть возможность использования методов построителя запросов <xref:System.Data.Objects.ObjectQuery%601> вместо создания строки запроса Entity SQL во время выполнения.  
  
-   Если требуется определить запрос как часть определения модели.  В модели данных поддерживается только Entity SQL.  Дополнительные сведения см. в разделе [QueryView Element \(MSL\)](http://msdn.microsoft.com/ru-ru/f0426b34-45cb-4fd7-9777-e0570c5e0e80).  
  
-   Если EntityClient применяется для возврата допускающих только для чтения данных сущности в виде наборов строк с использованием <xref:System.Data.EntityClient.EntityDataReader>.  Для получения дополнительной информации см. [Поставщик EntityClient для платформы Entity Framework](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).  
  
-   Для специалиста по языкам запросов на основе SQL язык Entity SQL может оказаться самым естественным выбором.  
  
## Использование Entity SQL с поставщиком EntityClient  
 Если требуется использовать Entity SQL с поставщиком EntityClient, см. дополнительные сведения в следующих разделах:  
  
 [Поставщик EntityClient для платформы Entity Framework](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)  
  
 [Как построить строку соединения EntityConnection](../../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)  
  
 [Как выполнить запрос, возвращающий типы\-примитивы](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)  
  
 [Как выполнить запрос, возвращающий результаты типа StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)  
  
 [Как выполнить запрос, возвращающий результаты RefType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-reftype-results.md)  
  
 [Как выполнить запрос, возвращающий сложные типы](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-complex-types.md)  
  
 [Как выполнить запрос, возвращающий вложенные коллекции](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-nested-collections.md)  
  
 [Как выполнить параметризованный запрос Entity SQL, использующий команды EntityCommand](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-entity-sql-query-using-entitycommand.md)  
  
 [Как выполнить параметризированную хранимую процедуру при помощи команды EntityCommand](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-stored-procedure-using-entitycommand.md)  
  
 [Как выполнить полиморфный запрос](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-polymorphic-query.md)  
  
 [Как переходить по связям с помощью оператора Navigate](../../../../../../docs/framework/data/adonet/ef/how-to-navigate-relationships-with-the-navigate-operator.md)  
  
## Использование Entity SQL с запросами объектов  
 Если требуется использовать Entity SQL с запросами объектов, см. дополнительные сведения в следующих разделах:  
  
 [How to: Execute a Query that Returns Entity Type Objects](http://msdn.microsoft.com/ru-ru/f73e137d-1534-42bb-9e31-99ca42c19b48)  
  
 [How to: Execute a Parameterized Query](http://msdn.microsoft.com/ru-ru/42048f03-c65c-4d98-b50a-3e7d537a63e8)  
  
 [How to: Navigate Relationships Using Navigation Properties](http://msdn.microsoft.com/ru-ru/b1d71c7d-16a7-4b46-96ac-690176bd5057)  
  
 [How to: Call a User\-Defined Function](http://msdn.microsoft.com/ru-ru/ad131b86-8b4e-4747-8605-d4fc64fb9d02)  
  
 [How to: Filter Data](http://msdn.microsoft.com/ru-ru/776f8556-3350-4572-804a-b1513515c1b2)  
  
 [How to: Sort Data](http://msdn.microsoft.com/ru-ru/c05f2506-cb9d-4ebc-822b-300042ad53e7)  
  
 [How to: Group Data](http://msdn.microsoft.com/ru-ru/df801d9d-9a8a-4157-97a6-5016b18998e1)  
  
 [How to: Aggregate Data](http://msdn.microsoft.com/ru-ru/4cf04ce8-3c0f-4f88-9d97-8fac8622598d)  
  
 [How to: Execute a Query that Returns Anonymous Type Objects](http://msdn.microsoft.com/ru-ru/3b264025-e911-4d73-90ce-992d2b9d189d)  
  
 [How to: Execute a Query that Returns a Collection of Primitive Types](http://msdn.microsoft.com/ru-ru/115b52c0-4f27-4253-8991-284b450000b5)  
  
 [How to: Query Related Objects in an EntityCollection](http://msdn.microsoft.com/ru-ru/11ce946f-16f8-4c1d-9d80-f740853807ba)  
  
 [How to: Order the Union of Two Queries](http://msdn.microsoft.com/ru-ru/853c583a-eaba-4400-830d-be974e735313)  
  
 [How to: Page Through Query Results](http://msdn.microsoft.com/ru-ru/ffc0f920-e7de-42e0-9b12-ef356421d030)  
  
## Содержание  
 [Общие сведения о языке Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
  
## См. также  
 [Платформа ADO.NET Entity Framework](../../../../../../docs/framework/data/adonet/ef/index.md)   
 [Справочник по языку](../../../../../../docs/framework/data/adonet/ef/language-reference/index.md)