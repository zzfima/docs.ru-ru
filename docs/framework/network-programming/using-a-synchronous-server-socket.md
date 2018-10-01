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
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 2e79c9a75e4513be91af1104195af3614b49092d
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2018
ms.locfileid: "47398554"
---
# <a name="using-a-synchronous-server-socket"></a><span data-ttu-id="bf61c-102">Использование синхронного сокета сервера</span><span class="sxs-lookup"><span data-stu-id="bf61c-102">Using a Synchronous Server Socket</span></span>
<span data-ttu-id="bf61c-103">Синхронные сокеты сервера приостанавливают выполнение приложения до тех пор, пока сокет не получит запрос на соединение.</span><span class="sxs-lookup"><span data-stu-id="bf61c-103">Synchronous server sockets suspend the execution of the application until a connection request is received on the socket.</span></span> <span data-ttu-id="bf61c-104">Синхронные сокеты сервера не подходят для приложений, которые сильно загружают сеть своими операциями, но они могут подходить для простых сетевых приложений.</span><span class="sxs-lookup"><span data-stu-id="bf61c-104">Synchronous server sockets are not suitable for applications that make heavy use of the network in their operation, but they can be suitable for simple network applications.</span></span>  
  
 <span data-ttu-id="bf61c-105">После настройки объекта <xref:System.Net.Sockets.Socket> для прослушивания в конечной точке с помощью методов <xref:System.Net.Sockets.Socket.Bind%2A> и <xref:System.Net.Sockets.Socket.Listen%2A> он готов принимать входящие запросы на соединение с помощью метода <xref:System.Net.Sockets.Socket.Accept%2A>.</span><span class="sxs-lookup"><span data-stu-id="bf61c-105">After a <xref:System.Net.Sockets.Socket> is set to listen on an endpoint using the <xref:System.Net.Sockets.Socket.Bind%2A> and <xref:System.Net.Sockets.Socket.Listen%2A> methods, it is ready to accept incoming connection requests using the <xref:System.Net.Sockets.Socket.Accept%2A> method.</span></span> <span data-ttu-id="bf61c-106">Работа приложения приостанавливается до тех пор, пока не будет получен запрос на соединение при вызове метода **Accept**.</span><span class="sxs-lookup"><span data-stu-id="bf61c-106">The application is suspended until a connection request is received when the **Accept** method is called.</span></span>  
  
 <span data-ttu-id="bf61c-107">При получении запроса на соединение метод **Accept** возвращает новый экземпляр **Socket**, связанный с подключающимся клиентом.</span><span class="sxs-lookup"><span data-stu-id="bf61c-107">When a connection request is received, **Accept** returns a new **Socket** instance that is associated with the connecting client.</span></span> <span data-ttu-id="bf61c-108">В приведенном ниже примере данные считываются из клиента, выводятся в консоли и отправляются обратно клиенту.</span><span class="sxs-lookup"><span data-stu-id="bf61c-108">The following example reads data from the client, displays it on the console, and echoes the data back to the client.</span></span> <span data-ttu-id="bf61c-109">Объект **Socket** не определяет протокол обмена данными, поэтому конец сообщения помечается строкой "\<EOF>".</span><span class="sxs-lookup"><span data-stu-id="bf61c-109">The **Socket** does not specify any messaging protocol, so the string "\<EOF>" marks the end of the message data.</span></span> <span data-ttu-id="bf61c-110">Предполагается, что объект **Socket** с именем `listener` инициализирован и привязан к конечной точке.</span><span class="sxs-lookup"><span data-stu-id="bf61c-110">It assumes that a **Socket** named `listener` has been initialized and bound to an endpoint.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bf61c-111">См. также</span><span class="sxs-lookup"><span data-stu-id="bf61c-111">See Also</span></span>  
 [<span data-ttu-id="bf61c-112">Использование асинхронных сокетов сервера</span><span class="sxs-lookup"><span data-stu-id="bf61c-112">Using an Asynchronous Server Socket</span></span>](../../../docs/framework/network-programming/using-an-asynchronous-server-socket.md)  
 [<span data-ttu-id="bf61c-113">Пример синхронного сокета сервера</span><span class="sxs-lookup"><span data-stu-id="bf61c-113">Synchronous Server Socket Example</span></span>](../../../docs/framework/network-programming/synchronous-server-socket-example.md)  
 [<span data-ttu-id="bf61c-114">Прослушивание с помощью сокетов</span><span class="sxs-lookup"><span data-stu-id="bf61c-114">Listening with Sockets</span></span>](../../../docs/framework/network-programming/listening-with-sockets.md)
