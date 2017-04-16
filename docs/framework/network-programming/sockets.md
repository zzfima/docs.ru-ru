---
title: "Сокеты | Microsoft Docs"
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
  - "Сокеты Windows"
  - "сокеты, о сокетах"
  - "класс Socket, о классе Socket"
  - "сокеты"
  - "запрос данных из Интернета, сокеты"
  - "сеть. сокеты"
  - "получение данных, сокеты"
  - "протоколы, сокеты"
  - "Интернет, сокеты"
ms.assetid: 10d22735-bd37-42c1-a2be-c1932f979a7d
caps.latest.revision: 8
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 6
---
# Сокеты
Пространство имен <xref:System.Net.Sockets> содержит управляемую реализацию интерфейса Windows sockets.  Все другие классы сеть\- доступа в пространстве имен <xref:System.Net> построены на этой реализации сокетов.  
  
 Класс платформы .NET Framework <xref:System.Net.Sockets.Socket> версия служб сокета, предоставленных API управляемого кода Winsock32.  В большинстве случаев методы класса **Сокет** просто маршалируют данные в их аналоги собственного Win32 и обрабатывают все необходимые проверки безопасности.  
  
 Класс **Сокет** поддерживает 2 основных режимов, синхронный и асинхронный.  В синхронном режиме, вызовы функций, которые выполняют операции сети \(например <xref:System.Net.Sockets.Socket.Send%2A> \) и <xref:System.Net.Sockets.Socket.Receive%2A> ожидать, пока операция не завершается до возвращения элемента управления в вызывающей программе.  В асинхронном режиме, эти вызовы возвращают немедленно.  
  
## См. также  
 [Практическое руководство. Создание сокета](../../../docs/framework/network-programming/how-to-create-a-socket.md)   
 [TCP\/UDP](../../../docs/framework/network-programming/tcp-udp.md)   
 [Использование протоколов приложений](../../../docs/framework/network-programming/using-application-protocols.md)