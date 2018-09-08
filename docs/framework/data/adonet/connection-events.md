---
title: События подключения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5a29de74-acfc-4134-8616-829dd7ce0710
ms.openlocfilehash: c1ef9ff9cc4d77e4951e99ed74c96cf78eb71506
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44139844"
---
# <a name="connection-events"></a>События подключения
Все поставщики данных .NET Framework имеют **подключения** объектов с двумя событиями, которые можно использовать для получения информационных сообщений из источника данных или для определения состояния **подключения** имеет изменить. В следующей таблице описаны событий **подключения** объекта.  
  
|событие|Описание|  
|-----------|-----------------|  
|**InfoMessage**|Возникает, когда из источника данных возвращается информационное сообщение. Информационные сообщения - это сообщения из источника данных, которые не приводят к формированию исключения.|  
|**StateChange**|Происходит, когда состояние **подключения** изменения.|  
  
## <a name="working-with-the-infomessage-event"></a>Работа с событием InfoMessage  
 При помощи события <xref:System.Data.SqlClient.SqlConnection.InfoMessage> объекта <xref:System.Data.SqlClient.SqlConnection> можно получать предупреждения и информационные сообщения из источника данных SQL Server. Ошибки со степенью серьезности от 11 до 16, возвращаемые из источника данных, вызывают формирование исключения. Однако событие <xref:System.Data.SqlClient.SqlConnection.InfoMessage> также можно использовать, чтобы получать сообщения из источника данных, которые не связаны с ошибками. В случае с Microsoft SQL Server любая ошибка с серьезностью 10 или меньше считается информационным сообщением, их можно отслеживать при помощи события <xref:System.Data.SqlClient.SqlConnection.InfoMessage>. Дополнительные сведения см. в разделе [степени серьезности ошибок ядра СУБД](/sql/relational-databases/errors-events/database-engine-error-severities) статьи.
  
 <xref:System.Data.SqlClient.SqlConnection.InfoMessage> Получает событие <xref:System.Data.SqlClient.SqlInfoMessageEventArgs> объект, содержащий, в его **ошибки** свойство, коллекция сообщений из источника данных. Вы можете запросить **ошибка** объекты в этой коллекции для ошибки номер и текст сообщения, а также источник ошибки. Поставщик данных .NET Framework для SQL Server также указывает сведения о базе данных, хранимой процедуре и номере строки, из которой поступило сообщение.  
  
### <a name="example"></a>Пример  
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
  
## <a name="handling-errors-as-infomessages"></a>Обработка ошибок как событий InfoMessages  
 Событие <xref:System.Data.SqlClient.SqlConnection.InfoMessage> обычно вызывается только для информационных и предупреждающих сообщений, которые отправляются с сервера. Тем не менее, когда возникает реальная ошибка, выполнение **ExecuteNonQuery** или **ExecuteReader** метод, который инициировали серверную операцию, приостанавливается и возникает исключение.  
  
 Если требуется продолжить обработку остальных инструкций команды несмотря ни на какие ошибки, выдаваемые сервером, следует задать свойству <xref:System.Data.SqlClient.SqlConnection.FireInfoMessageEventOnUserErrors%2A> объекта <xref:System.Data.SqlClient.SqlConnection> значение `true`. В этом случае соединение вызовет для ошибок событие <xref:System.Data.SqlClient.SqlConnection.InfoMessage>, а не будет формировать исключение и прерывать обработку. После этого клиентское приложение сможет обработать это событие и отреагировать на условия ошибки.  
  
> [!NOTE]
>  Ошибка со степенью серьезности 17 и выше, в результате которой сервер прекращает обработку команды, должна обрабатываться как исключение. В этом случае исключение формируется независимо от того, как обрабатывается ошибка в событии <xref:System.Data.SqlClient.SqlConnection.InfoMessage>.  
  
## <a name="working-with-the-statechange-event"></a>Работа с событием StateChange  
 **StateChange** событие возникает при состояние **подключения** изменения. **StateChange** получает событие <xref:System.Data.StateChangeEventArgs> , которые позволяют определить изменение в состоянии **подключения** с помощью **OriginalState** и **CurrentState** свойства. **OriginalState** свойство <xref:System.Data.ConnectionState> перечисление, указывающее состояние **подключения** до его изменения. **CurrentState** — <xref:System.Data.ConnectionState> перечисление, указывающее состояние **подключения** после его изменения.  
  
 В следующем примере кода используется **StateChange** событий для записи сообщения в консоль при состояние **подключения** изменения.  
  
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
  
## <a name="see-also"></a>См. также  
 [Подключение к источнику данных](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
