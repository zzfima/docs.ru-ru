---
title: "События подключения"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 5a29de74-acfc-4134-8616-829dd7ce0710
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: d4d6a818f3173780cee2f8a01b9f66804cd2969b
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="connection-events"></a><span data-ttu-id="dca03-102">События подключения</span><span class="sxs-lookup"><span data-stu-id="dca03-102">Connection Events</span></span>
<span data-ttu-id="dca03-103">Все поставщики данных .NET Framework имеют **подключения** объектов с двумя событиями, которые можно использовать для получения информационных сообщений из источника данных или для определения состояния **подключения** имеет изменить.</span><span class="sxs-lookup"><span data-stu-id="dca03-103">All of the .NET Framework data providers have **Connection** objects with two events that you can use to retrieve informational messages from a data source or to determine if the state of a **Connection** has changed.</span></span> <span data-ttu-id="dca03-104">В следующей таблице описаны события **подключения** объекта.</span><span class="sxs-lookup"><span data-stu-id="dca03-104">The following table describes the events of the **Connection** object.</span></span>  
  
|<span data-ttu-id="dca03-105">событие</span><span class="sxs-lookup"><span data-stu-id="dca03-105">Event</span></span>|<span data-ttu-id="dca03-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="dca03-106">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="dca03-107">**InfoMessage**</span><span class="sxs-lookup"><span data-stu-id="dca03-107">**InfoMessage**</span></span>|<span data-ttu-id="dca03-108">Возникает, когда из источника данных возвращается информационное сообщение.</span><span class="sxs-lookup"><span data-stu-id="dca03-108">Occurs when an informational message is returned from a data source.</span></span> <span data-ttu-id="dca03-109">Информационные сообщения - это сообщения из источника данных, которые не приводят к формированию исключения.</span><span class="sxs-lookup"><span data-stu-id="dca03-109">Informational messages are messages from a data source that do not result in an exception being thrown.</span></span>|  
|<span data-ttu-id="dca03-110">**StateChange**</span><span class="sxs-lookup"><span data-stu-id="dca03-110">**StateChange**</span></span>|<span data-ttu-id="dca03-111">Происходит, когда состояние **подключения** изменения.</span><span class="sxs-lookup"><span data-stu-id="dca03-111">Occurs when the state of the **Connection** changes.</span></span>|  
  
## <a name="working-with-the-infomessage-event"></a><span data-ttu-id="dca03-112">Работа с событием InfoMessage</span><span class="sxs-lookup"><span data-stu-id="dca03-112">Working with the InfoMessage Event</span></span>  
 <span data-ttu-id="dca03-113">При помощи события <xref:System.Data.SqlClient.SqlConnection.InfoMessage> объекта <xref:System.Data.SqlClient.SqlConnection> можно получать предупреждения и информационные сообщения из источника данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dca03-113">You can retrieve warnings and informational messages from a SQL Server data source using the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event of the <xref:System.Data.SqlClient.SqlConnection> object.</span></span> <span data-ttu-id="dca03-114">Ошибки со степенью серьезности от 11 до 16, возвращаемые из источника данных, вызывают формирование исключения.</span><span class="sxs-lookup"><span data-stu-id="dca03-114">Errors returned from the data source with a severity level of 11 through 16 cause an exception to be thrown.</span></span> <span data-ttu-id="dca03-115">Однако событие <xref:System.Data.SqlClient.SqlConnection.InfoMessage> также можно использовать, чтобы получать сообщения из источника данных, которые не связаны с ошибками.</span><span class="sxs-lookup"><span data-stu-id="dca03-115">However, the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event can be used to obtain messages from the data source that are not associated with an error.</span></span> <span data-ttu-id="dca03-116">В случае с Microsoft SQL Server любая ошибка с серьезностью 10 или меньше считается информационным сообщением, их можно отслеживать при помощи события <xref:System.Data.SqlClient.SqlConnection.InfoMessage>.</span><span class="sxs-lookup"><span data-stu-id="dca03-116">In the case of Microsoft SQL Server, any error with a severity of 10 or less is considered to be an informational message, and can be captured by using the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event.</span></span> <span data-ttu-id="dca03-117">Дополнительные сведения см. в разделе «Степени серьезности сообщений об ошибках» электронной документации по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dca03-117">For more information, see the "Error Message Severity Levels" topic in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="dca03-118"><xref:System.Data.SqlClient.SqlConnection.InfoMessage> Событие получает <xref:System.Data.SqlClient.SqlInfoMessageEventArgs> объект, содержащий, в его **ошибки** свойство, коллекция сообщений из источника данных.</span><span class="sxs-lookup"><span data-stu-id="dca03-118">The <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event receives an <xref:System.Data.SqlClient.SqlInfoMessageEventArgs> object containing, in its **Errors** property, a collection of the messages from the data source.</span></span> <span data-ttu-id="dca03-119">Вы можете запрашивать **ошибка** объектов в этой коллекции для ошибки номер и текст сообщения, а также источник ошибки.</span><span class="sxs-lookup"><span data-stu-id="dca03-119">You can query the **Error** objects in this collection for the error number and message text, as well as the source of the error.</span></span> <span data-ttu-id="dca03-120">Поставщик данных .NET Framework для SQL Server также указывает сведения о базе данных, хранимой процедуре и номере строки, из которой поступило сообщение.</span><span class="sxs-lookup"><span data-stu-id="dca03-120">The .NET Framework Data Provider for SQL Server also includes detail about the database, stored procedure, and line number that the message came from.</span></span>  
  
