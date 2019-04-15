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
ms.openlocfilehash: 4a1b18f2c31bf8dad8cf32e2e5205cf3008e7b18
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136049"
---
# <a name="sockets"></a>сокеты
Пространство имен <xref:System.Net.Sockets> содержит управляемую реализацию интерфейса Windows Sockets. Все остальные классы для доступа к сети в пространстве имен <xref:System.Net> основываются на этой реализации сокетов.  
  
 Класс <xref:System.Net.Sockets.Socket> платформы .NET Framework — это версия служб сокетов на основе управляемого кода, предоставляемая API Winsock32. В большинстве случаев методы класса **Socket** просто маршалируют данные в аналогичные собственные методы Win32 и осуществляют все необходимые проверки безопасности.  
  
 Класс **Socket** поддерживает два основных режима: синхронный и асинхронный. В синхронном режиме при вызове функций, выполняющих сетевые операции (например, <xref:System.Net.Sockets.Socket.Send%2A> и <xref:System.Net.Sockets.Socket.Receive%2A>), ожидается завершение операций, прежде чем управление возвращается вызывающей программе. В асинхронном режиме вызовы возвращаются немедленно.  
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Создание сокета](../../../docs/framework/network-programming/how-to-create-a-socket.md)

- [Использование протоколов приложений](../../../docs/framework/network-programming/using-application-protocols.md)
