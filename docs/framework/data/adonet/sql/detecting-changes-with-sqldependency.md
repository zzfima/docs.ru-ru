---
title: Обнаружение изменений с использованием SqlDependency
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e6a58316-f005-4477-92e1-45cc2eb8c5b4
ms.openlocfilehash: 63d6a17e5aaf3e5d39ed0eda288e75c071be4d73
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2018
ms.locfileid: "45649950"
---
# <a name="detecting-changes-with-sqldependency"></a><span data-ttu-id="da163-102">Обнаружение изменений с использованием SqlDependency</span><span class="sxs-lookup"><span data-stu-id="da163-102">Detecting Changes with SqlDependency</span></span>
<span data-ttu-id="da163-103">Объект <xref:System.Data.SqlClient.SqlDependency> может быть связан с командой <xref:System.Data.SqlClient.SqlCommand>, чтобы определить, отличаются ли результаты запроса от исходных полученных результатов.</span><span class="sxs-lookup"><span data-stu-id="da163-103">A <xref:System.Data.SqlClient.SqlDependency> object can be associated with a <xref:System.Data.SqlClient.SqlCommand> in order to detect when query results differ from those originally retrieved.</span></span> <span data-ttu-id="da163-104">Можно также назначить делегата событию `OnChange`, которое инициируется, когда для связанной команды изменяются результаты.</span><span class="sxs-lookup"><span data-stu-id="da163-104">You can also assign a delegate to the `OnChange` event, which will fire when the results change for an associated command.</span></span> <span data-ttu-id="da163-105"><xref:System.Data.SqlClient.SqlDependency> необходимо связать с командой перед выполнением команды.</span><span class="sxs-lookup"><span data-stu-id="da163-105">You must associate the <xref:System.Data.SqlClient.SqlDependency> with the command before you execute the command.</span></span> <span data-ttu-id="da163-106">Свойство `HasChanges` зависимости <xref:System.Data.SqlClient.SqlDependency> может также использоваться для определения, изменились ли результаты запроса после первого получения данных.</span><span class="sxs-lookup"><span data-stu-id="da163-106">The `HasChanges` property of the <xref:System.Data.SqlClient.SqlDependency> can also be used to determine if the query results have changed since the data was first retrieved.</span></span>  
  
## <a name="security-considerations"></a><span data-ttu-id="da163-107">Вопросы безопасности</span><span class="sxs-lookup"><span data-stu-id="da163-107">Security Considerations</span></span>  
 <span data-ttu-id="da163-108">Инфраструктура безопасности основана на соединении <xref:System.Data.SqlClient.SqlConnection>, которое открывается при вызове <xref:System.Data.SqlClient.SqlDependency.Start%2A>, чтобы получать уведомления о том, что базовые данные изменились для данной команды.</span><span class="sxs-lookup"><span data-stu-id="da163-108">The dependency infrastructure relies on a <xref:System.Data.SqlClient.SqlConnection> that is opened when <xref:System.Data.SqlClient.SqlDependency.Start%2A> is called in order to receive notifications that the underlying data has changed for a given command.</span></span> <span data-ttu-id="da163-109">Возможность для клиента инициировать вызов `SqlDependency.Start` регулируется использованием <xref:System.Data.SqlClient.SqlClientPermission> и атрибутами управления доступом для кода.</span><span class="sxs-lookup"><span data-stu-id="da163-109">The ability for a client to initiate the call to `SqlDependency.Start` is controlled through the use of <xref:System.Data.SqlClient.SqlClientPermission> and code access security attributes.</span></span> <span data-ttu-id="da163-110">Дополнительные сведения см. в разделе [Включение уведомлений о запросах](../../../../../docs/framework/data/adonet/sql/enabling-query-notifications.md) и [управления доступом для кода и ADO.NET](../../../../../docs/framework/data/adonet/code-access-security.md).</span><span class="sxs-lookup"><span data-stu-id="da163-110">For more information, see [Enabling Query Notifications](../../../../../docs/framework/data/adonet/sql/enabling-query-notifications.md) and [Code Access Security and ADO.NET](../../../../../docs/framework/data/adonet/code-access-security.md).</span></span>  
  
### <a name="example"></a><span data-ttu-id="da163-111">Пример</span><span class="sxs-lookup"><span data-stu-id="da163-111">Example</span></span>  
 <span data-ttu-id="da163-112">Следующие шаги иллюстрируют, как объявить о зависимости, выполнить команду и получить уведомление, когда изменяется результирующий набор.</span><span class="sxs-lookup"><span data-stu-id="da163-112">The following steps illustrate how to declare a dependency, execute a command, and receive a notification when the result set changes:</span></span>  
  
1.  <span data-ttu-id="da163-113">Инициирование соединения `SqlDependency` с сервером.</span><span class="sxs-lookup"><span data-stu-id="da163-113">Initiate a `SqlDependency` connection to the server.</span></span>  
  
