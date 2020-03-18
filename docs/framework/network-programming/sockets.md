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
ms.openlocfilehash: cffad6b4677a880bd63f5ae0232c639f7a262c59
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "71047257"
---
# <a name="sockets"></a><span data-ttu-id="cc9d2-102">сокеты</span><span class="sxs-lookup"><span data-stu-id="cc9d2-102">Sockets</span></span>
<span data-ttu-id="cc9d2-103">Пространство имен <xref:System.Net.Sockets> содержит управляемую реализацию интерфейса Windows Sockets.</span><span class="sxs-lookup"><span data-stu-id="cc9d2-103">The <xref:System.Net.Sockets> namespace contains a managed implementation of the Windows Sockets interface.</span></span> <span data-ttu-id="cc9d2-104">Все остальные классы для доступа к сети в пространстве имен <xref:System.Net> основываются на этой реализации сокетов.</span><span class="sxs-lookup"><span data-stu-id="cc9d2-104">All other network-access classes in the <xref:System.Net> namespace are built on top of this implementation of sockets.</span></span>  
  
 <span data-ttu-id="cc9d2-105">Класс <xref:System.Net.Sockets.Socket> платформы .NET Framework — это версия служб сокетов на основе управляемого кода, предоставляемая API Winsock32.</span><span class="sxs-lookup"><span data-stu-id="cc9d2-105">The .NET Framework <xref:System.Net.Sockets.Socket> class is a managed-code version of the socket services provided by the Winsock32 API.</span></span> <span data-ttu-id="cc9d2-106">В большинстве случаев методы класса **Socket** просто маршалируют данные в аналогичные собственные методы Win32 и осуществляют все необходимые проверки безопасности.</span><span class="sxs-lookup"><span data-stu-id="cc9d2-106">In most cases, the **Socket** class methods simply marshal data into their native Win32 counterparts and handle any necessary security checks.</span></span>  
  
 <span data-ttu-id="cc9d2-107">Класс **Socket** поддерживает два основных режима: синхронный и асинхронный.</span><span class="sxs-lookup"><span data-stu-id="cc9d2-107">The **Socket** class supports two basic modes, synchronous and asynchronous.</span></span> <span data-ttu-id="cc9d2-108">В синхронном режиме при вызове функций, выполняющих сетевые операции (например, <xref:System.Net.Sockets.Socket.Send%2A> и <xref:System.Net.Sockets.Socket.Receive%2A>), ожидается завершение операций, прежде чем управление возвращается вызывающей программе.</span><span class="sxs-lookup"><span data-stu-id="cc9d2-108">In synchronous mode, calls to functions that perform network operations (such as <xref:System.Net.Sockets.Socket.Send%2A> and <xref:System.Net.Sockets.Socket.Receive%2A>) wait until the operation completes before returning control to the calling program.</span></span> <span data-ttu-id="cc9d2-109">В асинхронном режиме вызовы возвращаются немедленно.</span><span class="sxs-lookup"><span data-stu-id="cc9d2-109">In asynchronous mode, these calls return immediately.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc9d2-110">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cc9d2-110">See also</span></span>

- [<span data-ttu-id="cc9d2-111">Практическое руководство. Создание сокета</span><span class="sxs-lookup"><span data-stu-id="cc9d2-111">How to: Create a Socket</span></span>](how-to-create-a-socket.md)

- [<span data-ttu-id="cc9d2-112">Использование протоколов приложений</span><span class="sxs-lookup"><span data-stu-id="cc9d2-112">Using Application Protocols</span></span>](using-application-protocols.md)
