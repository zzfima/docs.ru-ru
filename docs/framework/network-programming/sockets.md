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
ms.openlocfilehash: ce7ded81ad23c2df55afa9360435e8391fea7a63
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47176829"
---
# <a name="sockets"></a><span data-ttu-id="4bb5f-102">сокеты</span><span class="sxs-lookup"><span data-stu-id="4bb5f-102">Sockets</span></span>
<span data-ttu-id="4bb5f-103">Пространство имен <xref:System.Net.Sockets> содержит управляемую реализацию интерфейса Windows Sockets.</span><span class="sxs-lookup"><span data-stu-id="4bb5f-103">The <xref:System.Net.Sockets> namespace contains a managed implementation of the Windows Sockets interface.</span></span> <span data-ttu-id="4bb5f-104">Все остальные классы для доступа к сети в пространстве имен <xref:System.Net> основываются на этой реализации сокетов.</span><span class="sxs-lookup"><span data-stu-id="4bb5f-104">All other network-access classes in the <xref:System.Net> namespace are built on top of this implementation of sockets.</span></span>  
  
 <span data-ttu-id="4bb5f-105">Класс <xref:System.Net.Sockets.Socket> платформы .NET Framework — это версия служб сокетов на основе управляемого кода, предоставляемая API Winsock32.</span><span class="sxs-lookup"><span data-stu-id="4bb5f-105">The .NET Framework <xref:System.Net.Sockets.Socket> class is a managed-code version of the socket services provided by the Winsock32 API.</span></span> <span data-ttu-id="4bb5f-106">В большинстве случаев методы класса **Socket** просто маршалируют данные в аналогичные собственные методы Win32 и осуществляют все необходимые проверки безопасности.</span><span class="sxs-lookup"><span data-stu-id="4bb5f-106">In most cases, the **Socket** class methods simply marshal data into their native Win32 counterparts and handle any necessary security checks.</span></span>  
  
 <span data-ttu-id="4bb5f-107">Класс **Socket** поддерживает два основных режима: синхронный и асинхронный.</span><span class="sxs-lookup"><span data-stu-id="4bb5f-107">The **Socket** class supports two basic modes, synchronous and asynchronous.</span></span> <span data-ttu-id="4bb5f-108">В синхронном режиме при вызове функций, выполняющих сетевые операции (например, <xref:System.Net.Sockets.Socket.Send%2A> и <xref:System.Net.Sockets.Socket.Receive%2A>), ожидается завершение операций, прежде чем управление возвращается вызывающей программе.</span><span class="sxs-lookup"><span data-stu-id="4bb5f-108">In synchronous mode, calls to functions that perform network operations (such as <xref:System.Net.Sockets.Socket.Send%2A> and <xref:System.Net.Sockets.Socket.Receive%2A>) wait until the operation completes before returning control to the calling program.</span></span> <span data-ttu-id="4bb5f-109">В асинхронном режиме вызовы возвращаются немедленно.</span><span class="sxs-lookup"><span data-stu-id="4bb5f-109">In asynchronous mode, these calls return immediately.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bb5f-110">См. также</span><span class="sxs-lookup"><span data-stu-id="4bb5f-110">See Also</span></span>  
 [<span data-ttu-id="4bb5f-111">Практическое руководство. Создание сокета</span><span class="sxs-lookup"><span data-stu-id="4bb5f-111">How to: Create a Socket</span></span>](../../../docs/framework/network-programming/how-to-create-a-socket.md)  
    
 [<span data-ttu-id="4bb5f-112">Использование протоколов приложений</span><span class="sxs-lookup"><span data-stu-id="4bb5f-112">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)