### <a name="example"></a><span data-ttu-id="dca03-121">Пример</span><span class="sxs-lookup"><span data-stu-id="dca03-121">Example</span></span>  
 <span data-ttu-id="dca03-122">В следующем примере кода показано, как добавлять обработчик для события <xref:System.Data.SqlClient.SqlConnection.InfoMessage>.</span><span class="sxs-lookup"><span data-stu-id="dca03-122">The following code example shows how to add an event handler for the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event.</span></span>  
  
```vb  
' Assumes that connection represents a SqlConnection object.  
  AddHandler connection.InfoMessage, _  
    New SqlInfoMessageEventHandler(AddressOf OnInfoMessage)  
  
Private Shared Sub OnInfoMessage(sender As Object, _  
  args As SqlInfoMessageEventArgs)  
  Dim err As SqlError  
  For Each err In args.Errors  
    Console.WriteLine("The {0} has received a severity {1}, _  
       state {2} error number {3}\n" & _  
      "on line {4} of procedure {5} on server {6}:\n{7}", _  
      err.Source, err.Class, err.State, err.Number, err.LineNumber, _  
    err.Procedure, err.Server, err.Message)  
  Next  
End Sub  
```  
  
```csharp  
// Assumes that connection represents a SqlConnection object.  
  connection.InfoMessage +=   
    new SqlInfoMessageEventHandler(OnInfoMessage);  
  
protected static void OnInfoMessage(  
  object sender, SqlInfoMessageEventArgs args)  
{  
  foreach (SqlError err in args.Errors)  
  {  
    Console.WriteLine(  
  "The {0} has received a severity {1}, state {2} error number {3}\n" +  
  "on line {4} of procedure {5} on server {6}:\n{7}",  
   err.Source, err.Class, err.State, err.Number, err.LineNumber,   
   err.Procedure, err.Server, err.Message);  
  }  
}  
```  
  
## <a name="handling-errors-as-infomessages"></a><span data-ttu-id="dca03-123">Обработка ошибок как событий InfoMessages</span><span class="sxs-lookup"><span data-stu-id="dca03-123">Handling Errors as InfoMessages</span></span>  
 <span data-ttu-id="dca03-124">Событие <xref:System.Data.SqlClient.SqlConnection.InfoMessage> обычно вызывается только для информационных и предупреждающих сообщений, которые отправляются с сервера.</span><span class="sxs-lookup"><span data-stu-id="dca03-124">The <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event will normally fire only for informational and warning messages that are sent from the server.</span></span> <span data-ttu-id="dca03-125">Тем не менее, когда фактический возникает ошибка, выполнение **ExecuteNonQuery** или **ExecuteReader** методом, который инициировал операцию на сервере прерывается и создается исключение.</span><span class="sxs-lookup"><span data-stu-id="dca03-125">However, when an actual error occurs, the execution of the **ExecuteNonQuery** or **ExecuteReader** method that initiated the server operation is halted and an exception is thrown.</span></span>  
  
 <span data-ttu-id="dca03-126">Если требуется продолжить обработку остальных инструкций команды несмотря ни на какие ошибки, выдаваемые сервером, следует задать свойству <xref:System.Data.SqlClient.SqlConnection.FireInfoMessageEventOnUserErrors%2A> объекта <xref:System.Data.SqlClient.SqlConnection> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="dca03-126">If you want to continue processing the rest of the statements in a command regardless of any errors produced by the server, set the <xref:System.Data.SqlClient.SqlConnection.FireInfoMessageEventOnUserErrors%2A> property of the <xref:System.Data.SqlClient.SqlConnection> to `true`.</span></span> <span data-ttu-id="dca03-127">В этом случае соединение вызовет для ошибок событие <xref:System.Data.SqlClient.SqlConnection.InfoMessage>, а не будет формировать исключение и прерывать обработку.</span><span class="sxs-lookup"><span data-stu-id="dca03-127">Doing this causes the connection to fire the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event for errors instead of throwing an exception and interrupting processing.</span></span> <span data-ttu-id="dca03-128">После этого клиентское приложение сможет обработать это событие и отреагировать на условия ошибки.</span><span class="sxs-lookup"><span data-stu-id="dca03-128">The client application can then handle this event and respond to error conditions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dca03-129">Ошибка со степенью серьезности 17 и выше, в результате которой сервер прекращает обработку команды, должна обрабатываться как исключение.</span><span class="sxs-lookup"><span data-stu-id="dca03-129">An error with a severity level of 17 or above that causes the server to stop processing the command must be handled as an exception.</span></span> <span data-ttu-id="dca03-130">В этом случае исключение формируется независимо от того, как обрабатывается ошибка в событии <xref:System.Data.SqlClient.SqlConnection.InfoMessage>.</span><span class="sxs-lookup"><span data-stu-id="dca03-130">In this case, an exception is thrown regardless of how the error is handled in the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event.</span></span>  
  
