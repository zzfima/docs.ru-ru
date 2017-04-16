---
title: "Использование синхронного сокета клиента | Microsoft Docs"
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
  - "синхронные сокеты клиента"
  - "класс Socket, синхронные сокеты клиента"
  - "получение данных, сокеты"
  - "сокеты, синхронные сокеты клиента"
  - "протоколы, сокеты"
  - "Интернет, сокеты"
  - "сокеты клиента"
ms.assetid: 945d00c6-7202-466c-9df9-140b84156d43
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 12
---
# Использование синхронного сокета клиента
Синхронное сокет клиента приостанавливает программа приложения во время завершения сетевой операции.  Синхронные сокета не эквивалентны для приложений, выполняющих heavy использование сети для них операций, однако они могут включать простой доступ к сетевым службы для других приложений.  
  
 Чтобы отправить данные, передайте массив байтов до одного из методов отправить\- данных типа <xref:System.Net.Sockets.Socket> \(<xref:System.Net.Sockets.Socket.Send%2A> и <xref:System.Net.Sockets.Socket.SendTo%2A>\).  В следующем примере кодирует строку в буфер массива байтов с помощью свойства <xref:System.Text.Encoding.ASCII%2A?displayProperty=fullName>, а затем передать буфер в устройство сети с помощью метода **Отправить**.  Метод **Отправить** возвращает число байтов, отправленных на устройство в сети.  
  
```vb  
Dim msg As Byte() = _  
    System.Text.Encoding.ASCII.GetBytes("This is a test.")  
Dim bytesSent As Integer = s.Send(msg)  
  
```  
  
```csharp  
byte[] msg = System.Text.Encoding.ASCII.GetBytes("This is a test");  
int bytesSent = s.Send(msg);  
```  
  
 Метод **Отправить** удаляет байты из буфера и очередей их с сетевой интерфейс для отправки в устройство в сети.  Сетевой интерфейс не может отправлять данные немедленно, но он отправляет его наконец, если соединение будет закрыто обычно с помощью метода <xref:System.Net.Sockets.Socket.Shutdown%2A>.  
  
 Чтобы получить данные из устройства сети, передайте буфер до одного из методов получение\- данных типа **Сокет** \(<xref:System.Net.Sockets.Socket.Receive%2A> и <xref:System.Net.Sockets.Socket.ReceiveFrom%2A>\).  Синхронные сокета приостановят приложение до тех пор, пока байты не получены из сети или до тех пор, пока не закрыто сокета.  Следующий пример возвращает данные из сети и затем выводит его на консоль.  В примере предполагается, что данные, поступающих из сети ASCII\- закодированный текст.  Метод **Получить** возвращает число байтов, полученных из сети.  
  
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
  
 Когда сокет больше не нужен, его нужно освободить путем вызова метода <xref:System.Net.Sockets.Socket.Shutdown%2A>, а затем вызвать метод **Закрыть**.  В следующем примере освобождает **Сокет**.  Перечисление <xref:System.Net.Sockets.SocketShutdown> определяет константы, указывающие, должен ли сокет быть закрыто для отправки, получения или для обеих.  
  
```vb  
s.Shutdown(SocketShutdown.Both)  
s.Close()  
```  
  
```csharp  
s.Shutdown(SocketShutdown.Both);  
s.Close();  
```  
  
## См. также  
 [Использование асинхронных сокетов клиента](../../../docs/framework/network-programming/using-an-asynchronous-client-socket.md)   
 [Прослушивание с помощью сокетов](../../../docs/framework/network-programming/listening-with-sockets.md)   
 [Пример синхронного сокета клиента](../../../docs/framework/network-programming/synchronous-client-socket-example.md)