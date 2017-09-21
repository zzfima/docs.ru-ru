---
title: TCP-UDP
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
- protocols, TCP/UDP
- network resources, TCP/UDP
- sending data, TCP/UDP
- TCP/UDP
- TcpClient class, about TcpClient class
- application protocols, TCP/UDP
- receiving data, TCP/UDP
- TcpListener class, about TcpListener class
- Socket class, about Socket class
- UDP
- data requests, TCP/UDP
- requesting data from Internet, TCP/UDP
- Internet, TCP/UDP
ms.assetid: df29b4b0-49e8-4923-82b9-13150dfc40f5
caps.latest.revision: 8
author: mcleblanc
ms.author: markl
manager: markl
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f067d24b59fbb5b49803605a625cef52d12fdbea
ms.contentlocale: ru-ru
ms.lasthandoff: 08/21/2017

---
# <a name="tcp-udp"></a>TCP-UDP
Приложения могут использовать службы TCP и UDP с классами <xref:System.Net.Sockets.TcpClient>, <xref:System.Net.Sockets.TcpListener> и <xref:System.Net.Sockets.UdpClient>. Эти классы протоколов основаны на классе <xref:System.Net.Sockets.Socket?displayProperty=fullName> и управляют различными аспектами передачи данных.  
  
 Классы протоколов используют синхронные методы класса **Socket** для обеспечения простого доступа к сетевым службам без накладных расходов, связанных с сохранением сведений о состоянии. При этом также не требуется знать особенности настройки сокетов для определенного протокола. Для использования асинхронных методов **Socket** можно применять асинхронные методы, предоставляемые классом <xref:System.Net.Sockets.NetworkStream>. Для доступа к возможностям класса **Socket**, которые не предоставляются классами протоколов, необходимо использовать класс **Socket**.  
  
 **TcpClient** и **TcpListener** представляют сеть с помощью класса **NetworkStream**. С помощью метода <xref:System.Net.Sockets.TcpClient.GetStream%2A> возвращается сетевой поток, после чего вызываются методы <xref:System.Net.Sockets.NetworkStream.Read%2A> и <xref:System.Net.Sockets.NetworkStream.Write%2A> потока. Базовый сокет классов протоколов не принадлежит классу **NetworkStream**, поэтому закрытие этого класса не влияет на сокет.  
  
 Класс **UdpClient** использует массив байтов для хранения датаграммы UDP. С помощью метода <xref:System.Net.Sockets.UdpClient.Send%2A> данные отправляются в сеть, а с помощью метода <xref:System.Net.Sockets.UdpClient.Receive%2A> принимается входящая датаграмма.  
  
## <a name="see-also"></a>См. также  
 [Использование служб TCP](../../../docs/framework/network-programming/using-tcp-services.md)   
 [Использование служб UDP](../../../docs/framework/network-programming/using-udp-services.md)   
 [Использование потоков в сети](../../../docs/framework/network-programming/using-streams-on-the-network.md)   
 [Использование асинхронных сокетов сервера](../../../docs/framework/network-programming/using-an-asynchronous-server-socket.md)   
 [Использование асинхронных сокетов клиента](../../../docs/framework/network-programming/using-an-asynchronous-client-socket.md)   
 [Использование протоколов приложений](../../../docs/framework/network-programming/using-application-protocols.md)

