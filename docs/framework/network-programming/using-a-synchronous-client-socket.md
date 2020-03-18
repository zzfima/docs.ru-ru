---
title: Использование синхронного сокета клиента
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application protocols, sockets
- sending data, sockets
- data requests, sockets
- requesting data from Internet, sockets
- synchronous client sockets
- Socket class, synchronous client sockets
- receiving data, sockets
- sockets, synchronous client sockets
- protocols, sockets
- Internet, sockets
- client sockets
ms.assetid: 945d00c6-7202-466c-9df9-140b84156d43
ms.openlocfilehash: fdecd18dc5975cd469e49de0eb0b55081e738cd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "71047073"
---
# <a name="using-a-synchronous-client-socket"></a>Использование синхронного сокета клиента
Синхронный сокет клиента приостанавливает работу программы, пока выполняется сетевая операция. Синхронные сокеты не подходят для приложений, которые сильно загружают сеть своими операциями, но они могут обеспечивать простой доступ к сетевым службам для других приложений.  
  
 Для отправки данных передайте массив байтов в один из методов отправки данных класса <xref:System.Net.Sockets.Socket> (<xref:System.Net.Sockets.Socket.Send%2A> и <xref:System.Net.Sockets.Socket.SendTo%2A>). В приведенном же примере строка кодируется в буфер массива байтов с помощью свойства <xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>, после чего буфер передается сетевому устройству с помощью метода **Send**. Метод **Send** возвращает количество байтов, отправленных сетевому устройству.  
  
```vb  
Dim msg As Byte() = _  
    System.Text.Encoding.ASCII.GetBytes("This is a test.")  
Dim bytesSent As Integer = s.Send(msg)  
```  
  
```csharp  
byte[] msg = System.Text.Encoding.ASCII.GetBytes("This is a test");  
int bytesSent = s.Send(msg);  
```  
  
 Метод **Send** удаляет байты из буфера и помещает их в очередь сетевого интерфейса для отправки сетевому устройству. Сетевой интерфейс может отправлять данные не сразу, однако он отправит их рано или поздно, если подключение не будет закрыто стандартным образом с помощью метода <xref:System.Net.Sockets.Socket.Shutdown%2A>.  
  
 Для получения данных от сетевого устройства необходимо передать буфер в один из методов приема данных класса **Socket** (<xref:System.Net.Sockets.Socket.Receive%2A> и <xref:System.Net.Sockets.Socket.ReceiveFrom%2A>). Синхронные сокеты приостанавливают работу приложения до тех пор, пока все байты не будут получены из сети или пока сокет не будет закрыт. В приведенном ниже примере данные принимаются из сети, а затем выводятся в консоли. В нем предполагается, что данные поступают из сети в виде текста в кодировке ASCII. Метод **Receive** возвращает количество байтов, полученных из сети.  
  
```vb  
Dim bytes(1024) As Byte  
Dim bytesRec = s.Receive(bytes)  
Console.WriteLine("Echoed text = {0}", _  
    System.Text.Encoding.ASCII.GetString(bytes, 0, bytesRec))  
```  
  
```csharp  
byte[] bytes = new byte[1024];  
int bytesRec = s.Receive(bytes);  
Console.WriteLine("Echoed text = {0}",  
    System.Text.Encoding.ASCII.GetString(bytes, 0, bytesRec));  
```  
  
 Если сокет больше не нужен, его следует освободить, вызвав метод <xref:System.Net.Sockets.Socket.Shutdown%2A>, а затем метод **Close**. В приведенном ниже примере освобождается объект **Socket**. Перечисление <xref:System.Net.Sockets.SocketShutdown> включает в себя константы, которые определяют, должен ли сокет быть закрыт для отправки данных, их получения или и того, и другого.  
  
```vb  
s.Shutdown(SocketShutdown.Both)  
s.Close()  
```  
  
```csharp  
s.Shutdown(SocketShutdown.Both);  
s.Close();  
```  
  
## <a name="see-also"></a>См. также раздел

- [Использование асинхронных сокетов клиента](using-an-asynchronous-client-socket.md)
- [Прослушивание с помощью сокетов](listening-with-sockets.md)
- [Пример синхронного сокета клиента](synchronous-client-socket-example.md)