2.  <span data-ttu-id="da163-114">Создание объектов <xref:System.Data.SqlClient.SqlConnection> и <xref:System.Data.SqlClient.SqlCommand> для подключения к серверу и определения инструкции Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="da163-114">Create <xref:System.Data.SqlClient.SqlConnection> and <xref:System.Data.SqlClient.SqlCommand> objects to connect to the server and define a Transact-SQL statement.</span></span>  
  
3.  <span data-ttu-id="da163-115">Создание нового объекта `SqlDependency` или использование существующего объекта, привязывание его к объекту `SqlCommand`.</span><span class="sxs-lookup"><span data-stu-id="da163-115">Create a new `SqlDependency` object, or use an existing one, and bind it to the `SqlCommand` object.</span></span> <span data-ttu-id="da163-116">Внутренне это создает объект <xref:System.Data.Sql.SqlNotificationRequest>, и выполняется его привязка к объекту команды, как необходимо.</span><span class="sxs-lookup"><span data-stu-id="da163-116">Internally, this creates a <xref:System.Data.Sql.SqlNotificationRequest> object and binds it to the command object as needed.</span></span> <span data-ttu-id="da163-117">Запрос уведомления содержит внутренний идентификатор, который однозначно идентифицирует этот объект `SqlDependency`.</span><span class="sxs-lookup"><span data-stu-id="da163-117">This notification request contains an internal identifier that uniquely identifies this `SqlDependency` object.</span></span> <span data-ttu-id="da163-118">Он также запускает прослушивателя клиента, если он еще не активен.</span><span class="sxs-lookup"><span data-stu-id="da163-118">It also starts the client listener if it is not already active.</span></span>  
  
4.  <span data-ttu-id="da163-119">Подписка обработчика событий на событие `OnChange` объекта `SqlDependency`.</span><span class="sxs-lookup"><span data-stu-id="da163-119">Subscribe an event handler to the `OnChange` event of the `SqlDependency` object.</span></span>  
  
5.  <span data-ttu-id="da163-120">Выполнение команды с использованием любого метода `Execute` объекта `SqlCommand`.</span><span class="sxs-lookup"><span data-stu-id="da163-120">Execute the command using any of the `Execute` methods of the `SqlCommand` object.</span></span> <span data-ttu-id="da163-121">Так как команда привязана к объекту уведомления, сервер распознает, что она должна сформировать уведомление, и данные об очередях будут указывать на очередь зависимостей.</span><span class="sxs-lookup"><span data-stu-id="da163-121">Because the command is bound to the notification object, the server recognizes that it must generate a notification, and the queue information will point to the dependencies queue.</span></span>  
  
6.  <span data-ttu-id="da163-122">Остановка соединения `SqlDependency` с сервером.</span><span class="sxs-lookup"><span data-stu-id="da163-122">Stop the `SqlDependency` connection to the server.</span></span>  
  
 <span data-ttu-id="da163-123">Если какой-либо пользователь изменяет базовые данные, Microsoft SQL Server обнаруживает, что имеется уведомление, ожидающее это изменение, и формирует уведомление, которое обрабатывается и перенаправляется клиенту по базовому соединению `SqlConnection`, созданному вызовом `SqlDependency.Start`.</span><span class="sxs-lookup"><span data-stu-id="da163-123">If any user subsequently changes the underlying data, Microsoft SQL Server detects that there is a notification pending for such a change, and posts a notification that is processed and forwarded to the client through the underlying `SqlConnection` that was created by calling `SqlDependency.Start`.</span></span> <span data-ttu-id="da163-124">Прослушиватель клиента получает сообщение о недействительности.</span><span class="sxs-lookup"><span data-stu-id="da163-124">The client listener receives the invalidation message.</span></span> <span data-ttu-id="da163-125">Прослушиватель клиента находит связанный объект `SqlDependency` и инициирует событие `OnChange`.</span><span class="sxs-lookup"><span data-stu-id="da163-125">The client listener then locates the associated `SqlDependency` object and fires the `OnChange` event.</span></span>  
  
 <span data-ttu-id="da163-126">В следующем фрагменте кода показан шаблон конструирования, который используется для создания примера приложения.</span><span class="sxs-lookup"><span data-stu-id="da163-126">The following code fragment shows the design pattern you would use to create a sample application.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="da163-127">См. также</span><span class="sxs-lookup"><span data-stu-id="da163-127">See Also</span></span>  
 [<span data-ttu-id="da163-128">Уведомления запросов в SQL Server</span><span class="sxs-lookup"><span data-stu-id="da163-128">Query Notifications in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/query-notifications-in-sql-server.md)  
 [<span data-ttu-id="da163-129">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="da163-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
