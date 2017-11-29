---
title: "Поставщик EntityClient для Entity Framework"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8c5db787-78e6-4a34-8dc1-188bca0aca5e
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: eb6d8d4db676502b8c363a7d45407384333b3f22
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="entityclient-provider-for-the-entity-framework"></a>Поставщик EntityClient для Entity Framework
Поставщик EntityClient - это поставщик данных, используемый приложениями платформы Entity Framework для доступа к данным, описанным в концептуальной модели. Сведения о концептуальных моделей см. в разделе [моделирования и сопоставления](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md). В EntityClient для доступа к источнику данных используются другие поставщики данных .NET Framework. Например, в EntityClient используется поставщик данных .NET Framework для SQL Server (SqlClient) при доступе к базе данных SQL Server. Сведения о поставщике данных SqlClient см. в разделе [SqlClient для Entity Framework](../../../../../docs/framework/data/adonet/ef/sqlclient-for-the-entity-framework.md). Поставщик EntityClient реализован в пространстве имен <xref:System.Data.EntityClient>.  
  
## <a name="managing-connections"></a>Управление подключениями  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] Построения на основе отдельных [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)] поставщиков данных, предоставляя <xref:System.Data.EntityClient.EntityConnection> базового поставщика данных и реляционной базе данных. Для создания <xref:System.Data.EntityClient.EntityConnection> объекта по ссылке на набор метаданных, содержащий необходимые модели и сопоставления, а также данные, зависящие от хранилища поставщик имя и строку соединения. После <xref:System.Data.EntityClient.EntityConnection> — на месте, сущностям можно обращаться через классы, сформированные из концептуальной модели.  
  
 Строку соединения можно задать в файле app.config.  
  
 Пространство имен <xref:System.Data.EntityClient> включает также класс <xref:System.Data.EntityClient.EntityConnectionStringBuilder>. Этот класс позволяет разработчикам программным способом создавать синтаксически правильные строки соединения, а также выполнять синтаксический анализ существующих строк соединения и перестраивать их с помощью свойств и методов этого класса. Дополнительные сведения см. в разделе [как: построение строки подключения EntityConnection](../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md).  
  
## <a name="creating-queries"></a>Создание запросов  
 [!INCLUDE[esql](../../../../../includes/esql-md.md)] Язык-это независимый от хранилища диалект SQL, который работает непосредственно с концептуальными схемами сущности и поддерживает такие понятия модели EDM, как наследование и связи. <xref:System.Data.EntityClient.EntityCommand> Класс используется для выполнения [!INCLUDE[esql](../../../../../includes/esql-md.md)] команду для модели сущностей. При конструировании объектов <xref:System.Data.EntityClient.EntityCommand> можно указать имя хранимой процедуры или текст запроса. Платформа [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] работает с зависящими от хранилища поставщиками данных в целях преобразования общих конструкций языка [!INCLUDE[esql](../../../../../includes/esql-md.md)] в специфичные для хранилища запросы. Дополнительные сведения о записи [!INCLUDE[esql](../../../../../includes/esql-md.md)] запросы, в разделе [язык Entity SQL](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md).  
  
 В следующем примере создается <xref:System.Data.EntityClient.EntityCommand> объекта и назначит [!INCLUDE[esql](../../../../../includes/esql-md.md)] текст запроса его <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType> свойство. Это [!INCLUDE[esql](../../../../../includes/esql-md.md)] запросы продукты, отсортированные по прейскуранту из концептуальной модели. Следующий код не предполагает совершенно никаких знаний о модели хранения.  
  
 `EntityCommand cmd = conn.CreateCommand();`  
  
 `cmd.CommandText = @"` `SELECT VALUE p`  
  
 `FROM AdventureWorksEntities.Product AS p`  
  
 `ORDER BY p.ListPrice ";`  
  
## <a name="executing-queries"></a>Выполнение запросов  
 Во время выполнения запрос анализируется и преобразуется в каноническое дерево команд. Вся последующая обработка выполняется над деревом команд. Дерево команд является средством взаимодействия между объектом <xref:System.Data.EntityClient> и базовым поставщиком данных [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)], например <xref:System.Data.SqlClient>.  
  
 Объект <xref:System.Data.EntityClient.EntityDataReader> предоставляет доступ к результатам выполнения команды <xref:System.Data.EntityClient.EntityCommand> по отношению к концептуальной модели. Для выполнения команды, возвращающей значение <xref:System.Data.EntityClient.EntityDataReader>, нужно вызвать метод <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A>. Класс <xref:System.Data.EntityClient.EntityDataReader> реализует интерфейс <xref:System.Data.IExtendedDataRecord> для описания детально структурированных результатов.  
  
## <a name="managing-transactions"></a>Управление транзакциями  
 Платформа Entity Framework предлагает два способа использования транзакций: автоматический и явный. В автоматических транзакциях используется пространство имен <xref:System.Transactions>, а в явных транзакциях - класс <xref:System.Data.EntityClient.EntityTransaction>.  
  
 Для обновления данных, доступных через концептуальной модели. в разделе [как: управление транзакциями в Entity Framework](http://msdn.microsoft.com/en-us/4a55eb7f-f826-4a48-9df1-aebe2352ebef).  
  
## <a name="in-this-section"></a>Содержание  
 [Как: построение строки подключения EntityConnection](../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)  
  
 [Как: выполнение запроса, возвращающего результаты PrimitiveType](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)  
  
 [Как: выполнение запроса, возвращающего результаты StructuralType](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)  
  
 [Как: выполнение запроса, возвращающего результаты RefType](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-reftype-results.md)  
  
 [Как: выполнение запроса, возвращающего сложные типы](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-complex-types.md)  
  
 [Как: выполнение запроса, возвращающего вложенные коллекции](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-nested-collections.md)  
  
 [Как: выполнение параметризованного запроса Entity SQL с использованием EntityCommand](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-entity-sql-query-using-entitycommand.md)  
  
 [Как: выполнение параметризированную хранимую процедуру с использованием EntityCommand](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-stored-procedure-using-entitycommand.md)  
  
 [Как: выполнение полиморфного запроса](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-polymorphic-query.md)  
  
 [Как: перехода по связям с помощью оператора Navigate](../../../../../docs/framework/data/adonet/ef/how-to-navigate-relationships-with-the-navigate-operator.md)  
  
## <a name="see-also"></a>См. также  
 [Управление соединениями и транзакциями](http://msdn.microsoft.com/en-us/b6659d2a-9a45-4e98-acaa-d7a8029e5b99)  
 [Платформа ADO.NET Entity Framework](../../../../../docs/framework/data/adonet/ef/index.md)  
 [Справочник по языку](../../../../../docs/framework/data/adonet/ef/language-reference/index.md)
