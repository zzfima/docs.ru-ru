---
title: Обнаружение изменений с использованием SqlDependency
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e6a58316-f005-4477-92e1-45cc2eb8c5b4
ms.openlocfilehash: 63d6a17e5aaf3e5d39ed0eda288e75c071be4d73
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44183776"
---
# <a name="detecting-changes-with-sqldependency"></a>Обнаружение изменений с использованием SqlDependency
Объект <xref:System.Data.SqlClient.SqlDependency> может быть связан с командой <xref:System.Data.SqlClient.SqlCommand>, чтобы определить, отличаются ли результаты запроса от исходных полученных результатов. Можно также назначить делегата событию `OnChange`, которое инициируется, когда для связанной команды изменяются результаты. <xref:System.Data.SqlClient.SqlDependency> необходимо связать с командой перед выполнением команды. Свойство `HasChanges` зависимости <xref:System.Data.SqlClient.SqlDependency> может также использоваться для определения, изменились ли результаты запроса после первого получения данных.  
  
## <a name="security-considerations"></a>Вопросы безопасности  
 Инфраструктура безопасности основана на соединении <xref:System.Data.SqlClient.SqlConnection>, которое открывается при вызове <xref:System.Data.SqlClient.SqlDependency.Start%2A>, чтобы получать уведомления о том, что базовые данные изменились для данной команды. Возможность для клиента инициировать вызов `SqlDependency.Start` регулируется использованием <xref:System.Data.SqlClient.SqlClientPermission> и атрибутами управления доступом для кода. Дополнительные сведения см. в разделе [Включение уведомлений о запросах](../../../../../docs/framework/data/adonet/sql/enabling-query-notifications.md) и [управления доступом для кода и ADO.NET](../../../../../docs/framework/data/adonet/code-access-security.md).  
  
### <a name="example"></a>Пример  
 Следующие шаги иллюстрируют, как объявить о зависимости, выполнить команду и получить уведомление, когда изменяется результирующий набор.  
  
1.  Инициирование соединения `SqlDependency` с сервером.  
  
2.  Создание объектов <xref:System.Data.SqlClient.SqlConnection> и <xref:System.Data.SqlClient.SqlCommand> для подключения к серверу и определения инструкции Transact-SQL.  
  
3.  Создание нового объекта `SqlDependency` или использование существующего объекта, привязывание его к объекту `SqlCommand`. Внутренне это создает объект <xref:System.Data.Sql.SqlNotificationRequest>, и выполняется его привязка к объекту команды, как необходимо. Запрос уведомления содержит внутренний идентификатор, который однозначно идентифицирует этот объект `SqlDependency`. Он также запускает прослушивателя клиента, если он еще не активен.  
  
4.  Подписка обработчика событий на событие `OnChange` объекта `SqlDependency`.  
  
5.  Выполнение команды с использованием любого метода `Execute` объекта `SqlCommand`. Так как команда привязана к объекту уведомления, сервер распознает, что она должна сформировать уведомление, и данные об очередях будут указывать на очередь зависимостей.  
  
6.  Остановка соединения `SqlDependency` с сервером.  
  
 Если какой-либо пользователь изменяет базовые данные, Microsoft SQL Server обнаруживает, что имеется уведомление, ожидающее это изменение, и формирует уведомление, которое обрабатывается и перенаправляется клиенту по базовому соединению `SqlConnection`, созданному вызовом `SqlDependency.Start`. Прослушиватель клиента получает сообщение о недействительности. Прослушиватель клиента находит связанный объект `SqlDependency` и инициирует событие `OnChange`.  
  
 В следующем фрагменте кода показан шаблон конструирования, который используется для создания примера приложения.  
  
```vb  
Sub Initialization()  
    ' Create a dependency connection.  
    SqlDependency.Start(connectionString, queueName)  
End Sub  
  
Sub SomeMethod()   
    ' Assume connection is an open SqlConnection.  
    ' Create a new SqlCommand object.  
    Using command As New SqlCommand( _  
      "SELECT ShipperID, CompanyName, Phone FROM dbo.Shippers", _  
      connection)  
  
        ' Create a dependency and associate it with the SqlCommand.  
        Dim dependency As New SqlDependency(command)  
        ' Maintain the refence in a class member.  
        ' Subscribe to the SqlDependency event.  
        AddHandler dependency.OnChange, AddressOf OnDependencyChange  
  
        ' Execute the command.  
        Using reader = command.ExecuteReader()  
            ' Process the DataReader.  
        End Using  
    End Using  
End Sub   
  
' Handler method  
Sub OnDependencyChange(ByVal sender As Object, _  
    ByVal e As SqlNotificationEventArgs)   
    ' Handle the event (for example, invalidate this cache entry).  
End Sub  
  
Sub Termination()  
    ' Release the dependency  
    SqlDependency.Stop(connectionString, queueName)  
End Sub  
```  
  
```csharp  
void Initialization()  
{  
    // Create a dependency connection.  
    SqlDependency.Start(connectionString, queueName);  
}  
  
void SomeMethod()  
{  
    // Assume connection is an open SqlConnection.  
  
    // Create a new SqlCommand object.  
    using (SqlCommand command=new SqlCommand(  
        "SELECT ShipperID, CompanyName, Phone FROM dbo.Shippers",   
        connection))  
    {  
  
        // Create a dependency and associate it with the SqlCommand.  
        SqlDependency dependency=new SqlDependency(command);  
        // Maintain the reference in a class member.  
  
        // Subscribe to the SqlDependency event.  
        dependency.OnChange+=new  
           OnChangeEventHandler(OnDependencyChange);  
  
        // Execute the command.  
        using (SqlDataReader reader = command.ExecuteReader())  
        {  
            // Process the DataReader.  
        }  
    }  
}  
  
// Handler method  
void OnDependencyChange(object sender,   
   SqlNotificationEventArgs e )  
{  
  // Handle the event (for example, invalidate this cache entry).  
}  
  
void Termination()  
{  
    // Release the dependency.  
    SqlDependency.Stop(connectionString, queueName);  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Уведомления запросов в SQL Server](../../../../../docs/framework/data/adonet/sql/query-notifications-in-sql-server.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
