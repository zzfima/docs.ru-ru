---
title: "Использование сокетов клиента | Microsoft Docs"
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
  - "запросы данных, сокеты"
  - "запрос данных из Интернета, сокеты"
  - "получение данных, сокеты"
  - "класс Socket, сокеты клиента"
  - "протоколы, сокеты"
  - "Интернет, сокеты"
  - "сокеты, сокеты клиента"
  - "сокеты клиента"
ms.assetid: 81de9f59-8177-4d98-b25d-43fc32a98383
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# Использование сокетов клиента
Прежде чем начать диалог между <xref:System.Net.Sockets.Socket> необходимо создать канал данных между приложением и удаленный устройством.  Несмотря на то, что и другие семейства протоколов сетевой адрес этого примера показать, как создать соединение TCP\/IP к удаленной службе.  
  
 Протокол TCP\/IP использует сетевой адрес и номер порта службы для уникальной идентификации службы.  Сетевой адрес идентифицирует конкретные устройство в сети; номер порта указывается внешний вид обслуживания на этом устройстве для подключения.  Порт сетевого адреса и службы сочетания вызвать конечной точкой, которая представлена в платформе .NET Framework классом <xref:System.Net.EndPoint>.  Потомок **EndPoint** определен для каждого поддерживаемого семейства адресов. для семейства IP\-адрес, класс <xref:System.Net.IPEndPoint>.  
  
 Класс <xref:System.Net.Dns> предоставляет службы доменного имени приложения, использующие службы интернета TCP\/IP.  Метод <xref:System.Net.Dns.Resolve%2A> запрашивает DNS\-сервер для сопоставления дружественное имя домена \(например, "host.contoso.com"\) в числовые адреса в интернете \(например, 192.168.1.1\).  **Resolve** возвращает [IPHostEnty](frlrfsystemnetiphostentryclasstopic), содержащее список адресов и псевдонимов для имени.  В большинстве случаев можно использовать первый возвращенный адрес в массиве <xref:System.Net.IPHostEntry.AddressList%2A>.  Следующий код возвращает <xref:System.Net.IPAddress>, содержащий IP\-адрес для сервера host.contoso.com.  
  
```vb  
Dim ipHostInfo As IPHostEntry = Dns.Resolve("host.contoso.com")  
Dim ipAddress As IPAddress = ipHostInfo.AddressList(0)  
  
```  
  
```csharp  
IPHostEntry ipHostInfo = Dns.Resolve("host.contoso.com");  
IPAddress ipAddress = ipHostInfo.AddressList[0];  
```  
  
 Internet Assigned Numbers Authority \(Iana\) определяет номер порта для общих служб \(дополнительные сведения см. в разделе www.iana.org\/assignments\/port\-numbers\).  Службы могут регистрировать другие номера портов в диапазоне от 1.024 до 65.535.  Следующий код объединяет IP\-адрес host.contoso.com с номером порта для создания удаленная конечная точка соединения.  
  
```vb  
Dim ipe As New IPEndPoint(ipAddress, 11000)  
  
```  
  
```csharp  
IPEndPoint ipe = new IPEndPoint(ipAddress,11000);  
```  
  
 После определения устройства и выбрать адрес удаленного порта, используемый для соединения, приложение может попытаться установить соединение с удаленным устройством.  Следующий пример использует существующее **IPEndPoint**, чтобы подключиться к удаленному устройство и перехватывает все исключения, которые вызываются.  
  
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
  
## См. также  
 [Использование синхронного сокета клиента](../../../docs/framework/network-programming/using-a-synchronous-client-socket.md)   
 [Использование асинхронных сокетов клиента](../../../docs/framework/network-programming/using-an-asynchronous-client-socket.md)   
 [Практическое руководство. Создание сокета](../../../docs/framework/network-programming/how-to-create-a-socket.md)   
 [Сокеты](../../../docs/framework/network-programming/sockets.md)