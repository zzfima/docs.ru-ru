---
title: "Практическое руководство. Создание сокета | Microsoft Docs"
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
  - "Сеть"
  - "отправка данных, сокеты"
  - "запросы данных, сокеты"
  - "запрос данных из Интернета, сокеты"
  - "класс Socket, создание сокетов"
  - "Сетевые ресурсы"
  - "получение данных, сокеты"
  - "протоколы, сокеты"
  - "Интернет, сокеты"
  - "сокеты, создание"
ms.assetid: c64a049c-5981-43bc-a2dc-1851473589c7
caps.latest.revision: 7
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 7
---
# Практическое руководство. Создание сокета
Прежде чем можно будет использовать, когда сокет для обмена данными с удаленными устройствами, когда сокет должна быть инициализирована с данными и протокола сетевого адреса.  Конструктор для класса <xref:System.Net.Sockets.Socket> имеющий параметры, определяющие семейство адресов, типом сокета, а типом протокола, который используется, когда сокет для этого соединения.  
  
## Пример  
 Следующий пример создает сокет, который может использоваться для взаимодействия по сети TCP\/IP\-based, например Интернет.  
  
```csharp  
Socket s = new Socket(AddressFamily.InterNetwork,   
   SocketType.Stream, ProtocolType.Tcp);  
```  
  
```vb  
Dim s as New Socket(AddressFamily.InterNetwork, _  
   SocketType.Stream, ProtocolType.Tcp)  
  
```  
  
 Для использования протокола UDP вместо TCP, измените тип протокола, например в следующем примере:  
  
```csharp  
Socket s = new Socket(AddressFamily.InterNetwork,   
   SocketType.Dgram, ProtocolType.Udp);  
```  
  
```vb  
Dim s as New Socket(AddressFamily.InterNetwork, _  
   SocketType.Dgram, ProtocolType.Udp)  
  
```  
  
 Перечисление <xref:System.Net.Sockets.AddressFamily> определяет стандартные семейства адресов, используемые классом **Сокет** для предоставления сетевого адреса \(например, элемент **AddressFamily.InterNetwork** указывает семейство адресов версии 4 протокола IP\).  
  
 Перечисление <xref:System.Net.Sockets.SocketType> указывает тип сокета \(например, элемент **SocketType.Stream** отображает стандартное сокет для отправки и получения данных с элементом управления потоком\).  
  
 Перечисление <xref:System.Net.Sockets.ProtocolType> указывающее сетевой протокол, используемый для связи на **Сокет** \(например, **ProtocolType.Tcp** указывает, что используется, когда сокет TCP; **ProtocolType.Udp** указывает, что когда сокет использует протокол UDP\).  
  
 После **Сокет** создано, он может инициировать подключение к удаленной конечной точке получить из удаленных соединений или устройств.  
  
## См. также  
 [Использование сокетов клиента](../../../docs/framework/network-programming/using-client-sockets.md)   
 [Прослушивание с помощью сокетов](../../../docs/framework/network-programming/listening-with-sockets.md)