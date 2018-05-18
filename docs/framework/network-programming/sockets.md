---
title: сокеты
ms.date: 03/30/2017
helpviewer_keywords:
- application protocols, sockets
- sending data, sockets
- data requests, sockets
- Windows Sockets
- sockets, about sockets
- Socket class, about Socket class
- sockets
- requesting data from Internet, sockets
- network, sockets
- receiving data, sockets
- protocols, sockets
- Internet, sockets
ms.assetid: 10d22735-bd37-42c1-a2be-c1932f979a7d
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: b234846e63eab59602069aa72125df116e30375d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="sockets"></a>сокеты
Пространство имен <xref:System.Net.Sockets> содержит управляемую реализацию интерфейса Windows Sockets. Все остальные классы для доступа к сети в пространстве имен <xref:System.Net> основываются на этой реализации сокетов.  
  
 Класс <xref:System.Net.Sockets.Socket> платформы .NET Framework — это версия служб сокетов на основе управляемого кода, предоставляемая API Winsock32. В большинстве случаев методы класса **Socket** просто маршалируют данные в аналогичные собственные методы Win32 и осуществляют все необходимые проверки безопасности.  
  
 Класс **Socket** поддерживает два основных режима: синхронный и асинхронный. В синхронном режиме при вызове функций, выполняющих сетевые операции (например, <xref:System.Net.Sockets.Socket.Send%2A> и <xref:System.Net.Sockets.Socket.Receive%2A>), ожидается завершение операций, прежде чем управление возвращается вызывающей программе. В асинхронном режиме вызовы возвращаются немедленно.  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Создание сокета](../../../docs/framework/network-programming/how-to-create-a-socket.md)  
    
 [Использование протоколов приложений](../../../docs/framework/network-programming/using-application-protocols.md)
