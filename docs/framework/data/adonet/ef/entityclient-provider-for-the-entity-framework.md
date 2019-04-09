---
title: Поставщик EntityClient для Entity Framework
ms.date: 03/30/2017
ms.assetid: 8c5db787-78e6-4a34-8dc1-188bca0aca5e
ms.openlocfilehash: b8de4e36351a93858104a99045c5aeecce9d2997
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59169680"
---
# <a name="entityclient-provider-for-the-entity-framework"></a>Поставщик EntityClient для Entity Framework
Поставщик EntityClient - это поставщик данных, используемый приложениями платформы Entity Framework для доступа к данным, описанным в концептуальной модели. Сведения о концептуальной модели, см. в разделе [моделирования и сопоставления](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md). В EntityClient для доступа к источнику данных используются другие поставщики данных .NET Framework. Например, в EntityClient используется поставщик данных .NET Framework для SQL Server (SqlClient) при доступе к базе данных SQL Server. Сведения о поставщике SqlClient см. в разделе [SqlClient для Entity Framework](../../../../../docs/framework/data/adonet/ef/sqlclient-for-the-entity-framework.md). Поставщик EntityClient реализован в пространстве имен <xref:System.Data.EntityClient>.  
  
## <a name="managing-connections"></a>Управление подключениями  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] Построен на основе конкретного хранилища [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)] поставщики данных, предоставляя <xref:System.Data.EntityClient.EntityConnection> к базовому поставщику данных и реляционной базы данных. Для создания <xref:System.Data.EntityClient.EntityConnection> объекта, необходимо указать ссылку на набор метаданных, содержащий необходимые модели и сопоставления, а также строку подключения и имя поставщика данных. После <xref:System.Data.EntityClient.EntityConnection> находится в месте, сущностям может осуществляться через классы, сформированные из концептуальной модели.  
  
 Строку соединения можно задать в файле app.config.  
  
 Пространство имен <xref:System.Data.EntityClient> включает также класс <xref:System.Data.EntityClient.EntityConnectionStringBuilder>. Этот класс позволяет разработчикам программным способом создавать синтаксически правильные строки соединения, а также выполнять синтаксический анализ существующих строк соединения и перестраивать их с помощью свойств и методов этого класса. Дополнительные сведения см. в разделе [Как Построить строку соединения EntityConnection](../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md).  
  
## <a name="creating-queries"></a>Создание запросов  
 [!INCLUDE[esql](../../../../../includes/esql-md.md)] Язык — независимый от хранилища диалект SQL, который работает непосредственно с концептуальными схемами сущностей и поддерживает основные понятия модели EDM, таких как наследование и связи. <xref:System.Data.EntityClient.EntityCommand> Класс используется для выполнения [!INCLUDE[esql](../../../../../includes/esql-md.md)] команду для модели сущностей. При конструировании объектов <xref:System.Data.EntityClient.EntityCommand> можно указать имя хранимой процедуры или текст запроса. Платформа [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] работает с зависящими от хранилища поставщиками данных в целях преобразования общих конструкций языка [!INCLUDE[esql](../../../../../includes/esql-md.md)] в специфичные для хранилища запросы. Дополнительные сведения о записи [!INCLUDE[esql](../../../../../includes/esql-md.md)] запросы, см. в разделе [язык Entity SQL](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md).  
  
 В следующем примере создается <xref:System.Data.EntityClient.EntityCommand> объекта и назначит [!INCLUDE[esql](../../../../../includes/esql-md.md)] текст запроса его <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType> свойство. Это [!INCLUDE[esql](../../../../../includes/esql-md.md)] запрос запрашивает продукты, заказанные по прейскурантной цене из концептуальной модели. Следующий код не предполагает совершенно никаких знаний о модели хранения.  
  
 ```csharp
EntityCommand cmd = conn.CreateCommand();
cmd.CommandText = @"SELECT VALUE p
  FROM AdventureWorksEntities.Product AS p
  ORDER BY p.ListPrice";
```
  
## <a name="executing-queries"></a>Выполнение запросов  
 Во время выполнения запрос анализируется и преобразуется в каноническое дерево команд. Вся последующая обработка выполняется над деревом команд. Дерево команд является средством взаимодействия между объектом <xref:System.Data.EntityClient> и базовым поставщиком данных [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)], например <xref:System.Data.SqlClient>.  
  
 Объект <xref:System.Data.EntityClient.EntityDataReader> предоставляет доступ к результатам выполнения команды <xref:System.Data.EntityClient.EntityCommand> по отношению к концептуальной модели. Для выполнения команды, возвращающей значение <xref:System.Data.EntityClient.EntityDataReader>, нужно вызвать метод <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A>. Класс <xref:System.Data.EntityClient.EntityDataReader> реализует интерфейс <xref:System.Data.IExtendedDataRecord> для описания детально структурированных результатов.  
  
## <a name="managing-transactions"></a>Управление транзакциями  
 Платформа Entity Framework предлагает два способа использования транзакций: автоматический и явный. В автоматических транзакциях используется пространство имен <xref:System.Transactions>, а в явных транзакциях - класс <xref:System.Data.EntityClient.EntityTransaction>.  
  
 Для обновления данных, доступных через концептуальную модель, см. в разделе [как: Управление транзакциями в Entity Framework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738523(v=vs.100)).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Практическое руководство. Сборка строки соединения EntityConnection](../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)  
  
 [Практическое руководство. Выполнение запроса, возвращающего типы-примитивы](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)  
  
 [Практическое руководство. Выполнение запроса, возвращающего результаты типа StructuralType](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)  
  
 [Практическое руководство. Выполнение запроса, возвращающего результаты RefType](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-reftype-results.md)  
  
 [Практическое руководство. Выполнение запроса, возвращающего сложные типы](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-complex-types.md)  
  
 [Практическое руководство. Выполнение запроса, возвращающего вложенные коллекции](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-nested-collections.md)  
  
 [Практическое руководство. Выполнение SQL-запроса к параметрическому объекту с использованием EntityCommand](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-entity-sql-query-using-entitycommand.md)  
  
 [Практическое руководство. Выполнение параметризованной хранимой процедуры с использованием EntityCommand](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-stored-procedure-using-entitycommand.md)  
  
 [Практическое руководство. Выполнение полиморфного запроса](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-polymorphic-query.md)  
  
 [Практическое руководство. Переход по отношениям с помощью оператора Navigate](../../../../../docs/framework/data/adonet/ef/how-to-navigate-relationships-with-the-navigate-operator.md)  
  
## <a name="see-also"></a>См. также

- [Управление подключениями и транзакциями](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896325(v=vs.100))
- [ADO.NET Entity Framework](../../../../../docs/framework/data/adonet/ef/index.md)
- [Справочник по языку](../../../../../docs/framework/data/adonet/ef/language-reference/index.md)
