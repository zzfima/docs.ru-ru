---
title: "прослушивание с помощью сокетов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
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
caps.latest.revision: 10
author: mcleblanc
ms.author: markl
manager: markl
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 66c3a64a12e791cedbd4e978de2c1b6e06eabb98
ms.contentlocale: ru-ru
ms.lasthandoff: 08/21/2017

---
# <a name="listening-with-sockets"></a>прослушивание с помощью сокетов
Сокеты прослушивателя и сервера открывают порт в сети и ожидают, когда клиент подключится к этому порту. В этом примере показано, как создать удаленную службу для сети TCP/IP (хотя существуют и другие семейства сетевых адресов и протоколов).  
  
 Уникальный адрес службы TCP/IP определяется сочетанием IP-адреса узла и номера порта службы, которые используются при создании конечной точки службы. Класс <xref:System.Net.Dns> предоставляет методы, возвращающие сведения о сетевых адресах, поддерживаемых локальным сетевым устройством. Если локальное сетевое устройство имеет более одного сетевого адреса или локальная система поддерживает несколько сетевых устройств, класс **Dns** возвращает сведения обо всех сетевых адресах, и приложению необходимо выбрать соответствующий адрес службы. Номера портов для основных служб определяются организацией IANA ("Администрация адресного пространства Интернет"). Дополнительные сведения см. на странице www.iana.org/assignments/port-numbers. Другие службы могут использовать номера портов в диапазоне от 1024 до 65535.  
  
 В следующем примере создается <xref:System.Net.IPEndPoint> для сервера с помощью объединения первого IP-адреса, возвращенного классом **Dns** для компьютера узла, и номера порта, выбранного из диапазона зарегистрированных номеров портов.  
  
```vb  
Dim ipHostInfo As IPHostEntry = Dns.Resolve(Dns.GetHostName())  
Dim ipAddress As IPAddress = ipHostInfo.AddressList(0)  
Dim localEndPoint As New IPEndPoint(ipAddress, 11000)  
```  
  
```csharp  
IPHostEntry ipHostInfo = Dns.Resolve(Dns.GetHostName());  
IPAddress ipAddress = ipHostInfo.AddressList[0];  
IPEndPoint localEndPoint = new IPEndPoint(ipAddress, 11000);  
```  
  
 После определения локальной конечной точки необходимо связать <xref:System.Net.Sockets.Socket> с этой конечной точкой с помощью метода <xref:System.Net.Sockets.Socket.Bind%2A> и включить прослушивание для конечной точки с помощью метода <xref:System.Net.Sockets.Socket.Listen%2A>. Метод **Bind** выдает исключение, если указанное сочетание IP-адреса и порта уже используется. В следующем примере показано связывание сокета **Socket** с конечной точкой **IPEndPoint**.  
  
```vb  
listener.Bind(localEndPoint)  
listener.Listen(100)  
```  
  
```csharp  
listener.Bind(localEndPoint);  
listener.Listen(100);  
```  
  
 Метод **Listen** принимает один параметр, который определяет максимальное количество ожидающих подключений для сокета **Socket**. При превышении этого количества клиенту возвращается ошибка "Сервер занят". В данном случае в очередь на подключение размещается до 100 клиентов. 101 клиенту возвращается ответ "Сервер занят".  
  
## <a name="see-also"></a>См. также  
 [Использование синхронного сокета сервера](../../../docs/framework/network-programming/using-a-synchronous-server-socket.md)   
 [Использование асинхронных сокетов сервера](../../../docs/framework/network-programming/using-an-asynchronous-server-socket.md)   
 [Использование сокетов клиента](../../../docs/framework/network-programming/using-client-sockets.md)   
 [Практическое руководство. Создание сокета](../../../docs/framework/network-programming/how-to-create-a-socket.md)   
 [Сокеты](../../../docs/framework/network-programming/sockets.md)

