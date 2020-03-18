---
title: Использование синхронного сокета сервера
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application protocols, sockets
- synchronous server sockets
- sending data, sockets
- data requests, sockets
- requesting data from Internet, sockets
- server sockets
- receiving data, sockets
- Socket class, synchronous server sockets
- protocols, sockets
- sockets, synchronous server sockets
- Internet, sockets
ms.assetid: d1ce882e-653e-41f5-9289-844ec855b804
ms.openlocfilehash: cbc02c755ceefa8f31439f121a98978b82f33fa2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "71047032"
---
# <a name="using-a-synchronous-server-socket"></a>Использование синхронного сокета сервера
Синхронные сокеты сервера приостанавливают выполнение приложения до тех пор, пока сокет не получит запрос на соединение. Синхронные сокеты сервера не подходят для приложений, которые сильно загружают сеть своими операциями, но они могут подходить для простых сетевых приложений.  
  
 После настройки объекта <xref:System.Net.Sockets.Socket> для прослушивания в конечной точке с помощью методов <xref:System.Net.Sockets.Socket.Bind%2A> и <xref:System.Net.Sockets.Socket.Listen%2A> он готов принимать входящие запросы на соединение с помощью метода <xref:System.Net.Sockets.Socket.Accept%2A>. Работа приложения приостанавливается до тех пор, пока не будет получен запрос на соединение при вызове метода **Accept**.  
  
 При получении запроса на соединение метод **Accept** возвращает новый экземпляр **Socket**, связанный с подключающимся клиентом. В приведенном ниже примере данные считываются из клиента, выводятся в консоли и отправляются обратно клиенту. Объект **Socket** не определяет протокол обмена данными, поэтому конец сообщения помечается строкой "\<EOF>". Предполагается, что объект **Socket** с именем `listener` инициализирован и привязан к конечной точке.  
  
```vb  
Console.WriteLine("Waiting for a connection...")  
Dim handler As Socket = listener.Accept()  
Dim data As String = Nothing  
  
While True  
    bytes = New Byte(1024) {}  
    Dim bytesRec As Integer = handler.Receive(bytes)  
    data += Encoding.ASCII.GetString(bytes, 0, bytesRec)  
    If data.IndexOf("<EOF>") > - 1 Then  
        Exit While  
    End If  
End While  
  
Console.WriteLine("Text received : {0}", data)  
  
Dim msg As Byte() = Encoding.ASCII.GetBytes(data)  
handler.Send(msg)  
handler.Shutdown(SocketShutdown.Both)  
handler.Close()  
```  
  
```csharp  
Console.WriteLine("Waiting for a connection...");  
Socket handler = listener.Accept();  
String data = null;  
  
while (true) {  
    bytes = new byte[1024];  
    int bytesRec = handler.Receive(bytes);  
    data += Encoding.ASCII.GetString(bytes,0,bytesRec);  
    if (data.IndexOf("<EOF>") > -1) {  
        break;  
    }  
}  
  
Console.WriteLine( "Text received : {0}", data);  
  
byte[] msg = Encoding.ASCII.GetBytes(data);  
handler.Send(msg);  
handler.Shutdown(SocketShutdown.Both);  
handler.Close();  
```  
  
## <a name="see-also"></a>См. также раздел

- [Использование асинхронных сокетов сервера](using-an-asynchronous-server-socket.md)
- [Пример синхронного сокета сервера](synchronous-server-socket-example.md)
- [Прослушивание с помощью сокетов](listening-with-sockets.md)
