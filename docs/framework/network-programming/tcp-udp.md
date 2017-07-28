---
title: "TCP/UDP | Microsoft Docs"
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
  - "протоколы, TCP/UDP"
  - "сетевые ресурсы, TCP/UDP"
  - "отправка данных, TCP/UDP"
  - "TCP/UDP"
  - "класс TcpClient, сведения о классе TcpClient"
  - "протоколы приложений, TCP/UDP"
  - "получение данных, TCP/UDP"
  - "класс TcpListener, сведения о классе TcpListener"
  - "класс Socket, сведения о классе Socket"
  - "UDP"
  - "запросы данных, TCP/UDP"
  - "запрос данных из Интернета, TCP/UDP"
  - "Интернет, TCP/UDP"
ms.assetid: df29b4b0-49e8-4923-82b9-13150dfc40f5
caps.latest.revision: 8
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# TCP/UDP
Приложения могут использовать службы TCP \(TCP\) и UDP \(UDP\) с <xref:System.Net.Sockets.TcpClient>, <xref:System.Net.Sockets.TcpListener> и классами <xref:System.Net.Sockets.UdpClient>.  Эти классы протокола строятся поверх класса <xref:System.Net.Sockets.Socket?displayProperty=fullName> и позаботятся сведения о передачи данных.  
  
 Классы протокола используют синхронные методы класса **Сокет**, чтобы предоставить простой и простой доступ к сетевым службам без затрат на обслуживание сведения о состоянии или знать сведения сокетов протокол\- для создания.  Для использования асинхронных методов **Сокет** можно использовать асинхронные методы, предоставляемые классом <xref:System.Net.Sockets.NetworkStream>.  Для доступа к функции **Сокет** не классифицируйте предоставляемый классами протокола, необходимо использовать класс **Сокет**.  
  
 **TcpClient** и **TcpListener** представляют сети с использованием класса **NetworkStream**.  Используется метод <xref:System.Net.Sockets.TcpClient.GetStream%2A> для возвращения сетевой поток, а затем вызовите методы <xref:System.Net.Sockets.NetworkStream.Read%2A> и <xref:System.Net.Sockets.NetworkStream.Write%2A> потока.  **NetworkStream** не имеет сокет классов, лежащие в основе протокола, поэтому он не влияет на закрыть сокет.  
  
 Класс **UdpClient** использует байтовый массив для хранения датаграмму UDP.  Используется метод <xref:System.Net.Sockets.UdpClient.Send%2A> отправлять данные в сети, и метод <xref:System.Net.Sockets.UdpClient.Receive%2A> для получения входящую датаграмму.  
  
## См. также  
 [Использование служб TCP](../../../docs/framework/network-programming/using-tcp-services.md)   
 [Использование служб UDP](../../../docs/framework/network-programming/using-udp-services.md)   
 [Использование потоков в сети](../../../docs/framework/network-programming/using-streams-on-the-network.md)   
 [Использование асинхронных сокетов сервера](../../../docs/framework/network-programming/using-an-asynchronous-server-socket.md)   
 [Использование асинхронных сокетов клиента](../../../docs/framework/network-programming/using-an-asynchronous-client-socket.md)   
 [Использование протоколов приложений](../../../docs/framework/network-programming/using-application-protocols.md)