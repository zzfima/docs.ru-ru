---
title: Поставщик EntityClient для Entity Framework
ms.date: 03/30/2017
ms.assetid: 8c5db787-78e6-4a34-8dc1-188bca0aca5e
ms.openlocfilehash: 70cc5a9aaa22cc563c910f9d250ad4565e34a135
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251602"
---
# <a name="entityclient-provider-for-the-entity-framework"></a>Поставщик EntityClient для Entity Framework
Поставщик EntityClient - это поставщик данных, используемый приложениями платформы Entity Framework для доступа к данным, описанным в концептуальной модели. Дополнительные сведения о концептуальных моделях см. в разделе [моделирование и сопоставление](modeling-and-mapping.md). В EntityClient для доступа к источнику данных используются другие поставщики данных .NET Framework. Например, в EntityClient используется поставщик данных .NET Framework для SQL Server (SqlClient) при доступе к базе данных SQL Server. Дополнительные сведения о поставщике SqlClient см. [в разделе SqlClient для Entity Framework](sqlclient-for-the-entity-framework.md). Поставщик EntityClient реализован в пространстве имен <xref:System.Data.EntityClient>.  
  
## <a name="managing-connections"></a>Управление подключениями  
 Сборки на основе поставщиков данных ADO.NET, специфичных <xref:System.Data.EntityClient.EntityConnection> для хранилища, предоставляют базовому поставщику данных и реляционной базе данных. [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] Для создания <xref:System.Data.EntityClient.EntityConnection> объекта необходимо сослаться на набор метаданных, содержащий необходимые модели и сопоставление, а также имя поставщика данных и строку подключения для конкретного хранилища. <xref:System.Data.EntityClient.EntityConnection> После завершения можно получить доступ к сущностям через классы, созданные из концептуальной модели.  
  
 Строку соединения можно задать в файле app.config.  
  
 Пространство имен <xref:System.Data.EntityClient> включает также класс <xref:System.Data.EntityClient.EntityConnectionStringBuilder>. Этот класс позволяет разработчикам программным способом создавать синтаксически правильные строки соединения, а также выполнять синтаксический анализ существующих строк соединения и перестраивать их с помощью свойств и методов этого класса. Дополнительные сведения см. в разделе [Практическое руководство. Создайте строку](how-to-build-an-entityconnection-connection-string.md)подключения EntityConnection.  
  
## <a name="creating-queries"></a>Создание запросов  
 [!INCLUDE[esql](../../../../../includes/esql-md.md)] Язык является независимым от хранилища диалектом SQL, который работает непосредственно с концептуальными схемами сущностей и поддерживает EDM таких концепций, как наследование и отношения. Класс используется для [!INCLUDE[esql](../../../../../includes/esql-md.md)] выполнения команды в модели сущностей. <xref:System.Data.EntityClient.EntityCommand> При конструировании объектов <xref:System.Data.EntityClient.EntityCommand> можно указать имя хранимой процедуры или текст запроса. Платформа [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] работает с зависящими от хранилища поставщиками данных в целях преобразования общих конструкций языка [!INCLUDE[esql](../../../../../includes/esql-md.md)] в специфичные для хранилища запросы. Дополнительные сведения о написании [!INCLUDE[esql](../../../../../includes/esql-md.md)] запросов см. в разделе [язык Entity SQL](./language-reference/entity-sql-language.md).  
  
 В следующем примере создается <xref:System.Data.EntityClient.EntityCommand> объект и присваивается [!INCLUDE[esql](../../../../../includes/esql-md.md)] его <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType> свойству текст запроса. Этот [!INCLUDE[esql](../../../../../includes/esql-md.md)] запрос запрашивает продукты, упорядоченные по прейскурантной цене, из концептуальной модели. Следующий код не предполагает совершенно никаких знаний о модели хранения.  
  
 ```csharp
EntityCommand cmd = conn.CreateCommand();
cmd.CommandText = @"SELECT VALUE p
  FROM AdventureWorksEntities.Product AS p
  ORDER BY p.ListPrice";
```
  
## <a name="executing-queries"></a>Выполнение запросов  
 Во время выполнения запрос анализируется и преобразуется в каноническое дерево команд. Вся последующая обработка выполняется над деревом команд. Дерево команд — это средства взаимодействия между <xref:System.Data.EntityClient> и базовым .NET Framework поставщиком данных, <xref:System.Data.SqlClient>например.  
  
 Объект <xref:System.Data.EntityClient.EntityDataReader> предоставляет доступ к результатам выполнения команды <xref:System.Data.EntityClient.EntityCommand> по отношению к концептуальной модели. Для выполнения команды, возвращающей значение <xref:System.Data.EntityClient.EntityDataReader>, нужно вызвать метод <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A>. Класс <xref:System.Data.EntityClient.EntityDataReader> реализует интерфейс <xref:System.Data.IExtendedDataRecord> для описания детально структурированных результатов.  
  
## <a name="managing-transactions"></a>Управление транзакциями  
 Платформа Entity Framework предлагает два способа использования транзакций: автоматический и явный. В автоматических транзакциях используется пространство имен <xref:System.Transactions>, а в явных транзакциях - класс <xref:System.Data.EntityClient.EntityTransaction>.  
  
 Сведения об обновлении данных, предоставляемых с помощью концептуальной модели [, см. в разделе как Управление транзакциями в Entity Framework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738523(v=vs.100)).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Практическое руководство. Создание строки подключения EntityConnection](how-to-build-an-entityconnection-connection-string.md)  
  
 [Практическое руководство. Выполнение запроса, возвращающего результаты тип PrimitiveType](how-to-execute-a-query-that-returns-primitivetype-results.md)  
  
 [Практическое руководство. Выполнение запроса, возвращающего результаты Структуралтипе](how-to-execute-a-query-that-returns-structuraltype-results.md)  
  
 [Практическое руководство. Выполнение запроса, возвращающего результаты Рефтипе](how-to-execute-a-query-that-returns-reftype-results.md)  
  
 [Практическое руководство. Выполнение запроса, возвращающего сложные типы](how-to-execute-a-query-that-returns-complex-types.md)  
  
 [Практическое руководство. Выполнение запроса, возвращающего вложенные коллекции](how-to-execute-a-query-that-returns-nested-collections.md)  
  
 [Практическое руководство. Выполнение параметризованного Entity SQL запроса с помощью команды EntityCommand](how-to-execute-a-parameterized-entity-sql-query-using-entitycommand.md)  
  
 [Практическое руководство. Выполнение параметризованной хранимой процедуры с помощью EntityCommand](how-to-execute-a-parameterized-stored-procedure-using-entitycommand.md)  
  
 [Практическое руководство. Выполнение полиморфизма запроса](how-to-execute-a-polymorphic-query.md)  
  
 [Практическое руководство. Навигация по связям с помощью оператора Navigate](how-to-navigate-relationships-with-the-navigate-operator.md)  
  
## <a name="see-also"></a>См. также

- [Управление соединениями и транзакциями](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896325(v=vs.100))
- [ADO.NET Entity Framework](index.md)
- [Справочник по языку](./language-reference/index.md)
