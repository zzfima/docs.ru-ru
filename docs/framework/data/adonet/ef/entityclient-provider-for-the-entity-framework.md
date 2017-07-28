---
title: "Поставщик EntityClient для платформы Entity Framework | Microsoft Docs"
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
ms.assetid: 8c5db787-78e6-4a34-8dc1-188bca0aca5e
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Поставщик EntityClient для платформы Entity Framework
Поставщик EntityClient \- это поставщик данных, используемый приложениями платформы Entity Framework для доступа к данным, описанным в концептуальной модели.  Дополнительные сведения о концептуальных моделях см. в разделе [Моделирование и сопоставление](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md).  В EntityClient для доступа к источнику данных используются другие поставщики данных .NET Framework.  Например, в EntityClient используется поставщик данных .NET Framework для SQL Server \(SqlClient\) при доступе к базе данных SQL Server.  Сведения о поставщике SqlClient см. в разделе [SqlClient для платформы Entity Framework](../../../../../docs/framework/data/adonet/ef/sqlclient-for-the-entity-framework.md).  Поставщик EntityClient реализован в пространстве имен <xref:System.Data.EntityClient>.  
  
## Управление подключениями  
 Инфраструктура [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] построена на основе отдельных поставщиков данных [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)] путем передачи объекта <xref:System.Data.EntityClient.EntityConnection> базовому поставщику данных и реляционной базе данных.  Конструирование объекта <xref:System.Data.EntityClient.EntityConnection> производится по ссылке на набор метаданных, содержащий необходимые модели и сопоставления, а также имя поставщика данных и строку соединения.  После создания объекта <xref:System.Data.EntityClient.EntityConnection> к сущностям можно обращаться через классы, созданные на основе концептуальной модели.  
  
 Строку соединения можно задать в файле app.config.  
  
 Пространство имен <xref:System.Data.EntityClient> включает также класс <xref:System.Data.EntityClient.EntityConnectionStringBuilder>.  Этот класс позволяет разработчикам программным способом создавать синтаксически правильные строки соединения, а также выполнять синтаксический анализ существующих строк соединения и перестраивать их с помощью свойств и методов этого класса.  Для получения дополнительной информации см. [Как построить строку соединения EntityConnection](../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md).  
  
## Создание запросов  
 Язык [!INCLUDE[esql](../../../../../includes/esql-md.md)] представляет собой независимый от хранилища диалект SQL, который работает непосредственно с концептуальными схемами сущностей и поддерживает такие понятия модели EDM, как наследование и связи.  Класс <xref:System.Data.EntityClient.EntityCommand> используется для выполнения команд языка [!INCLUDE[esql](../../../../../includes/esql-md.md)] для модели сущностей.  При конструировании объектов <xref:System.Data.EntityClient.EntityCommand> можно указать имя хранимой процедуры или текст запроса.  Платформа [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] работает с зависящими от хранилища поставщиками данных в целях преобразования общих конструкций языка [!INCLUDE[esql](../../../../../includes/esql-md.md)] в специфичные для хранилища запросы.  Дополнительные сведения о создании запросов на языке [!INCLUDE[esql](../../../../../includes/esql-md.md)] см. в разделе [Язык Entity SQL](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md).  
  
 В следующем примере создается объект <xref:System.Data.EntityClient.EntityCommand>, а текст запроса [!INCLUDE[esql](../../../../../includes/esql-md.md)] присваивается свойству <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=fullName>.  Запрос выбирает из концептуальной модели продукты, заказанные по прейскурантной цене.  Следующий код не предполагает совершенно никаких знаний о модели хранения.  
  
 `EntityCommand cmd = conn.CreateCommand();`  
  
 `cmd.CommandText = @"` `SELECT VALUE p`  
  
 `FROM AdventureWorksEntities.Product AS p`  
  
 `ORDER BY p.ListPrice ";`  
  
## Выполнение запросов  
 Во время выполнения запрос анализируется и преобразуется в каноническое дерево команд.  Вся последующая обработка выполняется над деревом команд.  Дерево команд является средством взаимодействия между объектом <xref:System.Data.EntityClient> и базовым поставщиком данных [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)], например <xref:System.Data.SqlClient>.  
  
 Объект <xref:System.Data.EntityClient.EntityDataReader> предоставляет доступ к результатам выполнения команды <xref:System.Data.EntityClient.EntityCommand> по отношению к концептуальной модели.  Для выполнения команды, возвращающей значение <xref:System.Data.EntityClient.EntityDataReader>, нужно вызвать метод <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A>.  Класс <xref:System.Data.EntityClient.EntityDataReader> реализует интерфейс <xref:System.Data.IExtendedDataRecord> для описания детально структурированных результатов.  
  
## Управление транзакциями  
 Платформа Entity Framework предлагает два способа использования транзакций: автоматический и явный.  В автоматических транзакциях используется пространство имен <xref:System.Transactions>, а в явных транзакциях \- класс <xref:System.Data.EntityClient.EntityTransaction>.  
  
 Сведения об обновлении данных, доступ к которым предоставляется с помощью концептуальной модели, см. в разделе [How to: Manage Transactions in the Entity Framework](http://msdn.microsoft.com/ru-ru/4a55eb7f-f826-4a48-9df1-aebe2352ebef).  
  
## Содержание  
 [Как построить строку соединения EntityConnection](../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)  
  
 [Как выполнить запрос, возвращающий типы\-примитивы](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)  
  
 [Как выполнить запрос, возвращающий результаты типа StructuralType](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)  
  
 [Как выполнить запрос, возвращающий результаты RefType](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-reftype-results.md)  
  
 [Как выполнить запрос, возвращающий сложные типы](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-complex-types.md)  
  
 [Как выполнить запрос, возвращающий вложенные коллекции](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-nested-collections.md)  
  
 [Как выполнить параметризованный запрос Entity SQL, использующий команды EntityCommand](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-entity-sql-query-using-entitycommand.md)  
  
 [Как выполнить параметризированную хранимую процедуру при помощи команды EntityCommand](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-stored-procedure-using-entitycommand.md)  
  
 [Как выполнить полиморфный запрос](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-polymorphic-query.md)  
  
 [Как переходить по связям с помощью оператора Navigate](../../../../../docs/framework/data/adonet/ef/how-to-navigate-relationships-with-the-navigate-operator.md)  
  
## См. также  
 [Managing Connections and Transactions](http://msdn.microsoft.com/ru-ru/b6659d2a-9a45-4e98-acaa-d7a8029e5b99)   
 [Платформа ADO.NET Entity Framework](../../../../../docs/framework/data/adonet/ef/index.md)   
 [Справочник по языку](../../../../../docs/framework/data/adonet/ef/language-reference/index.md)