## <a name="working-with-the-statechange-event"></a><span data-ttu-id="dca03-131">Работа с событием StateChange</span><span class="sxs-lookup"><span data-stu-id="dca03-131">Working with the StateChange Event</span></span>  
 <span data-ttu-id="dca03-132">**StateChange** событие возникает при состояние **подключения** изменения.</span><span class="sxs-lookup"><span data-stu-id="dca03-132">The **StateChange** event occurs when the state of a **Connection** changes.</span></span> <span data-ttu-id="dca03-133">**StateChange** событие получает <xref:System.Data.StateChangeEventArgs> , которые позволяют определить изменение в состоянии **подключения** с помощью **OriginalState** и **CurrentState** свойства.</span><span class="sxs-lookup"><span data-stu-id="dca03-133">The **StateChange** event receives <xref:System.Data.StateChangeEventArgs> that enable you to determine the change in state of the **Connection** by using the **OriginalState** and **CurrentState** properties.</span></span> <span data-ttu-id="dca03-134">**OriginalState** свойство <xref:System.Data.ConnectionState> значение перечисления, указывающее состояние **подключения** до его изменения.</span><span class="sxs-lookup"><span data-stu-id="dca03-134">The **OriginalState** property is a <xref:System.Data.ConnectionState> enumeration that indicates the state of the **Connection** before it changed.</span></span> <span data-ttu-id="dca03-135">**CurrentState** — <xref:System.Data.ConnectionState> значение перечисления, указывающее состояние **подключения** после его изменения.</span><span class="sxs-lookup"><span data-stu-id="dca03-135">**CurrentState** is a <xref:System.Data.ConnectionState> enumeration that indicates the state of the **Connection** after it changed.</span></span>  
  
 <span data-ttu-id="dca03-136">Следующий пример кода использует **StateChange** событий для записи сообщения в консоль при состояние **подключения** изменения.</span><span class="sxs-lookup"><span data-stu-id="dca03-136">The following code example uses the **StateChange** event to write a message to the console when the state of the **Connection** changes.</span></span>  
  
```vb  
' Assumes connection represents a SqlConnection object.  
  AddHandler connection.StateChange, _  
    New StateChangeEventHandler(AddressOf OnStateChange)  
  
Protected Shared Sub OnStateChange( _  
  sender As Object, args As StateChangeEventArgs)  
  
  Console.WriteLine( _  
  "The current Connection state has changed from {0} to {1}.", _  
  args.OriginalState, args.CurrentState)  
End Sub  
```  
  
```csharp  
// Assumes connection represents a SqlConnection object.  
  connection.StateChange  += new StateChangeEventHandler(OnStateChange);  
  
protected static void OnStateChange(object sender,   
  StateChangeEventArgs args)  
{  
  Console.WriteLine(  
    "The current Connection state has changed from {0} to {1}.",  
      args.OriginalState, args.CurrentState);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="dca03-137">См. также</span><span class="sxs-lookup"><span data-stu-id="dca03-137">See Also</span></span>  
 [<span data-ttu-id="dca03-138">Подключение к источнику данных</span><span class="sxs-lookup"><span data-stu-id="dca03-138">Connecting to a Data Source</span></span>](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [<span data-ttu-id="dca03-139">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="dca03-139">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
