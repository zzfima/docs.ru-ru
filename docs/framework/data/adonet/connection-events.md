---
title: События подключения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5a29de74-acfc-4134-8616-829dd7ce0710
ms.openlocfilehash: 8ed62d0193639b434d66c446e3b9d0c184577a80
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69949565"
---
# <a name="connection-events"></a>События подключения
Все поставщики данных .NET Framework имеют объекты **соединения** с двумя событиями, которые можно использовать для получения информационных сообщений из источника данных или для определения, изменилось ли состояние **соединения** . В следующей таблице описаны события объекта **Connection** .  
  
|событие|Описание|  
|-----------|-----------------|  
|**InfoMessage**|Возникает, когда из источника данных возвращается информационное сообщение. Информационные сообщения - это сообщения из источника данных, которые не приводят к формированию исключения.|  
|**StateChange**|Происходит при изменении состояния **соединения** .|  
  
## <a name="working-with-the-infomessage-event"></a>Работа с событием InfoMessage  
 При помощи события <xref:System.Data.SqlClient.SqlConnection.InfoMessage> объекта <xref:System.Data.SqlClient.SqlConnection> можно получать предупреждения и информационные сообщения из источника данных SQL Server. Ошибки со степенью серьезности от 11 до 16, возвращаемые из источника данных, вызывают формирование исключения. Однако событие <xref:System.Data.SqlClient.SqlConnection.InfoMessage> также можно использовать, чтобы получать сообщения из источника данных, которые не связаны с ошибками. В случае с Microsoft SQL Server любая ошибка с серьезностью 10 или меньше считается информационным сообщением, их можно отслеживать при помощи события <xref:System.Data.SqlClient.SqlConnection.InfoMessage>. Дополнительные сведения см. в статье [ядро СУБД серьезности ошибок](/sql/relational-databases/errors-events/database-engine-error-severities) .
  
 Событие получает объект, содержащий в его свойстве Errors коллекцию сообщений из источника данных. <xref:System.Data.SqlClient.SqlConnection.InfoMessage> <xref:System.Data.SqlClient.SqlInfoMessageEventArgs> Вы можете запросить объекты **ошибок** в этой коллекции, чтобы получить номер ошибки и текст сообщения, а также источник ошибки. Поставщик данных .NET Framework для SQL Server также указывает сведения о базе данных, хранимой процедуре и номере строки, из которой поступило сообщение.  
  
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
 Событие <xref:System.Data.SqlClient.SqlConnection.InfoMessage> обычно вызывается только для информационных и предупреждающих сообщений, которые отправляются с сервера. Однако при возникновении фактической ошибки выполнение метода **ExecuteNonQuery** или **ExecuteReader** , инициировавшего операцию сервера, останавливается и создается исключение.  
  
 Если требуется продолжить обработку остальных инструкций команды несмотря ни на какие ошибки, выдаваемые сервером, следует задать свойству <xref:System.Data.SqlClient.SqlConnection.FireInfoMessageEventOnUserErrors%2A> объекта <xref:System.Data.SqlClient.SqlConnection> значение `true`. В этом случае соединение вызовет для ошибок событие <xref:System.Data.SqlClient.SqlConnection.InfoMessage>, а не будет формировать исключение и прерывать обработку. После этого клиентское приложение сможет обработать это событие и отреагировать на условия ошибки.  
  
> [!NOTE]
> Ошибка со степенью серьезности 17 и выше, в результате которой сервер прекращает обработку команды, должна обрабатываться как исключение. В этом случае исключение формируется независимо от того, как обрабатывается ошибка в событии <xref:System.Data.SqlClient.SqlConnection.InfoMessage>.  
  
## <a name="working-with-the-statechange-event"></a>Работа с событием StateChange  
 Событие **StateChange** возникает при изменении состояния **соединения** . Событие **StateChange** получает <xref:System.Data.StateChangeEventArgs> , позволяющее определить изменение состояния **соединения** с помощью свойств **оригиналстате** и **CurrentState** . Свойство **оригиналстате** — <xref:System.Data.ConnectionState> это перечисление, которое указывает состояние **соединения** до его изменения. **CurrentState** — <xref:System.Data.ConnectionState> это перечисление, указывающее состояние **соединения** после его изменения.  
  
 В следующем примере кода событие **StateChange** используется для записи сообщения в консоль при изменении состояния **соединения** .  
  
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

- [Подключение к источнику данных](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
