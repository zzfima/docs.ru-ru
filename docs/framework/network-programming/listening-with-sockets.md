---
title: "Прослушивание с помощью сокетов | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "протоколы приложений, сокеты"
  - "отправка данных, сокеты"
  - "сокеты, прослушивание с помощью сокетов"
  - "запросы данных, сокеты"
  - "запрос данных из Интернета, сокеты"
  - "получение данных, сокеты"
  - "протоколы, сокеты"
  - "прослушивание с помощью сокетов"
  - "Интернет, сокеты"
ms.assetid: 40e426cc-13db-4371-95eb-f7388bd23ebf
caps.latest.revision: 10
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# Прослушивание с помощью сокетов
Сокета сервера, прослушивателя или открытии портов в сети, а затем ожидает клиента для подключения к этому порту.  Несмотря на то, что и другие семейства протоколов сетевой адрес этого примера показать, как создать удаленную службу для сети TCP\/IP.  
  
 Уникальный адрес службы протокола TCP\/IP определяется путем объединения IP\-адрес узла с номером порта службы, чтобы создать конечную точку службы.  Класс <xref:System.Net.Dns> предоставляет методы, возвращающие сведения о сетевых адресах, которое поддерживается устройством локальной сети.  Если устройство локальной сети имеет более одного сетевого адреса или если поддержки локальной системы более чем одно устройство в сети, то класс **DNS** возвращает сведения обо всех адресов сети, а приложение должно выбрать правильный адрес службы.  Internet Assigned Numbers Authority \(Iana\) определяет номер порта для общих служб \(дополнительные сведения см. в разделе www.iana.org\/assignments\/port\-numbers\).  Службы могут регистрировать другие номера портов в диапазоне от 1.024 до 65.535.  
  
 В следующем примере создается <xref:System.Net.IPEndPoint> для сервера путем объединения первый IP\-адрес, возвращаемое **DNS** для главного компьютера, номер порта выбирается из зарегистрированных номеров портов в диапазоне.  
  
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
  
 После того как локальная конечная точка определяется, <xref:System.Net.Sockets.Socket> должны быть связаны с этой конечной точкой, используя метод и набор <xref:System.Net.Sockets.Socket.Bind%2A> для прослушивания конечной точке с использованием метода <xref:System.Net.Sockets.Socket.Listen%2A>.  **Bind** выдает исключение, если указанного комбинацию адреса и порт уже используется.  В следующем примере показано связывание **Сокет** с **IPEndPoint**.  
  
```vb  
listener.Bind(localEndPoint)  
listener.Listen(100)  
```  
  
```csharp  
listener.Bind(localEndPoint);  
listener.Listen(100);  
```  
  
 Метод **Прием** принимает один параметр, указывающий разрешены количество ожидающих подключений к **Сокет**, прежде чем ошибка сервера многодельная возвращается при подключении к клиенту.  В этом случае до 100 клиентов, помещаются в очереди соединения, прежде чем ответ сервера многодельный возвращается клиенту 101.  
  
## См. также  
 [Использование синхронного сокета сервера](../../../docs/framework/network-programming/using-a-synchronous-server-socket.md)   
 [Использование асинхронных сокетов сервера](../../../docs/framework/network-programming/using-an-asynchronous-server-socket.md)   
 [Использование сокетов клиента](../../../docs/framework/network-programming/using-client-sockets.md)   
 [Практическое руководство. Создание сокета](../../../docs/framework/network-programming/how-to-create-a-socket.md)   
 [Сокеты](../../../docs/framework/network-programming/sockets.md)