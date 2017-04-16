---
title: "Использование синхронного сокета сервера | Microsoft Docs"
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
  - "синхронные сокеты сервера"
  - "отправка данных, сокеты"
  - "запросы данных, сокеты"
  - "запрос данных из Интернета, сокеты"
  - "сокеты сервера"
  - "получение данных, сокеты"
  - "класс Socket, синхронные сокеты сервера"
  - "протоколы, сокеты"
  - "сокеты, синхронные сокеты сервера"
  - "Интернет, сокеты"
ms.assetid: d1ce882e-653e-41f5-9289-844ec855b804
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Использование синхронного сокета сервера
Синхронные сокета сервера приостановят выполнение приложения до тех пор, пока не получен запрос на соединение для сокета.  Синхронные сокета сервера не эквивалентны для приложений, выполняющих heavy использование сети в связанных с ними операций, однако они могут быть подходящими для приложений простой сети.  
  
 После установления <xref:System.Net.Sockets.Socket> для прослушивания конечной точке с использованием методов <xref:System.Net.Sockets.Socket.Bind%2A> и <xref:System.Net.Sockets.Socket.Listen%2A>, она готова принимать запросы входящего подключения с помощью метода <xref:System.Net.Sockets.Socket.Accept%2A>.  Приложение приостановитьо до тех пор, пока запрос на соединение не получен при **Принять** вызвать метод.  
  
 Если запрос подключения получен **Принять** возвращает новый экземпляр **Сокет**, который связан с клиентом при подключении.  В следующем примере считывает данные от клиента, выводит его на консоль и вторит данным обратно клиенту.  **Сокет** Не указала никакого протокол обмена сообщениями, поэтому метки "\<EOF\>" строки конец данных сообщения.  Это предполагает, что **Сокет** с именем `listener`  было инициализируется и было привязано к конечной точке.  
  
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
  
## См. также  
 [Использование асинхронных сокетов сервера](../../../docs/framework/network-programming/using-an-asynchronous-server-socket.md)   
 [Пример синхронного сокета сервера](../../../docs/framework/network-programming/synchronous-server-socket-example.md)   
 [Прослушивание с помощью сокетов](../../../docs/framework/network-programming/listening-with-sockets.md)