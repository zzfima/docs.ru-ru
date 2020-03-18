---
title: прослушивание с помощью сокетов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application protocols, sockets
- sending data, sockets
- sockets, listening with sockets
- data requests, sockets
- requesting data from Internet, sockets
- receiving data, sockets
- protocols, sockets
- listening with sockets
- Internet, sockets
ms.assetid: 40e426cc-13db-4371-95eb-f7388bd23ebf
ms.openlocfilehash: cf8316ede6888b99a8b0c87cfa3426b33be18b7f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "79180743"
---
# <a name="listening-with-sockets"></a>прослушивание с помощью сокетов
Сокеты прослушивателя и сервера открывают порт в сети и ожидают, когда клиент подключится к этому порту. В этом примере показано, как создать удаленную службу для сети TCP/IP (хотя существуют и другие семейства сетевых адресов и протоколов).  
  
 Уникальный адрес службы TCP/IP определяется сочетанием IP-адреса узла и номера порта службы, которые используются при создании конечной точки службы. Класс <xref:System.Net.Dns> предоставляет методы, возвращающие сведения о сетевых адресах, поддерживаемых локальным сетевым устройством. Если локальное сетевое устройство имеет более одного сетевого адреса или локальная система поддерживает несколько сетевых устройств, класс **Dns** возвращает сведения обо всех сетевых адресах, и приложению необходимо выбрать соответствующий адрес службы. Номера портов для основных служб определяются организацией IANA ("Администрация адресного пространства Интернет"). Дополнительные сведения см. в разделе [Реестр названий служб и номеров портов транспортных протоколов](https://www.iana.org/assignments/port-numbers). Другие службы могут использовать номера портов в диапазоне от 1024 до 65535.  
  
 В следующем примере создается <xref:System.Net.IPEndPoint> для сервера с помощью объединения первого IP-адреса, возвращенного классом **Dns** для компьютера узла, и номера порта, выбранного из диапазона зарегистрированных номеров портов.  
  
```vb  
Dim ipHostInfo As IPHostEntry = Dns.GetHostEntry(Dns.GetHostName())  
Dim ipAddress As IPAddress = ipHostInfo.AddressList(0)  
Dim localEndPoint As New IPEndPoint(ipAddress, 11000)  
```  
  
```csharp  
IPHostEntry ipHostInfo = Dns.GetHostEntry(Dns.GetHostName());  
IPAddress ipAddress = ipHostInfo.AddressList[0];  
IPEndPoint localEndPoint = new IPEndPoint(ipAddress, 11000);  
```  
  
 После определения локальной конечной точки необходимо связать <xref:System.Net.Sockets.Socket> с этой конечной точкой с помощью метода <xref:System.Net.Sockets.Socket.Bind%2A> и включить прослушивание для конечной точки с помощью метода <xref:System.Net.Sockets.Socket.Listen%2A>. Метод **Bind** выдает исключение, если указанное сочетание IP-адреса и порта уже используется. В следующем примере показано связывание сокета **Socket** с конечной точкой **IPEndPoint**.  
  
```vb  
Dim listener As New Socket(ipAddress.AddressFamily, _  
    SocketType.Stream, ProtocolType.Tcp)
listener.Bind(localEndPoint)  
listener.Listen(100)  
```  
  
```csharp  
Socket listener = new Socket(ipAddress.AddressFamily,
    SocketType.Stream, ProtocolType.Tcp);
listener.Bind(localEndPoint);  
listener.Listen(100);  
```  
  
 Метод **Listen** принимает один параметр, который определяет максимальное количество ожидающих подключений для сокета **Socket**. При превышении этого количества клиенту возвращается ошибка "Сервер занят". В данном случае в очередь на подключение размещается до 100 клиентов. 101 клиенту возвращается ответ "Сервер занят".  
  
## <a name="see-also"></a>См. также раздел

- [Использование синхронного сокета сервера](using-a-synchronous-server-socket.md)
- [Использование асинхронных сокетов сервера](using-an-asynchronous-server-socket.md)
- [Использование сокетов клиента](using-client-sockets.md)
- [Практическое руководство. Создание сокета](how-to-create-a-socket.md)
- [Сокеты](sockets.md)
