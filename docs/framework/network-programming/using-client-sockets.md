---
title: "Использование сокетов клиента"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application protocols, sockets
- sending data, sockets
- data requests, sockets
- requesting data from Internet, sockets
- receiving data, sockets
- Socket class, client sockets
- protocols, sockets
- Internet, sockets
- sockets, client sockets
- client sockets
ms.assetid: 81de9f59-8177-4d98-b25d-43fc32a98383
caps.latest.revision: "12"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 3df78be14da96d0bb7b8875a5c7532c003d1dbc8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="using-client-sockets"></a>Использование сокетов клиента
Перед инициацией взаимодействия через <xref:System.Net.Sockets.Socket> необходимо создать канал передачи данных между приложением и удаленным устройством. В этом примере показано, как создать подключение TCP/IP к удаленном устройству (хотя существуют и другие семейства сетевых адресов и протоколы).  
  
 В качестве уникального идентификатора службы протокол TCP/IP использует сетевой адрес и номер порта службы. Сетевой адрес определяет конкретное устройство в сети, а номер порта — службу на этом устройстве, к которой необходимо подключиться. Сочетание сетевого адреса и порта службы называется конечной точкой. Она представлена в платформе .NET Framework классом <xref:System.Net.EndPoint>. Для каждого поддерживаемого семейства адресов определен потомок **EndPoint**. Для семейства IP-адресов это класс <xref:System.Net.IPEndPoint>.  
  
 Класс <xref:System.Net.Dns> предоставляет службы доменных имен (DNS) для приложений, использующих интернет-службы TCP/IP. Метод <xref:System.Net.Dns.Resolve%2A> отправляет DNS-серверу запрос на сопоставление понятного доменного имени (например, host.contoso.com) с адресом в Интернете в числовой форме (например, 192.168.1.1). Метод **Resolve** возвращает объект <xref:System.Net.IPHostEntry>, который содержит список адресов и псевдонимов, соответствующих запрошенному имени. В большинстве случаев можно использовать первый адрес из возвращенного массива <xref:System.Net.IPHostEntry.AddressList%2A>. Приведенный ниже код получает объект <xref:System.Net.IPAddress>, содержащий IP-адрес сервера host.contoso.com.  
  
```vb  
Dim ipHostInfo As IPHostEntry = Dns.Resolve("host.contoso.com")  
Dim ipAddress As IPAddress = ipHostInfo.AddressList(0)  
```  
  
```csharp  
IPHostEntry ipHostInfo = Dns.Resolve("host.contoso.com");  
IPAddress ipAddress = ipHostInfo.AddressList[0];  
```  
  
 Номера портов для основных служб определяются организацией IANA ("Администрация адресного пространства Интернет"). Дополнительные сведения см. на странице www.iana.org/assignments/port-numbers. Другие службы могут использовать номера портов в диапазоне от 1024 до 65535. Приведенный ниже код объединяет IP-адрес сервера host.contoso.com с номером порта для формирования удаленной конечной точки, к которой необходимо подключиться.  
  
```vb  
Dim ipe As New IPEndPoint(ipAddress, 11000)  
```  
  
```csharp  
IPEndPoint ipe = new IPEndPoint(ipAddress,11000);  
```  
  
 Определив адрес удаленного устройства и выбрав порт для подключения, приложение может попытаться установить соединение с удаленным устройством. В приведенном ниже примере существующий объект **IPEndPoint** используется для подключения к удаленному устройству. Кроме того, перехватываются все возникающие исключения.  
  
```vb  
Try  
    s.Connect(ipe)  
Catch ae As ArgumentNullException  
    Console.WriteLine("ArgumentNullException : {0}", _  
        ae.ToString())  
Catch se As SocketException  
    Console.WriteLine("SocketException : {0}", se.ToString())  
Catch e As Exception  
    Console.WriteLine("Unexpected exception : {0}", e.ToString())  
End Try  
```  
  
```csharp  
try {  
    s.Connect(ipe);  
} catch(ArgumentNullException ae) {  
    Console.WriteLine("ArgumentNullException : {0}", ae.ToString());  
} catch(SocketException se) {  
    Console.WriteLine("SocketException : {0}", se.ToString());  
} catch(Exception e) {  
    Console.WriteLine("Unexpected exception : {0}", e.ToString());  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Использование синхронного сокета клиента](../../../docs/framework/network-programming/using-a-synchronous-client-socket.md)  
 [Использование асинхронных сокетов клиента](../../../docs/framework/network-programming/using-an-asynchronous-client-socket.md)  
 [Практическое руководство. Создание сокета](../../../docs/framework/network-programming/how-to-create-a-socket.md)  
 [Сокеты](../../../docs/framework/network-programming/sockets.md)
