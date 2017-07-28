---
title: "События соединений | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5a29de74-acfc-4134-8616-829dd7ce0710
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# События соединений
Все поставщики данных платформы .NET Framework имеют объекты **Connection** с двумя событиями, которые можно использовать для получения информационных сообщений из источника данных или для определения того, изменилось ли состояние объекта **Connection**.  В следующей таблице описываются события объекта **Connection**.  
  
|Событие|Описание|  
|-------------|--------------|  
|**InfoMessage**|Возникает, когда из источника данных возвращается информационное сообщение.  Информационные сообщения \- это сообщения из источника данных, которые не приводят к формированию исключения.|  
|**StateChange**|Возникает при изменении состояния объекта **Connection**.|  
  
## Работа с событием InfoMessage  
 При помощи события <xref:System.Data.SqlClient.SqlConnection.InfoMessage> объекта <xref:System.Data.SqlClient.SqlConnection> можно получать предупреждения и информационные сообщения из источника данных SQL Server.  Ошибки со степенью серьезности от 11 до 16, возвращаемые из источника данных, вызывают формирование исключения.  Однако событие <xref:System.Data.SqlClient.SqlConnection.InfoMessage> также можно использовать, чтобы получать сообщения из источника данных, которые не связаны с ошибками.  В случае с Microsoft SQL Server любая ошибка с серьезностью 10 или меньше считается информационным сообщением, их можно отслеживать при помощи события <xref:System.Data.SqlClient.SqlConnection.InfoMessage>.  Дополнительные сведения см. в разделе «Степени серьезности сообщений об ошибках» электронной документации по SQL Server.  
  
 Событие <xref:System.Data.SqlClient.SqlConnection.InfoMessage> принимает объект <xref:System.Data.SqlClient.SqlInfoMessageEventArgs>, в свойстве **Errors** которого содержится коллекция сообщений из источника данных.  В объектах **Error** этой коллекции можно запрашивать номер ошибки и текст сообщения, а также сведения об источнике ошибки.  Поставщик данных .NET Framework для SQL Server также указывает сведения о базе данных, хранимой процедуре и номере строки, из которой поступило сообщение.  
  
### Пример  
 В следующем примере кода показано, как добавлять обработчик для события <xref:System.Data.SqlClient.SqlConnection.InfoMessage>.  
  
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
  
## Обработка ошибок как событий InfoMessages  
 Событие <xref:System.Data.SqlClient.SqlConnection.InfoMessage> обычно вызывается только для информационных и предупреждающих сообщений, которые отправляются с сервера.  Однако когда возникает реальная ошибка, выполнение методов **ExecuteNonQuery** или **ExecuteReader**, которые инициировали серверную операцию, приостанавливается и формируется исключение.  
  
 Если требуется продолжить обработку остальных инструкций команды несмотря ни на какие ошибки, выдаваемые сервером, следует задать свойству <xref:System.Data.SqlClient.SqlConnection.FireInfoMessageEventOnUserErrors%2A> объекта <xref:System.Data.SqlClient.SqlConnection> значение `true`.  В этом случае соединение вызовет для ошибок событие <xref:System.Data.SqlClient.SqlConnection.InfoMessage>, а не будет формировать исключение и прерывать обработку.  После этого клиентское приложение сможет обработать это событие и отреагировать на условия ошибки.  
  
> [!NOTE]
>  Ошибка со степенью серьезности 17 и выше, в результате которой сервер прекращает обработку команды, должна обрабатываться как исключение.  В этом случае исключение формируется независимо от того, как обрабатывается ошибка в событии <xref:System.Data.SqlClient.SqlConnection.InfoMessage>.  
  
## Работа с событием StateChange  
 Событие **StateChange** возникает при изменении состояния объекта **Connection**.  Событие **StateChange** воспринимается объектом <xref:System.Data.StateChangeEventArgs>, который позволяет определять состояние объекта **Connection** при помощи свойств **OriginalState** и **CurrentState**.  Свойство **OriginalState** является перечислением <xref:System.Data.ConnectionState>, которое указывает состояние объекта **Connection** до его изменения.  Свойство **CurrentState** является перечислением <xref:System.Data.ConnectionState>, которое указывает состояние объекта **Connection** после его изменения.  
  
 В следующем примере кода событие **StateChange** используется, чтобы написать сообщение в консольном окне при изменении состояния объекта **Connection**.  
  
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
  
## См. также  
 [Подключение к источнику данных](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)